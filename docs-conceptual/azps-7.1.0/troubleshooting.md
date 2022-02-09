---
title: Pemecahan masalah modul Azure Az PowerShell
description: Pemecahan masalah modul Azure Az PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/04/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 0bef4da70736a984fb200fa6fd414e644d177544
ms.sourcegitcommit: e0271fba109b9a6cf263676f7a4c4b84922adbc7
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/04/2022
ms.locfileid: "138025248"
---
# <a name="troubleshooting-the-azure-az-powershell-module"></a>Pemecahan masalah modul Azure Az PowerShell

## <a name="enable-debug-logging"></a>Mengaktifkan pengelogan debug

Salah satu langkah pertama yang harus Anda ambil dalam memecahkan masalah dengan modul Azure Az PowerShell adalah mengaktifkan pembuatan debug.

Untuk mengaktifkan pembuatan log debug berdasarkan per perintah, tentukan parameter **Debug** .

```azurepowershell-interactive
Get-AzResource -Name 'DoesNotExist' -Debug
```

Untuk mengaktifkan pembuatan log debug untuk seluruh sesi PowerShell, Anda menetapkan nilai variabel **DebugPreference** ke `Continue`.

```azurepowershell-interactive
$DebugPreference = 'Continue'
```

## <a name="permission-issues-with-azad-cmdlets"></a>Masalah izin dengan cmdlet AzAD

[Referensi izin Graph Microsoft](/graph/permissions-reference)

## <a name="microsoft-graph-query-parameters"></a>Parameter kueri Graph Microsoft

Cmdlet AzAd di bawah Az.Resources sekarang mendukung [parameter kueri](/graph/query-parameters) dan [parameter kueri penelusuran](/graph/search-query-parameter). Untuk detail tentang sintaks, lihat tautan yang direferensikan sebelumnya.

## <a name="get-azadgroupmember-doesnt-return-service-principals"></a>Get-AzAdGroupMember tidak mengembalikan prinsipal layanan

Karena keterbatasan dengan API Graph saat ini, prinsipal layanan tidak dikembalikan oleh [Get-AzAdGroupMember](/powershell/module/az.resources/get-azadgroupmember) di Az 7.x. Sebagai solusi, [Invoke-AzRestMethod](/powershell/module/az.accounts/invoke-azrestmethod) dapat digunakan dengan versi beta dari Microsoft Graph API.

Contoh berikut memerlukan modul Az PowerShell. Ganti `myGroupName` di baris pertama dengan nama grup Anda.

```azurepowershell-interactive
$Group = Get-AzADGroup -DisplayName myGroupName
((Invoke-AzRestMethod -Uri "https://graph.microsoft.com/beta/groups/$($Group.id)/members").Content |
  ConvertFrom-Json).value |
  Select-Object -Property DisplayName, Id, @{label='OdataType';expression={$_.'@odata.type'}}
```

## <a name="command-found-but-could-not-be-loaded"></a>Perintah ditemukan tetapi tidak dapat dimuat

Pesan berikut dikembalikan oleh PowerShell ketika Anda mencoba menjalankan salah satu perintah Az PowerShell.

```Output
Connect-AzAccount: The 'Connect-AzAccount' command was found in the module 'Az.Accounts', but the module could not be loaded. For more information, run 'Import-Module Az.Accounts'.
```

Pesan ini terjadi ketika Anda memiliki modul PowerShell Az dan AzureRM yang diinstal pada sistem berbasis Windows yang sama dan mereka ada di [$env: PSModulePath](/powershell/module/microsoft.powershell.core/about/about_psmodulepath) untuk versi PowerShell yang sama.

> [!IMPORTANT]
> Ketika AzureRM diinstal dalam `AllUsers` lingkup Windows PowerShell, itu diinstal di lokasi yang merupakan bagian dari `$env:PSModulePath` untuk PowerShell 7. Hal ini tidak didukung karena konflik antara modul AzureRM dan Az PowerShell.

Baik Az dan AzureRM dapat hidup berdampingan pada sistem Windows yang sama, tetapi hanya jika AzureRM diinstal dalam `CurrentUser` lingkup Windows PowerShell dan Az diinstal di PowerShell 7. Untuk informasi selengkapnya, lihat [Menginstal modul Azure PowerShell](/powershell/azure/install-az-ps).

## <a name="on-macos-an-error-returns-when-keychain-authorization-fails"></a>Di MacOS, kesalahan kembali saat otorisasi KeyChain gagal

Saat menjalankan Azure PowerShell di MacOS, Anda mungkin menemukan pesan kesalahan saat mencoba masuk ke akun Azure dari sesi PowerShell.

```txt
DeviceCodeCredential authentication failed: Persistence check failed. Reason: KeyChain authorization/authentication failed. .Error code: -25293. OS error code -25293.
```

Sebagai solusi untuk masalah ini, Anda dapat menonaktifkan menyimpan kredensial antar sesi dengan menjalankan perintah berikut. Namun, setelah membuat perubahan ini, Anda harus berlari `Connect-AzAccount` setiap kali memulai sesi PowerShell baru.

```powershell
Disable-AzContextAutosave
```

## <a name="service-principal-identifieruri-verified-domain-error"></a>Service Principal IdentifierUri kesalahan domain terverifikasi

Kesalahan: _Nilai properti identifierUris harus menggunakan domain terverifikasi dari organisasi atau subdomainnya_ ditampilkan saat menjalankan `New-AzADServicePrincipal` atau `New-AzADApplication`.

Karena perubahan Azure Active Directory melanggar yang mengharuskan [AppId Uri dalam aplikasi penyewa tunggal untuk memerlukan penggunaan skema default atau domain terverifikasi](/active-directory/develop/reference-breaking-changes#appid-uri-in-single-tenant-applications-will-require-use-of-default-scheme-or-verified-domains) Anda harus meng-upgrade modul [Az.Resources](https://www.powershellgallery.com/packages/Az.Resources) ke versi 4.1.0 atau yang lebih baru untuk terus menggunakan `New-AzADServicePrincipal` atau `New-AzADApplication` cmdlets.

Anda juga dapat meng-upgrade ke modul Az PowerShell versi 6.0 atau lebih besar.

### <a name="timeline"></a>Garis waktu

Persyaratan akan berlaku mulai 10/15/2021.

### <a name="impacted-versions"></a>Versi yang terpengaruh

Versi Azure PowerShell berikut dipengaruhi oleh perubahan melanggar AzureAD:

- Modul Az.Resources PowerShell versi 3.5.1-preview atau lebih rendah.
- Az Modul PowerShell versi 5.9.0 atau lebih rendah.

Jika Anda masih mengalami masalah setelah meningkatkan, jangan ragu untuk membuka [masalah](https://github.com/Azure/azure-powershell/issues/new?assignees=&labels=needs-triage&template=az-module-bug-report.md&title=).

### <a name="workaround"></a>Solusi Sementara

Jika Anda tidak dapat meng-upgrade ke modul PowerShell yang dijelaskan di atas, Anda dapat mengikuti langkah-langkah tersebut saat membuat prinsip layanan:

- Jika diperlukan, [tambahkan nama domain kustom Anda menggunakan portal Azure Active Directory](/active-directory/fundamentals/add-custom-domain)
- Membuat aplikasi dengan IdentifierUri yang diterima
- Membuat prinsip layanan yang merujuk aplikasi ini
