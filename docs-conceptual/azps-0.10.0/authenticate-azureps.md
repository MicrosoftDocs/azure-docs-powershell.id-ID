---
title: Masuk dengan Azure PowerShell
description: Cara masuk dengan pengguna Azure PowerShell pengguna, prinsipal layanan, atau dengan identitas yang dikelola untuk sumber daya Azure.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 08/10/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 2cae54a8e8823b35cfcc9b985cb71e1c7cd78e34
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428012"
---
# <a name="sign-in-with-azure-powershell"></a>Masuk dengan Azure PowerShell

Azure PowerShell mendukung beberapa metode autentikasi. Cara termudah untuk memulai adalah dengan [Azure Cloud Shell,](/azure/cloud-shell/overview)yang secara otomatis mencatat Anda. Dengan instalasi lokal, Anda bisa masuk secara interaktif melalui browser Anda. Ketika menulis skrip untuk otomatisasi, pendekatan yang direkomendasikan adalah menggunakan [prinsipal layanan](create-azure-service-principal-azureps.md) dengan izin yang diperlukan. Jika Anda membatasi izin masuk sebanyak mungkin untuk kasus penggunaan, Anda membantu menjaga sumber daya Azure Anda tetap aman.

Setelah masuk, perintah dijalankan pada langganan default Anda. Untuk mengubah langganan aktif Anda selama satu sesi, gunakan cmdlet [Set-AzContext.](/powershell/module/az.accounts/set-azcontext) Untuk mengubah langganan default yang digunakan saat masuk dengan Azure PowerShell, gunakan [Set-AzDefault](/powershell/module/az.accounts/set-azdefault).

> [!IMPORTANT]
>
> Kredensial Dibagikan di antara beberapa sesi PowerShell selama Anda tetap masuk.
> Untuk informasi selengkapnya, lihat artikel tentang [Kredensial Tetap.](context-persistence.md)

## <a name="sign-in-interactively"></a>Masuk secara interaktif

Untuk masuk secara interaktif, gunakan cmdlet [Koneksi-AzAccount.](/powershell/module/az.accounts/connect-azaccount)

```azurepowershell-interactive
Connect-AzAccount
```

Saat dijalankan, cmdlet ini akan menyajikan string token. Untuk masuk, salin string ini dan tempelkan https://microsoft.com/devicelogin ke dalam browser. Sesi PowerShell Anda akan diautentikasi untuk tersambung ke Azure.

> [!IMPORTANT]
>
> Otorisasi kredensial nama pengguna/kata sandi telah dihapus Azure PowerShell karena perubahan dalam implementasi otorisasi Direktori Aktif dan masalah keamanan.
> Jika Anda menggunakan otorisasi kredensial untuk tujuan otomatisasi, sebagai [gantinya buat prinsipal layanan](create-azure-service-principal-azureps.md).

## <a name="sign-in-with-a-service-principal"></a>Masuk dengan prinsipal layanan <a name="sp-signin"/>

Prinsipal layanan adalah akun Azure yang tidak interaktif. Seperti akun pengguna lain, izin mereka dikelola dengan Azure Active Directory. Dengan memberikan izin yang diperlukan hanya prinsipal layanan, skrip otomatisasi Anda tetap aman.

Untuk mempelajari cara membuat prinsipal layanan untuk digunakan dengan Azure PowerShell, lihat [Membuat prinsipal layanan Azure dengan Azure PowerShell](create-azure-service-principal-azureps.md).

Untuk masuk dengan prinsipal layanan, gunakan `-ServicePrincipal` argumen dengan `Connect-AzAccount` cmdlet. Anda juga akan memerlukan ID aplikasi prinsipal layanan, kredensial masuk, dan ID penyewa terkait dengan prinsipal layanan. Cara Anda masuk dengan prinsipal layanan akan bergantung pada konfigurasi untuk autentikasi berbasis kata sandi atau berbasis sertifikat.

