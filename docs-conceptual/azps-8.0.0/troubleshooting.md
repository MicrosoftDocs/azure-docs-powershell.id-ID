---
description: Memecahkan masalah modul Azure Az PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 06/09/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Pemecahan masalah modul Azure Az PowerShell
ms.openlocfilehash: e5072c11ccafccc612712c21e48c370ba7b8c77c
ms.sourcegitcommit: 37440f9593703a5e400f8052b026691982899953
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/11/2022
ms.locfileid: "146259754"
---
# <a name="troubleshooting-the-azure-az-powershell-module"></a>Pemecahan masalah modul Azure Az PowerShell

## <a name="enable-debug-logging"></a>Mengaktifkan pengelogan debug

Salah satu langkah pertama yang harus Anda ambil dalam memecahkan masalah dengan modul Azure Az PowerShell adalah mengaktifkan pengelogan debug.

Untuk mengaktifkan pengelogan debug berdasarkan perintah, tentukan parameter **Debug**.

```azurepowershell-interactive
Get-AzResource -Name 'DoesNotExist' -Debug
```

Untuk mengaktifkan pengelogan debug untuk seluruh sesi PowerShell, Anda menetapkan nilai variabel **DebugPreference** menjadi `Continue`.

```powershell-interactive
$DebugPreference = 'Continue'
```

## <a name="object-reference-not-set-to-an-instance-of-an-object"></a>Referensi objek tidak diatur ke instans objek

Pesan "_referensi objek tidak diatur ke instans objek_" berarti Anda merujuk ke objek yang null atau sumber daya Azure yang tidak ada atau Anda tidak memiliki izin untuk mengakses.

```azurepowershell
$resourceId =  '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/<resource-group-name>/providers/Microsoft.Web/sites/<webapp-name>/privateEndpointConnections/<endpoint-name>'
Get-AzPrivateEndpointConnection -ResourceId $resourceId
```

```Output
Get-AzPrivateEndpointConnection: Object reference not set to an instance of an object.
```

Anda dapat menggunakan `Get-AzResource` cmdlet untuk memverifikasi bahwa sumber daya Azure yang ditentukan ada.

```azurepowershell
Get-AzResource -ResourceId $resourceId
```

## <a name="permission-issues-with-azad-cmdlets"></a>Masalah izin dengan cmdlet AzAD

[Referensi izin Microsoft Graph](/graph/permissions-reference)

## <a name="microsoft-graph-query-parameters"></a>Parameter Kueri Microsoft Graph

Cmdlet AzAd pada Az.Resources kini mendukung [parameter kueri](/graph/query-parameters) dan [parameter kueri pencarian](/graph/search-query-parameter). Untuk detail tentang sintaks, lihat tautan yang direferensikan sebelumnya.

## <a name="get-azadgroupmember-doesnt-return-service-principals"></a>Get-AzAdGroupMember tidak mengembalikan perwakilan layanan

Karena keterbatasan dengan API Graph saat ini, perwakilan layanan tidak dikembalikan oleh [Get-AzAdGroupMember](/powershell/module/az.resources/get-azadgroupmember) di Az 7.x. Sebagai solusinya, [Invoke-AzRestMethod](/powershell/module/az.accounts/invoke-azrestmethod) dapat digunakan dengan versi beta dari API Microsoft Graph.

Contoh berikut ini memerlukan modul Az PowerShell. Ganti `myGroupName` di baris pertama dengan nama grup Anda.

```azurepowershell-interactive
$Group = Get-AzADGroup -DisplayName myGroupName
((Invoke-AzRestMethod -Uri "https://graph.microsoft.com/beta/groups/$($Group.id)/members").Content |
  ConvertFrom-Json).value |
  Select-Object -Property DisplayName, Id, @{label='OdataType';expression={$_.'@odata.type'}}
```

## <a name="command-found-but-could-not-be-loaded"></a>Perintah ditemukan namun tidak dapat dimuat

Pesan berikut dikembalikan oleh PowerShell saat Anda mencoba menjalankan salah satu perintah Az PowerShell.

```Output
Connect-AzAccount: The 'Connect-AzAccount' command was found in the module 'Az.Accounts', but the module could not be loaded. For more information, run 'Import-Module Az.Accounts'.
```

