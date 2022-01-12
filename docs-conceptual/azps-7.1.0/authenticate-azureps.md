---
title: Masuk dengan Azure PowerShell
description: Cara masuk dengan pengguna Azure PowerShell pengguna, prinsipal layanan, atau dengan identitas yang dikelola untuk sumber daya Azure.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/06/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: afb64db4a009b325bb71828683a2a79c0e9bef49
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "135958518"
---
# <a name="sign-in-with-azure-powershell"></a>Masuk dengan Azure PowerShell

Azure PowerShell mendukung beberapa metode autentikasi. Cara termudah untuk memulai adalah dengan [Azure Cloud Shell,](/azure/cloud-shell/overview)yang secara otomatis mencatat Anda. Dengan instalasi lokal, Anda bisa masuk secara interaktif melalui browser Anda. Ketika menulis skrip untuk otomatisasi, pendekatan yang direkomendasikan adalah menggunakan [prinsipal layanan](create-azure-service-principal-azureps.md) dengan izin yang diperlukan. Jika Anda membatasi izin masuk sebanyak mungkin untuk kasus penggunaan, Anda membantu menjaga sumber daya Azure Anda tetap aman.

Pada awalnya, Anda masuk ke langganan pertama azure jika memiliki akses ke lebih dari satu langganan. Perintah dijalankan terhadap langganan ini secara default. Untuk mengubah langganan aktif Anda selama satu sesi, gunakan cmdlet [Set-AzContext.](/powershell/module/az.accounts/set-azcontext) Untuk mengubah langganan aktif Anda dan membuatnya tetap berada di antara sesi pada sistem yang sama, gunakan cmdlet [Select-AzContext.](/powershell/module/az.accounts/select-azcontext)

> [!IMPORTANT]
> Kredensial Dibagikan di antara beberapa sesi PowerShell selama Anda tetap masuk.
> Untuk informasi selengkapnya, lihat artikel tentang [Kredensial Tetap.](context-persistence.md)

## <a name="sign-in-interactively"></a>Masuk secara interaktif

Untuk masuk secara interaktif, gunakan cmdlet [Koneksi-AzAccount.](/powershell/module/az.accounts/connect-azaccount)

```azurepowershell-interactive
Connect-AzAccount
```

Dimulai dengan modul Az PowerShell versi 5.0.0, cmdlet ini menampilkan perintah masuk berbasis browser interaktif secara default. Anda dapat menentukan `UseDeviceAuthentication` parameter untuk menerima string token yang sebelumnya merupakan default untuk PowerShell versi 6 dan lebih tinggi.

> [!IMPORTANT]
> Otorisasi kredensial nama pengguna/kata sandi telah dihapus Azure PowerShell karena perubahan dalam implementasi otorisasi Direktori Aktif dan masalah keamanan. Jika Anda menggunakan otorisasi kredensial untuk tujuan otomatisasi, sebagai [gantinya buat prinsipal layanan](create-azure-service-principal-azureps.md).

Gunakan cmdlet [Get-AzContext](/powershell/module/az.accounts/get-azcontext) untuk menyimpan ID penyewa Dalam variabel yang akan digunakan di dua bagian berikutnya dalam artikel ini.

```azurepowershell-interactive
$tenantId = (Get-AzContext).Tenant.Id
```

## <a name="sign-in-with-a-service-principal"></a>Masuk dengan prinsipal layanan

Prinsipal layanan adalah akun Azure yang tidak interaktif. Seperti akun pengguna lain, izin mereka dikelola dengan Azure Active Directory. Dengan memberikan izin yang diperlukan hanya prinsipal layanan, skrip otomatisasi Anda tetap aman.

Untuk mempelajari cara membuat prinsipal layanan untuk digunakan dengan Azure PowerShell, lihat [Membuat prinsipal layanan Azure dengan Azure PowerShell](create-azure-service-principal-azureps.md).

Untuk masuk dengan prinsipal layanan, `ServicePrincipal` gunakan parameter `Connect-AzAccount` cmdlet. Anda juga akan memerlukan ID aplikasi prinsipal layanan, kredensial masuk, dan ID penyewa terkait dengan prinsipal layanan. Cara Anda masuk dengan prinsipal layanan bergantung pada konfigurasi untuk autentikasi berbasis kata sandi atau berbasis sertifikat.

### <a name="password-based-authentication"></a>Autentikasi berbasis kata sandi

Buat prinsipal layanan yang akan digunakan dalam contoh di bagian ini. Untuk informasi selengkapnya tentang pembuatan prinsipal layanan, [lihat Membuat prinsipal layanan Azure dengan Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps).

```azurepowershell-interactive
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName
```

Untuk mendapatkan kredensial prinsipal layanan sebagai objek yang tepat, gunakan cmdlet [Get-Credential.](/powershell/module/microsoft.powershell.security/get-credential) Cmdlet ini menampilkan perintah untuk nama pengguna dan kata sandi. Gunakan prinsipal layanan untuk `applicationID` nama pengguna dan konversi ke teks biasa bagi kata `secret` sandi.