### <a name="password-based-authentication"></a>Autentikasi berbasis kata sandi

Untuk mendapatkan kredensial prinsipal layanan sebagai objek yang tepat, gunakan cmdlet [Get-Credential.](/powershell/module/microsoft.powershell.security/get-credential) Cmdlet ini akan meminta nama pengguna dan kata sandi. Gunakan ID prinsipal layanan untuk nama pengguna.

```azurepowershell-interactive
$pscredential = Get-Credential
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

Untuk skenario otomatisasi, Anda perlu membuat kredensial dari nama pengguna dan string aman:

```azurepowershell-interactive
$passwd = ConvertTo-SecureString <use a secure password here> -AsPlainText -Force
$pscredential = New-Object System.Management.Automation.PSCredential('service principal name/id', $passwd)
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

Pastikan Anda menggunakan praktik penyimpanan kata sandi yang bagus ketika mengotomatiskan koneksi prinsipal layanan.

### <a name="certificate-based-authentication"></a>Autentikasi berbasis sertifikat

Autentikasi berbasis sertifikat mengharuskan Azure PowerShell mengambil informasi dari penyimpanan sertifikat lokal berdasarkan pada cetakan sertifikat.

```azurepowershell-interactive
Connect-AzAccount -ApplicationId $appId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

Ketika menggunakan prinsipal layanan dan bukan aplikasi terdaftar, tambahkan argumen dan sediakan ID Aplikasi prinsipal `-ServicePrincipal` layanan `-ApplicationId` sebagai nilai parameter.

```azurepowershell-interactive
Connect-AzAccount -ServicePrincipal -ApplicationId $servicePrincipalId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

Di PowerShell 5.1, penyimpanan sertifikat dapat dikelola dan diperiksa dengan [modul PKI.](/powershell/module/pki) Untuk PowerShell Core 6.x dan yang lebih baru, prosesnya lebih rumit. Skrip berikut ini memperlihatkan cara mengimpor sertifikat yang sudah ada ke penyimpanan sertifikat yang dapat diakses oleh PowerShell.

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

Perintah ini tersambung menggunakan identitas terkelola lingkungan host. Misalnya, jika dijalankan di VirtualMachine dengan Identitas Layanan Terkelola yang ditetapkan, hal ini memungkinkan kode untuk masuk menggunakan identitas yang ditetapkan tersebut.

```azurepowershell-interactive
 Connect-AzAccount -Identity
```

## <a name="sign-in-with-a-non-default-tenant-or-as-a-cloud-solution-provider-csp"></a>Masuk dengan penyewa non-default atau sebagai penyedia layanan Penyedia Solusi Cloud (CSP)

Jika akun Anda terkait dengan lebih dari satu penyewa, masuk memerlukan penggunaan `-Tenant` parameter saat menyambungkan. Parameter ini akan bekerja dengan metode masuk apa pun. Saat pembuatan log masuk, nilai parameter ini bisa berupa ID objek Azure dari penyewa (ID Penyewa) atau nama domain penyewa yang sepenuhnya memenuhi syarat.

Jika Merupakan pelanggan Penyedia Solusi Cloud [(CSP),](https://azure.microsoft.com/offers/ms-azr-0145p/)nilai `-Tenant` harus **merupakan** ID penyewa.

```azurepowershell-interactive
Connect-AzAccount -Tenant 'xxxx-xxxx-xxxx-xxxx'
```

## <a name="sign-in-to-another-cloud"></a>Masuk ke Cloud lain

Lingkungan penawaran layanan awan Azure mematuhi hukum penanganan data kawasan.
Untuk akun di awan regional, setel lingkungan ketika Anda masuk dengan `-Environment` argumen.
Parameter ini akan bekerja dengan metode masuk apa pun. Misalnya, jika akun Anda berada di awan Tiongkok:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

Perintah berikut ini berisi daftar lingkungan yang tersedia:

```azurepowershell-interactive
Get-AzEnvironment | Select-Object Name
```