Pesan ini muncul ketika Anda menginstal modul Az dan AzureRM PowerShell yang diinstal di sistem berbasis Windows yang sama dan ada di [$env:PSModulePath](/powershell/module/microsoft.powershell.core/about/about_psmodulepath) untuk versi PowerShell yang sama.

> [!IMPORTANT]
> Saat AzureRM diinstal dalam cakupan `AllUsers` Windows PowerShell, AzureRM diinstal di lokasi yang merupakan bagian dari `$env:PSModulePath` untuk PowerShell 7. Ini tidak didukung karena konflik antara modul AzureRM dan Az PowerShell.

Az dan AzureRM dapat hidup berdampingan pada sistem Windows yang sama, tetapi hanya jika AzureRM diinstal dalam cakupan `CurrentUser` Windows PowerShell dan Az yang diinstal di PowerShell 7. Untuk informasi selengkapnya, lihat [Menginstal modul Azure PowerShell](/powershell/azure/install-az-ps).

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## <a name="on-macos-an-error-returns-when-keychain-authorization-fails"></a>Di MacOS, kesalahan akan kembali terjadi saat otorisasi KeyChain gagal

Saat menjalankan Azure PowerShell di MacOS, Anda mungkin menemukan pesan kesalahan saat mencoba masuk ke akun Azure Anda dari sesi PowerShell.

```txt
DeviceCodeCredential authentication failed: Persistence check failed. Reason: KeyChain authorization/authentication failed. .Error code: -25293. OS error code -25293.
```

Sebagai solusi untuk masalah ini, Anda dapat menonaktifkan penyimpanan kredensial antar sesi dengan menjalankan perintah berikut. Namun, setelah membuat perubahan ini, Anda harus menjalankan `Connect-AzAccount` setiap kali memulai sesi PowerShell baru.

```azurepowershell
Disable-AzContextAutosave
```

## <a name="service-principal-identifieruri-verified-domain-error"></a>Kesalahan domain terverifikasi IdentifierUri Perwakilan Layanan

Kesalahan: _Nilai properti IdentifierUris harus menggunakan domain terverifikasi dari organisasi atau subdomainnya_ ditampilkan saat menjalankan `New-AzADServicePrincipal` atau `New-AzADApplication`.

Karena Azure Active Directory melanggar perubahan yang mengharuskan [AppId Uri dalam aplikasi penyewa tunggal untuk mewajibkan penggunaan skema default atau domain terverifikasi](/azure/active-directory/develop/reference-breaking-changes#appid-uri-in-single-tenant-applications-will-require-use-of-default-scheme-or-verified-domains), Anda harus meningkatkan modul [Az.Resources](https://www.powershellgallery.com/packages/Az.Resources) ke versi 4.1.0 atau yang lebih baru untuk terus menggunakan cmdlet `New-AzADServicePrincipal` atau `New-AzADApplication`.

Anda juga dapat meningkatkan ke modul Az PowerShell versi 6.0 atau lebih baru.

### <a name="timeline"></a>Garis waktu

Persyaratan akan berlaku mulai 10/15/2021.

### <a name="impacted-versions"></a>Versi yang terpengaruh

Versi Azure PowerShell berikut dipengaruhi oleh perubahan yang melanggar AzureAD:

- Modul Az.Resources PowerShell versi 3.5.1-preview atau lebih rendah.
- Modul Az PowerShell versi 5.9.0 atau yang lebih rendah.

Jika Anda masih mengalami masalah setelah peningkatan, jangan ragu untuk membuka [masalah](https://github.com/Azure/azure-powershell/issues/new?assignees=&labels=needs-triage&template=az-module-bug-report.md&title=).

### <a name="workaround"></a>Solusi Sementara

Jika Anda tidak dapat meningkatkan ke modul PowerShell yang dijelaskan di atas, Anda dapat mengikuti langkah-langkah tersebut saat membuat perwakilan layanan:

- Bila perlu, [tambahkan nama domain kustom Anda menggunakan portal Azure Active Directory](/azure/active-directory/fundamentals/add-custom-domain)
- Membuat aplikasi dengan IdentifierUri yang diterima
- Membuat perwakilan layanan yang merujuk aplikasi ini
