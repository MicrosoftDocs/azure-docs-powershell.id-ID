---
title: Menghapus instalan Azure PowerShell
description: Cara melakukan penghapusan instalan Azure PowerShell secara menyeluruh
ms.date: 06/10/2019
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 17a9b604da84f131c434e3001732a34f7d620fbd
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427986"
---
# <a name="uninstall-the-azure-powershell-module"></a>Menghapus instalan modul Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini menjelaskan cara menghapus instalan versi Azure PowerShell lama, atau menghapus seluruhnya dari sistem Anda. Jika Anda memutuskan untuk menghapus instalan Azure PowerShell sepenuhnya, harap berikan beberapa umpan balik kepada kami melalui cmdlet [Send-Feedback](/powershell/module/azurerm.profile/send-feedback).
Jika Anda menemukan bug, kami akan menghargainya jika Anda [mengajukan masalah GitHub](https://github.com/azure/azure-powershell/issues).

## <a name="uninstall-msi-or-web-platform-installer"></a>Menghapus instalan MSI atau Penginstal Platform Web

Jika Anda menginstal Azure PowerShell menggunakan paket MSI atau Penginstal Platform Web, Anda harus menghapus instalan melalui sistem Windows bukan PowerShell.

| Platform | Instruksi |
|----------|--------------|
| Windows 10 | Mulai > Pengaturan > Aplikasi |
| Windows 7 </br>Windows 8 | Mulai > Panel Kontrol > Program > Hapus instalan program |

Setelah tiba di layar ini, Anda akan melihat "Azure PowerShell" dalam daftar program, dan dapat menghapus instalan dari sana.

## <a name="uninstall-from-powershell"></a>Menghapus instalan dari PowerShell

Jika Anda menginstal Azure PowerShell menggunakan PowerShellGet, Anda dapat menggunakan cmdlet [Uninstall-Module](/powershell/module/powershellget/uninstall-module). Namun, `Uninstall-Module` hanya menghapus instalan satu modul. Untuk menghapus Azure PowerShell seluruhnya, Anda harus menghapus instalan setiap modul satu per satu. Penghapusan instalan dapat menjadi rumit jika Anda memiliki beberapa versi Azure PowerShell yang diinstal.

Anda dapat menggunakan skrip berikut yang digunakan untuk menghapus satu versi Azure PowerShell sepenuhnya. Skrip ini mengkueri Galeri PowerShell untuk mendapatkan daftar submodel dependen. Kemudian, skrip menghapus instalan versi setiap submodul yang benar.

```powershell-interactive
function Uninstall-AllModules {
  param(
    [Parameter(Mandatory=$true)]
    [string]$TargetModule,

    [Parameter(Mandatory=$true)]
    [string]$Version,

    [switch]$Force,

    [switch]$WhatIf
  )

  $AllModules = @()

  'Creating list of dependencies...'
  $target = Find-Module $TargetModule -RequiredVersion $version
  $target.Dependencies | ForEach-Object {
    if ($_.PSObject.Properties.Name -contains 'requiredVersion') {
      $AllModules += New-Object -TypeName psobject -Property @{name=$_.name; version=$_.requiredVersion}
    }
    else { # Assume minimum version
      # Minimum version actually reports the installed dependency
      # which is used, not the actual "minimum dependency." Check to
      # see if the requested version was installed as a dependency earlier.
      $candidate = Get-InstalledModule $_.name -RequiredVersion $version -ErrorAction Ignore
      if ($candidate) {
        $AllModules += New-Object -TypeName psobject -Property @{name=$_.name; version=$version}
      }
      else {
        $availableModules = Get-InstalledModule $_.name -AllVersions
        Write-Warning ("Could not find uninstall candidate for {0}:{1} - module may require manual uninstall. Available versions are: {2}" -f $_.name,$version,($availableModules.Version -join ', '))
      }
    }
  }
  $AllModules += New-Object -TypeName psobject -Property @{name=$TargetModule; version=$Version}

  foreach ($module in $AllModules) {
    Write-Host ('Uninstalling {0} version {1}...' -f $module.name,$module.version)
    try {
      Uninstall-Module -Name $module.name -RequiredVersion $module.version -Force:$Force -ErrorAction Stop -WhatIf:$WhatIf
    } catch {
      Write-Host ("`t" + $_.Exception.Message)
    }
  }
}
```

Untuk menggunakan fungsi ini, salin dan tempel kode ke dalam sesi PowerShell Anda. Contoh berikut menunjukkan cara menjalankan fungsi untuk menghapus versi Azure PowerShell yang lebih lama.

```powershell-interactive
Uninstall-AllModules -TargetModule AzureRM -Version 4.4.1 -Force
```

Saat skrip berjalan, skrip akan menampilkan nama dan versi setiap submodul yang sedang dihapus. Untuk menjalankan skrip hanya untuk melihat yang akan dihapus, tanpa menghapusnya, gunakan opsi `-WhatIf`.

```output
Creating list of dependencies...
Uninstalling AzureRM.Profile version 3.4.1
Uninstalling Azure.Storage version 3.4.1
Uninstalling AzureRM.AnalysisServices version 0.4.7
Uninstalling Azure.AnalysisServices version 0.4.7
...
```

> [!NOTE]
> Jika skrip tidak dapat mencocokkan dependensi dengan versi sama yang akan dihapus instalannya, skrip tidak akan menghapus _setiap_ versi dependensi. Hal ini karena dapat terdapat versi modul target lainnya di sistem Anda yang bergantung pada dependensi ini. Dalam hal ini, versi dependensi yang tersedia dicantumkan.
> Anda kemudian dapat menghapus versi lama secara manual dengan `Uninstall-Module`.


Jalankan perintah untuk setiap versi Azure PowerShell yang ingin Anda hapus instalannya. Untuk mudahnya, skrip berikut akan menghapus instalan semua versi AzureRM __kecuali__ versi terbaru.

```powershell-interactive
$versions = (get-installedmodule AzureRM -AllVersions | Select-Object Version)
$versions[0..($versions.Length-2)]  | foreach { Uninstall-AllModules -TargetModule AzureRM -Version ($_.Version) -Force }
```
