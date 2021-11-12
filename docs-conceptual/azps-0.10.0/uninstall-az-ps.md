---
title: Menghapus Azure PowerShell
description: Cara melakukan penghapusan instalan Azure PowerShell
ms.date: 09/15/2020
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: ff9135839b01ad9a1bf10e5969cd3226fe492145
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428325"
---
# <a name="uninstall-the-azure-powershell-module"></a>Menghapus instalan Azure PowerShell modul

Artikel ini memberi tahu Anda cara menghapus instalan versi lama Azure PowerShell, atau sepenuhnya menghapusnya dari sistem. Jika memutuskan untuk menghapus instalan Azure PowerShell sepenuhnya, beri kami beberapa umpan balik melalui cmdlet [Kirim Umpan Balik.](/powershell/module/az.accounts/send-feedback) Jika menemukan bug, kami menghargainya jika Anda [mengajukan GitHub sehingga](https://github.com/azure/azure-powershell/issues) masalah tersebut dapat diperbaiki.

## <a name="uninstall-the-az-powershell-module-from-msi"></a>Menghapus instalan modul Az PowerShell dari MSI

Jika Anda menginstal modul Az PowerShell menggunakan paket MSI, Anda harus menghapus instalasi melalui sistem Windows dan bukan PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Memulai > Pengaturan > Baru                                |
| Windows 7 </br>Windows 8 | Mulai > Panel Kontrol > Program > Menghapus instalan program |

Setelah berada di layar ini, Anda **akan Azure PowerShell** layar dalam daftar program. Ini adalah aplikasi untuk menghapus instalasi. Jika anda tidak melihat program ini dicantumkan, maka Anda menginstal melalui PowerShellGet, dan harus mengikuti kumpulan instruksi berikutnya.

## <a name="uninstall-the-az-powershell-module-from-powershellget"></a>Menghapus instalan modul Az PowerShell dari PowerShellGet

Untuk menghapus instalasi modul Az, Anda bisa menggunakan cmdlet [Uninstall-Module.](/powershell/module/powershellget/uninstall-module) Namun, `Uninstall-Module` hanya menghapus instalan satu modul. Untuk menghapus modul Az PowerShell sepenuhnya, Anda harus menghapus instalan setiap modul satu per satu. Penghapusan instalan bisa rumit jika Anda memiliki lebih dari satu versi Azure PowerShell diinstal.

Untuk memeriksa versi modul Az PowerShell mana yang sudah Anda instal, jalankan perintah berikut ini:

```powershell-interactive
Get-InstalledModule -Name Az -AllVersions
```

```output
Version             Name                           Repository           Description
-------             ----                           ----------           -----------
3.8.0               Az                             PSGallery            Microsoft Azure PowerShell
4.1.0               Az                             PSGallery            Microsoft Azure PowerShell
```

Skrip berikut ini memberikan kueri Galeri PowerShell untuk mendapatkan daftar submodul dependen. Kemudian, skrip menghapus instalan versi submodule yang benar. Anda harus mempunyai akses administrator untuk menjalankan skrip ini dalam lingkup selain Proses **atau** Pengguna **Saat Ini.**

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

Untuk menggunakan fungsi ini, salin dan tempelkan kode ke sesi PowerShell Anda. Contoh berikut ini menunjukkan cara menjalankan fungsi untuk menghapus versi lama modul Az PowerShell dan submodulnya.

```powershell-interactive
Uninstall-AzModule -Name Az -Version 1.8.0
```

Saat skrip berjalan, skrip menampilkan **Nama,** **Versi,** dan **Negara Bagian** setiap submodule yang sedang dihapus instalasinya. Untuk menjalankan skrip agar hanya melihat apa yang akan dihapus, tanpa menghapusnya, tentukan `-WhatIf` parameter.

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
> Jika skrip ini tidak dapat menyesuaikan dependensi persis dengan versi yang  sama untuk dihapus, skrip tidak akan menghapus instalan versi dependensi tersebut. Ini karena mungkin ada versi modul target lainnya pada sistem Anda yang mengandalkan dependensi ini.

Jalankan contoh berikut ini untuk setiap versi modul Az PowerShell yang ingin Anda hapus instalannya.
Demi kenyamanan, skrip berikut menghapus instalasi semua versi Az **kecuali** untuk yang terbaru.

```powershell-interactive
$Modules = Get-InstalledModule -Name Az -AllVersions |
    Sort-Object -Property Version -Descending |
        Select-Object -Skip 1
$Modules | ForEach-Object {Uninstall-AzModule -Name $_.Name -Version $_.Version}
```

## <a name="uninstall-the-azurerm-module"></a>Menghapus instalan modul AzureRM

Jika modul Az sudah terinstal di sistem Anda dan ingin menghapus instalan AzureRM, ada dua opsi. Metode mana yang Anda ikuti bergantung pada cara Anda menginstal modul AzureRM. Jika tidak yakin dengan metode penginstalan asli, ikuti langkah-langkah untuk menghapus instalan MSI terlebih dahulu.

### <a name="uninstall-the-azurerm-powershell-module-from-msi"></a>Menghapus instalan modul PowerShell AzureRM dari MSI

Jika menginstal modul PowerShell AzureRM menggunakan paket MSI, Anda harus menghapus instalan melalui sistem Windows, bukan PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Memulai > Pengaturan > Baru                                |
| Windows 7 </br>Windows 8 | Mulai > Panel Kontrol > Program > Menghapus instalan program |

Setelah berada di layar ini, Anda akan **Azure PowerShell** nama **Microsoft Azure PowerShell - Tahun Bulan** di daftar program. Ini adalah aplikasi untuk menghapus instalasi. Jika anda tidak melihat program ini dicantumkan, maka Anda menginstal melalui PowerShellGet, dan harus mengikuti kumpulan instruksi berikutnya.

### <a name="uninstall-the-azurerm-powershell-module-from-powershellget"></a>Menghapus instalan modul PowerShell AzureRM dari PowerShellGet

Jika menginstal AzureRM dengan PowerShellGet, Anda dapat menghapus modul menggunakan cmdlet [AzureRM Hapus](/powershell/module/az.accounts/uninstall-azurerm) Instalan, yang tersedia sebagai bagian `Az.Accounts` dari modul. Contoh berikut ini menghapus semua _modul_ AzureRM dari komputer Anda. Situs ini membutuhkan hak istimewa administrator.

```powershell-interactive
Uninstall-AzureRm
```
