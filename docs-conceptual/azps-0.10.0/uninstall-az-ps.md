---
title: Menghapus instalan Azure PowerShell
description: Cara melakukan penghapusan instalan Azure PowerShell secara menyeluruh
ms.date: 09/15/2020
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: ff9135839b01ad9a1bf10e5969cd3226fe492145
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428325"
---
# <a name="uninstall-the-azure-powershell-module"></a>Menghapus instalan modul Azure PowerShell

Artikel ini menjelaskan cara menghapus instalan versi Azure PowerShell lama, atau menghapus seluruhnya dari sistem Anda. Jika Anda memutuskan untuk menghapus instalan Azure PowerShell sepenuhnya, berikan beberapa umpan balik kepada kami melalui cmdlet [Send-Feedback](/powershell/module/az.accounts/send-feedback). Jika Anda menjumpai bug, kami akan sangat menghargainya jika Anda [mencatatkan masalah GitHub](https://github.com/azure/azure-powershell/issues) sehingga dapat diperbaiki.

## <a name="uninstall-the-az-powershell-module-from-msi"></a>Menghapus instalan modul Az PowerShell dari MSI

Jika Anda menginstal modul Az PowerShell menggunakan paket MSI, Anda harus menghapus instalan melalui sistem Windows bukan PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Mulai > Pengaturan > Aplikasi                                |
| Windows 7 </br>Windows 8 | Mulai > Panel Kontrol > Program > Hapus instalan program |

Setelah tiba di layar ini, Anda akan melihat **Azure PowerShell** di daftar program. Daftar ini adalah aplikasi yang akan dihapus instalannya. Jika Anda tidak melalui program tercantum ini, Anda menghapus instalan melalui PowerShellGet, dan harus mengikuti set instruksi berikutnya.

## <a name="uninstall-the-az-powershell-module-from-powershellget"></a>Menghapus instalan modul Az PowerShell dari PowerShellGet

Untuk menghapus modul Az, Anda dapat menggunakan cmdlet [Uninstall-Module](/powershell/module/powershellget/uninstall-module). Namun, `Uninstall-Module` hanya menghapus instalan satu modul. Untuk menghapus modul Az PowerShell seluruhnya, Anda harus menghapus instalan setiap modul satu per satu. Penghapusan instalan dapat menjadi rumit jika Anda memiliki lebih dari satu versi Azure PowerShell yang diinstal.

Untuk memeriksa versi modul Az PowerShell yang telah diinstal, jalankan perintah berikut:

```powershell-interactive
Get-InstalledModule -Name Az -AllVersions
```

```output
Version             Name                           Repository           Description
-------             ----                           ----------           -----------
3.8.0               Az                             PSGallery            Microsoft Azure PowerShell
4.1.0               Az                             PSGallery            Microsoft Azure PowerShell
```

Skrip berikut meminta Galeri PowerShell untuk mendapatkan daftar submodul dependen. Kemudian, skrip menghapus instalan versi setiap submodul yang benar. Anda harus memiliki akses administrator untuk menjalankan skrip ini dalam cakupan selain **Proses** atau **Pengguna Saat Ini**.

```powershell-interactive
function Uninstall-AzModule {
  [CmdletBinding(SupportsShouldProcess)]
  param(
    [ValidateNotNullOrEmpty()]
    [ValidateSet('Az','AzureRM','Azure')]
    [string]$Name = 'Az',

    [Parameter(Mandatory)]
    [string]$Version,

    [switch]$AllowPrerelease
  )

  $Params = @{}

  if ($PSBoundParameters.AllowPrerelease) {
    $Params.AllowPrerelease = $true
  }

  $IsAdmin = ([Security.Principal.WindowsPrincipal] [Security.Principal.WindowsIdentity]::GetCurrent()).IsInRole([Security.Principal.WindowsBuiltInRole] 'Administrator')

  if (-not(Get-InstalledModule -Name $Name -RequiredVersion $Version -ErrorAction SilentlyContinue -OutVariable RootModule @Params)) {

    Write-Warning -Message "Uninstall aborted. $Name version $Version not found."

  } elseif (($RootModule.InstalledLocation -notlike "*$env:USERPROFILE*") -and ($IsAdmin -eq $false)) {

    Write-Warning -Message "Uninstall aborted. $Name version $Version exists in a system path. PowerShell must be run elevated as an admin to remove it."

  } elseif ((Get-Process -Name powershell, pwsh -OutVariable Sessions -ErrorAction SilentlyContinue).Count -gt 1) {

    Write-Warning -Message "Uninstall aborted. Please close all other PowerShell sessions before continuing. There are currently $($Sessions.Count) PowerShell sessions running."

  } else {
    Write-Verbose -Message 'Creating list of dependencies...'
    $target = Find-Module -Name $Name -RequiredVersion $Version @Params

    $AllModules = @([pscustomobject]@{
      Name = $Name
      Version = $Version
    })

    $AllModules += foreach ($dependency in $target.Dependencies) {
      switch ($dependency.keys) {
        {$_ -contains 'RequiredVersion'} {$UninstallVersion = $dependency.RequiredVersion; break}
        {$_ -contains 'MinimumVersion'} {$UninstallVersion = $dependency.MinimumVersion; break}
      }

      [pscustomobject]@{
        Name = $dependency.Name
        Version = $UninstallVersion
      }
    }

    [int]$i = 100 / $AllModules.Count

    foreach ($module in $AllModules) {
      Write-Progress -Activity 'Uninstallation in Progress' -Status "$i% Complete:" -PercentComplete $i
      $i++

      if (Get-InstalledModule -Name $module.Name -RequiredVersion $module.Version -ErrorAction SilentlyContinue @Params) {
        Write-Verbose -Message "Uninstalling $($module.Name) version $($module.Version)"

        Remove-Module -FullyQualifiedName @{ModuleName=$module.Name;ModuleVersion=$module.Version} -ErrorAction SilentlyContinue

        try {
          if ($PSCmdlet.ShouldProcess("$($module.Name) version $($module.Version)")) {
            Uninstall-Module -Name $module.Name -RequiredVersion $module.Version -Force -ErrorAction Stop @Params
          }
          $State = 'Uninstalled'
        } Catch {
          $State = 'Manual uninstall required'
          Write-Verbose -Message "$($module.Name) version: $($module.Version) may require manual uninstallation."
        }

      } else {
        $State = 'Not found'
        Write-Verbose -Message "$($module.Name) version: $($module.Version) not found."
      }

      if (-not $PSBoundParameters.WhatIf) {
        [pscustomobject]@{
          ModuleName = $module.Name
          Version = $module.Version
          State = $State
        }
      }

    }
  }
}
```

Untuk menggunakan fungsi ini, salin dan tempel kode ke dalam sesi PowerShell Anda. Contoh berikut menunjukkan cara menjalankan fungsi untuk menghapus versi modul Az PowerShell yang lebih lama dan submodulnya.

```powershell-interactive
Uninstall-AzModule -Name Az -Version 1.8.0
```

Saat skrip berjalan, skrip menampilkan **Nama**, **Versi**, dan **Status** setiap submodul yang akan dihapus instalannya. Untuk menjalankan skrip hanya untuk melihat yang akan dihapus, tanpa menghapusnya, tentukan parameter `-WhatIf`.

```output
ModuleName              Version  State
----------              -------  -----
Az.Accounts             1.5.1    Not found
Az.Aks                  1.0.1    Uninstalled
Az.AnalysisServices     1.1.0    Uninstalled
Az.ApiManagement        1.0.0    Uninstalled
Az.ApplicationInsights  1.0.0    Uninstalled
...
```

> [!IMPORTANT]
> Jika skrip tidak dapat mencocokkan dependensi dengan versi sama yang akan dihapus instalannya, skrip tidak akan menghapus _setiap_ versi dependensi. Hal ini karena dapat terdapat versi modul target lainnya di sistem Anda yang bergantung pada dependensi ini.

Jalankan contoh berikut untuk setiap versi modul Az PowerShell yang ingin Anda hapus instalannya.
Untuk mudahnya, skrip berikut menghapus instalan semua versi Az **kecuali** versi terbaru.

```powershell-interactive
$Modules = Get-InstalledModule -Name Az -AllVersions |
    Sort-Object -Property Version -Descending |
        Select-Object -Skip 1
$Modules | ForEach-Object {Uninstall-AzModule -Name $_.Name -Version $_.Version}
```

## <a name="uninstall-the-azurerm-module"></a>Menghapus instalan modul AzureRM

Jika modul Az terinstal di sistem Anda dan Anda ingin menghapus instalan AzureRM, terdapat dua opsi. Metode yang diikuti bergantung pada cara Anda menginstal modul AzureRM. Jika Anda tidak yakin dengan metode penginstalan awal Anda, ikuti langkah untuk menghapus MSI terlebih dahulu.

### <a name="uninstall-the-azurerm-powershell-module-from-msi"></a>Menghapus instalan modul AzureRM PowerShell dari MSI

Jika Anda menginstal modul AzureRM PowerShell menggunakan paket MSI, Anda harus menghapus instalan melalui sistem Windows bukan PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Mulai > Pengaturan > Aplikasi                                |
| Windows 7 </br>Windows 8 | Mulai > Panel Kontrol > Program > Hapus instalan program |

Setelah tiba di layar ini, Anda akan melihat **Azure PowerShell** atau **Microsoft Azure PowerShell - Bulan Tahun** di daftar program. Daftar ini adalah aplikasi yang akan dihapus instalannya. Jika Anda tidak melalui program tercantum ini, Anda menghapus instalan melalui PowerShellGet, dan harus mengikuti set instruksi berikutnya.

### <a name="uninstall-the-azurerm-powershell-module-from-powershellget"></a>Menghapus instalan modul AzureRM PowerShell dari PowerShellGet

Jika Anda menginstal AzureRM dengan PowerShellGet, Anda dapat menghapus modul dengan cmdlet [Uninstall-AzureRM](/powershell/module/az.accounts/uninstall-azurerm), yang tersedia sebagai bagian dari modul `Az.Accounts`. Contoh berikut menghapus _semua_ modul AzureRM dari komputer Anda. Tindakan ini memerlukan hak istimewa administrator.

```powershell-interactive
Uninstall-AzureRm
```
