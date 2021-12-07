---
title: Memecahkan masalah modul PowerShell Azure Az
description: Memecahkan masalah modul PowerShell Azure Az.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/02/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: d05fa1fa702a8b09fc4139850e37a9654abf3155
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "133988766"
---
# <a name="troubleshooting-the-azure-az-powershell-module"></a>Memecahkan masalah modul PowerShell Azure Az

## <a name="enable-debug-logging"></a>Mengaktifkan pembuatan log debug

Salah satu langkah pertama yang harus Anda lakukan dalam memecahkan masalah dengan modul PowerShell Azure Az adalah mengaktifkan pembuatan log debug.

Untuk mengaktifkan pembuatan log debug pada tiap basis perintah, tentukan parameter **Debug.**

```azurepowershell-interactive
Get-AzResource -Name 'DoesNotExist' -Debug
```

Untuk mengaktifkan pembuatan log debug untuk seluruh sesi PowerShell, Anda mengatur nilai variabel **DebugPreference** ke `Continue` .

```azurepowershell-interactive
$DebugPreference = 'Continue'
```

## <a name="command-found-but-could-not-be-loaded"></a>Perintah ditemukan tetapi tidak dapat dimuat

Pesan berikut ini dikembalikan oleh PowerShell ketika Anda mencoba menjalankan perintah Az PowerShell apa pun.

```Output
Connect-AzAccount: The 'Connect-AzAccount' command was found in the module 'Az.Accounts', but the module could not be loaded. For more information, run 'Import-Module Az.Accounts'.
```

Pesan ini muncul jika modul PowerShell Az dan AzureRM telah terinstal pada sistem berbasis Windows yang sama dan terdapat di [$env:PSModulePath](/powershell/module/microsoft.powershell.core/about/about_psmodulepath) untuk versi PowerShell yang sama.

> [!IMPORTANT]
> Ketika AzureRM diinstal dalam lingkup Windows PowerShell, AzureRM akan diinstal di lokasi yang menjadi bagian dari `AllUsers` `$env:PSModulePath` PowerShell 7. Hal ini tidak didukung karena adanya konflik antara modul AzureRM dan Az PowerShell.

Az dan AzureRM mungkin berdampingan pada sistem Windows yang sama, tetapi hanya jika AzureRM diinstal dalam lingkup Windows PowerShell dan Az yang diinstal di `CurrentUser` PowerShell 7. Untuk informasi selengkapnya, [lihat Menginstal modul PowerShell Azure Az](/powershell/azure/install-az-ps).

## <a name="on-macos-an-error-returns-when-keychain-authorization-fails"></a>Di MacOS, kesalahan akan muncul ketika otorisasi KeyChain gagal

Ketika menjalankan Azure PowerShell Di MacOS, Anda mungkin mengalami pesan kesalahan ketika mencoba masuk ke akun Azure dari sesi PowerShell.

```txt
DeviceCodeCredential authentication failed: Persistence check failed. Reason: KeyChain authorization/authentication failed. .Error code: -25293. OS error code -25293.
```

Sebagai solusi untuk masalah ini, Anda dapat menonaktifkan penyimpanan kredensial antar sesi dengan menjalankan perintah berikut ini. Setelah membuat perubahan ini, Anda perlu menjalankan `Connect-AzAccount` setiap kali Anda memulai sesi PowerShell baru.

```powershell
Disable-AzContextAutosave
```

## <a name="service-principal-identifieruri-verified-domain-error"></a>Kesalahan domain yang diverifikasi Pengidentifikasi Prinsipal Layanan

Kesalahan: _Nilai properti pengidentifikasiUris harus menggunakan domain_ terverifikasi organisasi atau subdomainnya ditampilkan saat berjalan atau `New-AzADServicePrincipal` `New-AzADApplication` .

Karena perubahan Azure Active Directory yang mengharuskan [AppId Uri](/active-directory/develop/reference-breaking-changes#appid-uri-in-single-tenant-applications-will-require-use-of-default-scheme-or-verified-domains) dalam aplikasi penyewa tunggal untuk memerlukan penggunaan skema default atau domain terverifikasi, Anda harus memutakhirkan modul [Az.Resources](https://www.powershellgallery.com/packages/Az.Resources) ke versi 4.1.0 atau yang lebih baru untuk terus menggunakan atau `New-AzADServicePrincipal` `New-AzADApplication` cmdlet.

Anda juga bisa memutakhirkan ke modul Az PowerShell versi 6.0 atau yang lebih besar.

### <a name="timeline"></a>Garis Waktu

Persyaratan tersebut akan berlaku mulai 15/10/2021.

### <a name="impacted-versions"></a>Versi yang terkena dampak

Versi pembaruan berikut Azure PowerShell terkena dampak perubahan pembaruan AzureAD:

- Az.Resources PowerShell module version 3.5.1-preview or lesser.
- Az PowerShell module versi 5.9.0 atau yang lebih kecil.

Jika Anda masih mengalami masalah setelah pemutakhiran, jangan ragu untuk membuka [masalah.](https://github.com/Azure/azure-powershell/issues/new?assignees=&labels=needs-triage&template=az-module-bug-report.md&title=)

### <a name="workaround"></a>Solusi

Jika tidak dapat memutakhirkan ke modul PowerShell yang dijelaskan di atas, Anda dapat mengikuti langkah-langkah tersebut saat membuat prinsipal layanan:

- Jika diperlukan, [tambahkan nama domain kustom Anda menggunakan portal Azure Active Directory](/active-directory/fundamentals/add-custom-domain)
- Membuat aplikasi dengan Pengidentifikasi Yang Diterima
- Membuat pokok layanan yang merujuk pada aplikasi ini
