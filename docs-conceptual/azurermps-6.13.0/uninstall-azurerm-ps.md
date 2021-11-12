---
title: Menghapus Azure PowerShell
description: Cara melakukan penghapusan instalan Azure PowerShell
ms.date: 10/05/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 8b2cd5302b84718af1dd54298748f72914741b05
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429342"
---
# <a name="uninstall-the-azure-powershell-module"></a>Menghapus instalan Azure PowerShell aplikasi

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini memberi tahu Anda cara menghapus instalan versi lama Azure PowerShell, atau menghapus instalan sepenuhnya dari sistem. Jika memutuskan untuk menghapus instalan Azure PowerShell sepenuhnya, kirimkan umpan balik melalui cmdlet [Kirim-Umpan](/powershell/module/azurerm.profile/send-feedback) Balik. Jika Anda menghadapi bug, kami sangat menghargainya jika Anda [menggunggah GitHub Anda.](https://github.com/azure/azure-powershell/issues)


## <a name="uninstall-azure-powershell-msi"></a>Menghapus Azure PowerShell MSI

Jika menginstal Azure PowerShell paket MSI, Anda harus menghapus instalan melalui sistem Windows dan bukan PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Memulai > Pengaturan > Baru                                |
| Windows 7 </br>Windows 8 | Memulai > Panel Kontrol > Program > Menghapus instalan program |

Setelah berada di layar ini, Anda __Azure PowerShell__ layar dalam daftar program. Ini adalah aplikasi untuk menghapus instalasi.

## <a name="uninstall-from-powershell"></a>Menghapus instalan dari PowerShell

Jika Menginstal Azure PowerShell PowerShellGet, Anda dapat menggunakan cmdlet [Uninstall-Module.](/powershell/module/powershellget/uninstall-module) Namun, `Uninstall-Module` hanya menghapus instalan satu modul. Untuk menghapus Azure PowerShell, Anda harus menghapus instalan setiap modul satu per satu. Penghapusan instalan bisa rumit jika Anda memiliki lebih dari satu versi Azure PowerShell diinstal.

Untuk memeriksa versi versi Azure PowerShell yang saat ini terinstal, jalankan perintah berikut:

```powershell
Get-InstalledModule -Name AzureRM -AllVersions
```

```Output
Version              Name                                Repository           Description
-------              ----                                ----------           -----------
6.11.0               AzureRM                             PSGallery            Azure Resource Manager Module
6.13.1               AzureRM                             PSGallery            Azure Resource Manager Module
```

Skrip berikut ini memberikan kueri Galeri PowerShell untuk mendapatkan daftar submodul dependen. Kemudian, skrip menghapus instalan versi submodule yang benar. Anda harus memiliki akses administrator untuk menjalankan skrip ini dalam lingkup selain `Process` atau `CurrentUser` .

```powershell
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

Untuk menggunakan fungsi ini, salin dan tempelkan kode ke sesi PowerShell Anda. Contoh berikut ini memperlihatkan cara menjalankan fungsi untuk menghapus versi lama Azure PowerShell.

```powershell
Uninstall-AllModules -TargetModule AzureRM -Version 4.4.1 -Force
```

Saat skrip berjalan, skrip akan menampilkan nama dan versi setiap submodule yang sedang dihapus instalannya. Untuk menjalankan skrip agar hanya melihat apa yang akan dihapus, tanpa menghapusnya, gunakan `-WhatIf` opsi tersebut.

```Output
Creating list of dependencies...
Uninstalling AzureRM.Profile version 3.4.1
Uninstalling Azure.Storage version 3.4.1
Uninstalling AzureRM.AnalysisServices version 0.4.7
Uninstalling Azure.AnalysisServices version 0.4.7
...
```

> [!NOTE]
> Jika skrip ini tidak dapat menyesuaikan dependensi persis dengan versi yang  sama untuk dihapus, skrip tidak akan menghapus instalan versi dependensi tersebut. Ini karena mungkin ada versi modul target lainnya pada sistem Anda yang mengandalkan dependensi ini. Dalam hal ini, versi dependensi yang tersedia akan dicantumkan. Lalu Anda bisa menghapus versi lama secara manual dengan `Uninstall-Module` .

Jalankan perintah ini untuk setiap versi Azure PowerShell ingin Anda hapus instalannya. Demi kenyamanan, skrip berikut akan menghapus instalasi semua versi AzureRM __kecuali__ untuk yang terbaru.

```powershell
$versions = (Get-InstalledModule -Name AzureRM -AllVersions | Select-Object -Property Version)
$versions[0..($versions.Length-2)]  | foreach { Uninstall-AllModules -TargetModule AzureRM -Version ($_.Version) -Force }
```
