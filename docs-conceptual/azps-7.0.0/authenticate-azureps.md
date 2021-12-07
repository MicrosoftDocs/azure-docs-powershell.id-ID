---
title: Masuk dengan Azure PowerShell
description: Cara masuk dengan Azure PowerShell sebagai pengguna, kepala layanan, atau dengan identitas terkelola untuk sumber daya Azure.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/02/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: e67b60013fb8577ec18bc8da59c431cf234241e1
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "133988928"
---
# <a name="sign-in-with-azure-powershell"></a>Masuk dengan Azure PowerShell

Azure PowerShell mendukung beberapa metode otentikasi. Cara termudah untuk memulai adalah dengan [Azure Cloud Shell,](/azure/cloud-shell/overview)yang secara otomatis masuk ke Dalam Anda. Dengan instalasi lokal, Anda dapat masuk secara interaktif melalui browser Anda. Saat menulis skrip untuk otomatisasi, pendekatan yang disarankan adalah menggunakan [prinsip layanan](create-azure-service-principal-azureps.md) dengan izin yang diperlukan. Saat Anda membatasi izin masuk sebanyak mungkin untuk kasus penggunaan Anda, Anda membantu menjaga keamanan sumber daya Azure Anda.

Awalnya, Anda masuk ke langganan pertama Azure kembali jika Anda memiliki akses ke lebih dari satu langganan. Perintah dijalankan terhadap langganan ini secara default. Untuk mengubah langganan aktif Anda untuk sesi, gunakan cmdlet [Set-AzContext.](/powershell/module/az.accounts/set-azcontext) Untuk mengubah langganan aktif Anda dan mempertahankannya di antara sesi pada sistem yang sama, gunakan cmdlet [Select-AzContext.](/powershell/module/az.accounts/select-azcontext)

> [!IMPORTANT]
> Kredensial Anda dibagikan di antara beberapa sesi PowerShell selama Anda tetap masuk.
> Untuk informasi selengkapnya, lihat artikel tentang [Kredensial Persisten.](context-persistence.md)

## <a name="sign-in-interactively"></a>Masuk secara interaktif

Untuk masuk secara interaktif, gunakan [cmdlet Koneksi-AzAccount.](/powershell/module/az.accounts/connect-azaccount)

```azurepowershell-interactive
Connect-AzAccount
```

Dimulai dengan modul Az PowerShell versi 5.0.0, cmdlet ini menyajikan prompt login berbasis browser interaktif secara default. Anda dapat menentukan `UseDeviceAuthentication` parameter untuk menerima string token yang sebelumnya default untuk PowerShell versi 6 dan lebih tinggi.

> [!IMPORTANT]
> Otorisasi kredensial nama pengguna/kata sandi telah dihapus di Azure PowerShell karena perubahan dalam implementasi otorisasi Direktori Aktif dan masalah keamanan. Jika Anda menggunakan otorisasi kredensial untuk tujuan otomatisasi, alih-alih [membuat prinsip layanan.](create-azure-service-principal-azureps.md)

Gunakan cmdlet [Get-AzContext](/powershell/module/az.accounts/get-azcontext) untuk menyimpan ID penyewa Anda dalam variabel yang akan digunakan dalam dua bagian berikutnya dari artikel ini.

```azurepowershell-interactive
$tenantId = (Get-AzContext).Tenant.Id
```

## <a name="sign-in-with-a-service-principal"></a>Masuk dengan kepala layanan

Kepala layanan adalah akun Azure non-interaktif. Seperti akun pengguna lainnya, izin mereka dikelola dengan Azure Active Directory. Dengan memberikan prinsip layanan hanya izin yang dibutuhkan, skrip otomatisasi Anda tetap aman.

Untuk mempelajari cara membuat prinsip layanan untuk digunakan dengan Azure PowerShell, lihat [Membuat kepala layanan Azure dengan Azure PowerShell](create-azure-service-principal-azureps.md).

Untuk masuk dengan kepala layanan, gunakan `ServicePrincipal` parameter `Connect-AzAccount` cmdlet. Anda juga akan memerlukan ID aplikasi kepala layanan, kredensial masuk, dan ID penyewa yang terkait dengan kepala layanan. Bagaimana Anda masuk dengan kepala layanan tergantung pada apakah itu dikonfigurasi untuk otentikasi berbasis kata sandi atau berbasis sertifikat.

### <a name="password-based-authentication"></a>Autentikasi berbasis kata sandi

Buat prinsip layanan untuk digunakan dalam contoh di bagian ini. Untuk informasi selengkapnya tentang membuat prinsip layanan, lihat [Membuat kepala layanan Azure dengan Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps).

```azurepowershell-interactive
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName
```

Untuk mendapatkan kredensial kepala layanan sebagai objek yang sesuai, gunakan cmdlet [Get-Credential.](/powershell/module/microsoft.powershell.security/get-credential) Cmdlet ini menyajikan prompt untuk nama pengguna dan kata sandi. Gunakan kepala layanan `applicationID` untuk nama pengguna dan konversi `secret` ke teks biasa untuk kata sandi.

```azurepowershell-interactive
# Retrieve the plain text password for use with `Get-Credential` in the next command.
$sp.secret | ConvertFrom-SecureString -AsPlainText

$pscredential = Get-Credential -UserName $sp.ApplicationId
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

Untuk skenario otomatisasi, Anda perlu membuat kredensial dari kepala layanan `applicationId` `secret` dan:

```azurepowershell-interactive
$pscredential = New-Object -TypeName System.Management.Automation.PSCredential($sp.ApplicationId, $sp.Secret)
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

Pastikan Anda menggunakan praktik penyimpanan kata sandi yang baik saat mengotomatisasi koneksi utama layanan.

