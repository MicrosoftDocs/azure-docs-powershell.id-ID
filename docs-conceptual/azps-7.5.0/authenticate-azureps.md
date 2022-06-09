---
description: Cara masuk dengan Azure PowerShell sebagai pengguna, perwakilan layanan, atau dengan identitas terkelola untuk sumber daya Azure.
ms.custom: devx-track-azurepowershell
ms.date: 06/07/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Masuk dengan Azure PowerShell
ms.openlocfilehash: 508ce4192a9fc43f05a33b6a6571a98b0bd9d685
ms.sourcegitcommit: 10639f1badb6c7312556e6dcfa0f38f5d33a4b9c
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/09/2022
ms.locfileid: "146191448"
---
# <a name="sign-in-with-azure-powershell"></a>Masuk dengan Azure PowerShell

Azure PowerShell mendukung beberapa metode autentikasi. Cara termudah untuk memulai adalah dengan [Azure Cloud Shell](/azure/cloud-shell/overview), yang secara otomatis memasukkan Anda. Dengan penginstalan lokal, Anda dapat masuk secara interaktif melalui browser Anda. Saat menulis skrip untuk otomatisasi, pendekatan yang disarankan adalah menggunakan [perwakilan layanan](create-azure-service-principal-azureps.md) dengan izin yang diperlukan. Saat Anda membatasi izin masuk sebanyak mungkin untuk kasus penggunaan Anda, Anda membantu menjaga sumber daya Azure Anda tetap aman.

Awalnya, Anda masuk ke langganan pertama yang kembali Azure jika Anda memiliki akses ke lebih dari satu langganan. Perintah dijalankan terhadap langganan ini secara default. Untuk mengubah langganan aktif Anda untuk sesi, gunakan cmdlet [Set-AzContext](/powershell/module/az.accounts/set-azcontext). Untuk mengubah langganan aktif Anda dan mempertahankannya di antara sesi pada sistem yang sama, gunakan cmdlet [Select-AzContext](/powershell/module/az.accounts/select-azcontext).

> [!IMPORTANT]
> Info masuk Anda dibagikan di antara beberapa sesi PowerShell selama Anda tetap masuk.
> Untuk informasi selengkapnya, lihat [Objek konteks Azure PowerShell](context-persistence.md).

## <a name="sign-in-interactively"></a>Masuk secara interaktif

Untuk masuk secara interaktif, gunakan cmdlet [Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount).

```azurepowershell
Connect-AzAccount
```

Cmdlet ini menyajikan permintaan masuk berbasis browser interaktif secara default.

Gunakan cmdlet [Get-AzContext](/powershell/module/az.accounts/get-azcontext) untuk menyimpan ID penyewa Anda dalam variabel yang akan digunakan di dua bagian berikutnya dari artikel ini.

```azurepowershell-interactive
$tenantId = (Get-AzContext).Tenant.Id
```

## <a name="device-code-authentication"></a>Autentikasi kode perangkat

Anda dapat menentukan `UseDeviceAuthentication` parameter untuk menggunakan autentikasi kode perangkat alih-alih kontrol browser.

```azurepowershell-interactive
Connect-AzAccount -UseDeviceAuthentication
```

## <a name="sign-in-with-a-service-principal"></a>Masuk dengan perwakilan layanan

Perwakilan layanan adalah akun Azure non-interaktif. Seperti akun pengguna lainnya, izinnya dikelola dengan Azure Active Directory. Dengan memberikan perwakilan layanan hanya izin yang dibutuhkan, skrip otomatisasi Anda tetap aman.

Untuk mempelajari cara membuat perwakilan layanan untuk digunakan dengan Azure PowerShell, lihat [Membuat perwakilan layanan Azure dengan Azure PowerShell](create-azure-service-principal-azureps.md).

Untuk masuk dengan perwakilan layanan, gunakan parameter `ServicePrincipal` cmdlet `Connect-AzAccount`. Anda juga memerlukan ID aplikasi perwakilan layanan, info masuk, dan mengaitkan ID penyewa dengan perwakilan layanan. Cara Anda masuk dengan perwakilan layanan tergantung pada apakah itu dikonfigurasi untuk autentikasi berbasis kata sandi atau berbasis sertifikat.

### <a name="password-based-authentication"></a>Autentikasi berbasis kata sandi

Buat perwakilan layanan untuk digunakan dalam contoh di bagian ini. Untuk informasi selengkapnya tentang membuat perwakilan layanan, kunjungi [Buat perwakilan layanan Azure dengan Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps).

```azurepowershell-interactive
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName
```

Untuk mendapatkan info masuk perwakilan layanan sebagai objek yang sesuai, gunakan cmdlet [Get-Credential](/powershell/module/microsoft.powershell.security/get-credential). Cmdlet ini menyajikan perintah untuk nama pengguna dan kata sandi. Gunakan perwakilan layanan `applicationID` untuk nama pengguna dan ubah `secret` menjadi teks biasa untuk kata sandi.

```azurepowershell-interactive
# Retrieve the plain text password for use with `Get-Credential` in the next command.
$sp.PasswordCredentials.SecretText

$pscredential = Get-Credential -UserName $sp.AppId
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

Untuk skenario otomatisasi, Anda perlu membuat info masuk dari perwakilan layanan `AppId` dan `SecretText`:

```azurepowershell-interactive
$SecureStringPwd = $sp.PasswordCredentials.SecretText | ConvertTo-SecureString -AsPlainText -Force
$pscredential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $sp.AppId, $SecureStringPwd
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