```azurepowershell-interactive
# Retrieve the plain text password for use with `Get-Credential` in the next command.
$sp.PasswordCredentials.SecretText

$pscredential = Get-Credential -UserName $sp.AppId
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

Untuk skenario otomatisasi, Anda perlu membuat kredensial dari prinsipal layanan `AppId` dan `SecretText` :

```azurepowershell-interactive
$SecureStringPwd = $sp.PasswordCredentials.SecretText | ConvertTo-SecureString -AsPlainText -Force
$pscredential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $sp.AppId, $SecureStringPwd
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

Pastikan Anda menggunakan praktik penyimpanan kata sandi yang bagus ketika mengotomatiskan koneksi prinsipal layanan.

### <a name="certificate-based-authentication"></a>Autentikasi berbasis sertifikat

Autentikasi berbasis sertifikat mengharuskan Azure PowerShell mengambil informasi dari penyimpanan sertifikat lokal berdasarkan pada thumbprint sertifikat.

```azurepowershell-interactive
Connect-AzAccount -ApplicationId $appId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

Ketika menggunakan prinsipal layanan dan bukan aplikasi terdaftar, tentukan parameter dan sediakan ID Aplikasi prinsipal layanan `ServicePrincipal` `-ApplicationId` sebagai nilai parameter.

```azurepowershell-interactive
Connect-AzAccount -ServicePrincipal -ApplicationId $servicePrincipalId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

Di PowerShell 5.1, penyimpanan sertifikat dapat dikelola dan diperiksa dengan [modul PKI.](/powershell/module/pki) Untuk PowerShell 6.x dan yang lebih baru, prosesnya lebih rumit.
Skrip berikut ini memperlihatkan cara mengimpor sertifikat yang sudah ada ke penyimpanan sertifikat yang dapat diakses oleh PowerShell.

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

Identitas yang dikelola adalah fitur penting Azure Active Directory. Identitas terkelola adalah prinsipal layanan yang ditetapkan ke sumber daya yang dijalankan di Azure. Anda dapat menggunakan prinsipal layanan identitas terkelola untuk masuk, dan memperoleh token akses aplikasi-saja untuk mengakses sumber daya lainnya. Identitas terkelola hanya tersedia pada sumber daya yang berjalan di awan Azure.

This example connects using the managed identity of the host environment. Misalnya, jika dijalankan di VirtualMachine dengan Identitas Layanan Terkelola yang ditetapkan, hal ini memungkinkan kode untuk masuk menggunakan identitas yang ditetapkan tersebut.

```azurepowershell-interactive
 Connect-AzAccount -Identity
```

Contoh ini tersambung menggunakan Managed Service Identity of myUserAssignedIdentity. Tambahkan identitas yang ditetapkan pengguna ke komputer virtual, lalu tersambung menggunakan ClientId identitas yang ditetapkan pengguna. Untuk informasi selengkapnya, [lihat Mengonfigurasi identitas terkelola untuk sumber daya Azure pada Azure VM](/active-directory/managed-identities-azure-resources/qs-configure-powershell-windows-vm).

```azurepowershell-interactive
$identity = Get-AzUserAssignedIdentity -ResourceGroupName 'myResourceGroup' -Name 'myUserAssignedIdentity'
Get-AzVM -ResourceGroupName contoso -Name testvm | Update-AzVM -IdentityType UserAssigned -IdentityId $identity.Id
Connect-AzAccount -Identity -AccountId $identity.ClientId # Run on the virtual machine

Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
yyyy-yyyy-yyyy-yyyy    Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

## <a name="sign-in-with-a-non-default-tenant-or-as-a-cloud-solution-provider-csp"></a>Masuk dengan penyewa non-default atau sebagai penyedia Penyedia Solusi Cloud (CSP)

Jika akun Anda terkait dengan lebih dari satu penyewa, masuk memerlukan `Tenant` parameter yang ditentukan saat menyambungkan. Parameter ini bekerja dengan metode masuk apa pun. Saat pembuatan log masuk, nilai parameter ini bisa berupa ID objek Azure dari penyewa (ID Penyewa) atau nama domain penyewa yang sepenuhnya memenuhi syarat.

Jika Anda adalah seorang [Penyedia Solusi Cloud (CSP),](https://azure.microsoft.com/offers/ms-azr-0145p/)nilai untuk `Tenant` parameter tersebut **harus** merupakan ID penyewa.

```azurepowershell-interactive
Connect-AzAccount -Tenant '00000000-0000-0000-0000-000000000000'
```

## <a name="sign-in-to-another-cloud"></a>Masuk ke Cloud lain

Lingkungan penawaran layanan awan Azure mematuhi hukum penanganan data kawasan. Untuk akun di awan regional, atur lingkungan ketika Anda masuk dengan `Environment` parameter. Parameter ini bekerja dengan metode masuk apa pun. Misalnya, jika akun Anda berada di Azure China 21Vianet:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

Perintah berikut ini berisi daftar lingkungan yang tersedia:

```azurepowershell-interactive
Get-AzEnvironment | Select-Object -Property Name
```