### <a name="certificate-based-authentication"></a>Autentikasi berbasis sertifikat

Otentikasi berbasis sertifikat mengharuskan Azure PowerShell dapat mengambil informasi dari toko sertifikat lokal berdasarkan cap jempol sertifikat.

```azurepowershell-interactive
Connect-AzAccount -ApplicationId $appId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

Saat menggunakan kepala layanan alih-alih aplikasi terdaftar, tentukan `ServicePrincipal` parameter dan berikan ID Aplikasi kepala layanan sebagai nilai `-ApplicationId` parameter.

```azurepowershell-interactive
Connect-AzAccount -ServicePrincipal -ApplicationId $servicePrincipalId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

Di PowerShell 5.1, toko sertifikat dapat dikelola dan diperiksa dengan modul [PKI.](/powershell/module/pki) Untuk PowerShell 6.x dan yang lebih baru, prosesnya lebih rumit.
Skrip berikut menunjukkan kepada Anda cara mengimpor sertifikat yang sudah ada ke toko sertifikat yang dapat diakses oleh PowerShell.

#### <a name="import-a-certificate-in-powershell-51"></a>Mengimpor sertifikat di PowerShell 5.1

```azurepowershell-interactive
# Import a PFX
$credentials = Get-Credential -Message "Provide PFX private key password"
Import-PfxCertificate -FilePath <path to certificate> -Password $credentials.Password -CertStoreLocation cert:\CurrentUser\My
```

#### <a name="import-a-certificate-in-powershell-core-6x-and-later"></a>Mengimpor sertifikat di PowerShell Core 6.x dan yang lebih baru

```azurepowershell-interactive
# Import a PFX
$storeName = [System.Security.Cryptography.X509Certificates.StoreName]::My
$storeLocation = [System.Security.Cryptography.X509Certificates.StoreLocation]::CurrentUser
$store = [System.Security.Cryptography.X509Certificates.X509Store]::new($storeName, $storeLocation)
$certPath = <path to certificate>
$credentials = Get-Credential -Message "Provide PFX private key password"
$flag = [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::Exportable
$certificate = [System.Security.Cryptography.X509Certificates.X509Certificate2]::new($certPath, $credentials.Password, $flag)
$store.Open([System.Security.Cryptography.X509Certificates.OpenFlags]::ReadWrite)
$store.Add($Certificate)
$store.Close()
```

## <a name="sign-in-using-a-managed-identity"></a>Masuk menggunakan identitas terkelola

Identitas yang dikelola adalah fitur dari Azure Active Directory. Identitas yang dikelola adalah kepala layanan yang ditugaskan untuk sumber daya yang berjalan di Azure. Anda dapat menggunakan prinsipal layanan identitas terkelola untuk masuk, dan memperoleh token akses khusus aplikasi untuk mengakses sumber daya lain. Identitas terkelola hanya tersedia pada sumber daya yang berjalan di cloud Azure.

Contoh ini terhubung menggunakan identitas terkelola dari lingkungan host. Misalnya, jika dijalankan pada VirtualMachine dengan Identitas Layanan Terkelola yang ditetapkan, ini memungkinkan kode untuk masuk menggunakan identitas yang ditetapkan.

```azurepowershell-interactive
 Connect-AzAccount -Identity
```

Contoh ini terhubung menggunakan Identitas Layanan Terkelola myUserAssignedIdentity. Ini menambahkan identitas yang ditetapkan pengguna ke mesin virtual, lalu terhubung menggunakan ClientId dari identitas yang ditetapkan pengguna. Untuk informasi selengkapnya, lihat [Mengonfigurasi identitas terkelola untuk sumber daya Azure pada Azure VM](/active-directory/managed-identities-azure-resources/qs-configure-powershell-windows-vm).

```azurepowershell-interactive
$identity = Get-AzUserAssignedIdentity -ResourceGroupName 'myResourceGroup' -Name 'myUserAssignedIdentity'
Get-AzVM -ResourceGroupName contoso -Name testvm | Update-AzVM -IdentityType UserAssigned -IdentityId $identity.Id
Connect-AzAccount -Identity -AccountId $identity.ClientId # Run on the virtual machine

Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
yyyy-yyyy-yyyy-yyyy    Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

## <a name="sign-in-with-a-non-default-tenant-or-as-a-cloud-solution-provider-csp"></a>Masuk dengan penyewa non-default atau sebagai Penyedia Solusi Cloud (CSP)

Jika akun Anda dikaitkan dengan lebih dari satu penyewa, masuk memerlukan `Tenant` parameter yang akan ditentukan saat menghubungkan. Parameter ini bekerja dengan metode masuk. Saat masuk, nilai parameter ini bisa berupa ID objek Azure dari penyewa (Id Penyewa) atau nama domain penyewa yang berkualifikasi penuh.

Jika Anda seorang [Penyedia Solusi Cloud (CSP),](https://azure.microsoft.com/offers/ms-azr-0145p/)nilai untuk `Tenant` parameter **harus** menjadi ID penyewa.

```azurepowershell-interactive
Connect-AzAccount -Tenant '00000000-0000-0000-0000-000000000000'
```

## <a name="sign-in-to-another-cloud"></a>Masuk ke cloud lain

Layanan cloud Azure menawarkan lingkungan yang sesuai dengan undang-undang penanganan data regional. Untuk akun di cloud regional, atur lingkungan saat Anda masuk dengan `Environment` parameter. Parameter ini bekerja dengan metode masuk. Misalnya, jika akun Anda berada di Azure China 21Vianet:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

Perintah berikut mendapatkan daftar lingkungan yang tersedia:

```azurepowershell-interactive
Get-AzEnvironment | Select-Object -Property Name
```