Pastikan Anda menggunakan praktik penyimpanan kata sandi yang baik saat mengotomatiskan koneksi perwakilan layanan.

### <a name="certificate-based-authentication"></a>Autentikasi berbasis sertifikat

Autentikasi berbasis sertifikat mengharuskan Azure PowerShell dapat mengambil informasi dari penyimpanan sertifikat lokal berdasarkan thumbprint sertifikat.

```azurepowershell-interactive
Connect-AzAccount -ApplicationId $appId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

Saat menggunakan perwakilan layanan alih-alih aplikasi terdaftar, tentukan parameter `ServicePrincipal` dan berikan ID Aplikasi perwakilan layanan sebagai nilai parameter `-ApplicationId`.

```azurepowershell-interactive
Connect-AzAccount -ServicePrincipal -ApplicationId $servicePrincipalId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

Di PowerShell 5.1, penyimpanan sertifikat dapat dikelola dan diperiksa dengan modul [PKI](/powershell/module/pki). Untuk PowerShell 6.x dan yang lebih baru, prosesnya lebih rumit.
Skrip berikut menunjukkan kepada Anda cara mengimpor sertifikat yang ada ke penyimpanan sertifikat yang dapat diakses oleh PowerShell.

#### <a name="import-a-certificate-in-powershell-51"></a>Mengimpor sertifikat di PowerShell 5.1

```powershell-interactive
# Import a PFX
$credentials = Get-Credential -Message 'Provide PFX private key password'
Import-PfxCertificate -FilePath <path to certificate> -Password $credentials.Password -CertStoreLocation cert:\CurrentUser\My
```

#### <a name="import-a-certificate-in-powershell-core-6x-and-later"></a>Mengimpor sertifikat di PowerShell Core 6.x dan versi lebih baru

```powershell-interactive
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

## <a name="sign-in-using-a-managed-identity"></a>Masuk dengan identitas terkelola

Identitas terkelola juga merupakan fitur Azure Active Directory. Identitas terkelola adalah perwakilan layanan yang ditetapkan ke sumber daya yang berjalan di Azure. Anda dapat menggunakan perwakilan layanan identitas terkelola untuk masuk, dan memperoleh token akses khusus aplikasi untuk mengakses sumber daya lain. Identitas terkelola hanya tersedia pada sumber daya yang berjalan di cloud Azure.

Contoh ini menghubungkan menggunakan identitas terkelola dari lingkungan host. Misalnya, jika dijalankan pada VirtualMachine dengan Identitas Layanan Terkelola yang ditetapkan, ini memungkinkan kode untuk masuk menggunakan identitas yang ditetapkan tersebut.

```azurepowershell-interactive
 Connect-AzAccount -Identity
```

Contoh ini terhubung menggunakan Identitas Layanan Terkelola myUserAssignedIdentity. Ini menambahkan identitas yang ditetapkan pengguna ke mesin virtual, lalu menghubungkan menggunakan ClientId dari identitas yang ditetapkan pengguna. Untuk informasi selengkapnya, lihat [Mengonfigurasi identitas terkelola untuk sumber daya Azure di Azure VM](/azure/active-directory/managed-identities-azure-resources/qs-configure-powershell-windows-vm).

```azurepowershell-interactive
$identity = Get-AzUserAssignedIdentity -ResourceGroupName 'myResourceGroup' -Name 'myUserAssignedIdentity'
Get-AzVM -ResourceGroupName contoso -Name testvm | Update-AzVM -IdentityType UserAssigned -IdentityId $identity.Id
Connect-AzAccount -Identity -AccountId $identity.ClientId # Run on the virtual machine

Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
yyyy-yyyy-yyyy-yyyy    Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

## <a name="sign-in-with-a-non-default-tenant-or-as-a-cloud-solution-provider-csp"></a>Masuk dengan penyewa non-default atau sebagai Penyedia Solusi Cloud (CSP)

Jika akun Anda dikaitkan dengan lebih dari satu penyewa, proses masuk memerlukan parameter `Tenant` yang akan ditentukan saat menyambungkan. Parameter ini bekerja dengan metode masuk apa pun. Saat masuk, nilai parameter ini dapat berupa ID objek Azure dari penyewa (ID Penyewa) atau nama domain penyewa yang sepenuhnya memenuhi syarat.

Jika Anda seorang [Penyedia Solusi Cloud (CSP)](https://azure.microsoft.com/offers/ms-azr-0145p/), nilai untuk parameter `Tenant` **harus** id penyewa.

```azurepowershell-interactive
Connect-AzAccount -Tenant '00000000-0000-0000-0000-000000000000'
```

## <a name="sign-in-to-another-cloud"></a>Masuk ke Cloud lain

Layanan cloud Azure menawarkan lingkungan yang sesuai dengan undang-undang penanganan data regional. Untuk akun di cloud regional, atur lingkungan saat Anda masuk dengan parameter `Environment`. Parameter ini bekerja dengan metode masuk apa pun. Misalnya, jika akun Anda berada di Azure Tiongkok 21Vianet:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

Perintah berikut mendapatkan daftar lingkungan yang tersedia:

```azurepowershell-interactive
Get-AzEnvironment | Select-Object -Property Name
```
