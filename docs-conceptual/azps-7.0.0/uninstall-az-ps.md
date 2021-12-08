---
title: Menghapus Azure PowerShell
description: Cara melakukan penghapusan instalan Azure PowerShell
ms.date: 12/07/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: ca10e4f6dd937a54a233de4d06dc3a0af2d7b457
ms.sourcegitcommit: 2a404a7aac28f6568e0e17912814e4403ea5d0d9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/08/2021
ms.locfileid: "134111063"
---
# <a name="how-to-uninstall-azure-powershell-modules"></a>Cara menghapus Azure PowerShell modul

Artikel ini menjelaskan cara menghapus Azure PowerShell, atau menghapus sepenuhnya dari sistem Anda.
Jika memutuskan untuk menghapus instalan Azure PowerShell sepenuhnya dan tidak berencana untuk menginstal ulang, berikan kami beberapa umpan balik melalui cmdlet [Kirim-Umpan](/powershell/module/az.accounts/send-feedback) Balik. Jika Anda menemukan bug, [terjadi masalah GitHub file](https://github.com/azure/azure-powershell/issues).

## <a name="uninstall-the-az-module"></a>Menghapus instalan modul Az

Jika Anda memiliki modul Az yang terinstal di sistem Anda dan ingin menghapus instalasinya, ada dua opsi. Metode mana yang Anda ikuti bergantung pada cara Anda menginstal modul Az. Jika tidak yakin dengan metode penginstalan asli, ikuti langkah-langkah MSI untuk menghapus instalan terlebih dahulu.

### <a name="option-1-uninstall-the-az-powershell-module-from-msi"></a>Opsi 1: Menghapus instalan modul Az PowerShell dari MSI

Jika Anda menginstal modul Az PowerShell menggunakan paket MSI, Anda harus menghapus instalasi melalui sistem Windows dan bukan PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Memulai > Pengaturan > Baru                                |
| Windows 7 </br>Windows 8 | Memulai > Panel Kontrol > Program > Menghapus instalan program |

Setelah berada di layar ini, Anda akan **Azure PowerShell** daftar program. Ini adalah aplikasi untuk menghapus instalasi. Jika Anda tidak melihat program ini dicantumkan, maka Anda menginstal melalui PowerShellGet dan harus mengikuti instruksi yang diuraikan dalam opsi 2.

### <a name="option-2-uninstall-the-az-powershell-module-from-powershellget"></a>Opsi 2: Menghapus instalan modul Az PowerShell dari PowerShellGet

Saat modul Az PowerShell diinstal, modul ini akan menginstal sejumlah modul PowerShell untuk layanan Azure yang berbeda. Semua modul dimulai dengan prefiks Az.

> [!IMPORTANT]
> Jalankan PowerShell yang ditinggikan sebagai admin jika versi modul Az PowerShell apa pun diinstal di semua `$env:PSModulePath` pengguna.

Untuk menghapus instalasi modul Az PowerShell, Anda bisa menggunakan cmdlet [Uninstall-Module.](/powershell/module/powershellget/uninstall-module) Namun, `Uninstall-Module` hanya menghapus instalan modul yang ditentukan untuk parameter **Name.** Untuk menghapus modul Az PowerShell sepenuhnya, Anda harus menghapus instalan setiap modul satu per satu.

> [!NOTE]
> Penghapusan instalan bisa rumit jika Anda memiliki lebih dari satu versi modul Az PowerShell yang terinstal. Karena kompleksitas ini, kami hanya mendukung penghapusan instalan semua versi modul Az PowerShell yang saat ini terinstal.

Pertama, Anda akan membutuhkan daftar semua versi modul Az PowerShell yang terinstal di sistem Anda.

```azurepowershell-interactive
Get-InstalledModule -Name Az -AllVersions -OutVariable AzVersions
```

Anda bisa menggunakan contoh berikut ini untuk membuat daftar semua modul Az PowerShell yang perlu dihapus instalasinya selain modul Az.

```azurepowershell-interactive
($AzVersions |
  ForEach-Object {
    Import-Clixml -Path (Join-Path -Path $_.InstalledLocation -ChildPath PSGetModuleInfo.xml)
  }).Dependencies.Name | Sort-Object -Descending -Unique -OutVariable AzModules
```

Hapus modul Az dari memori, lalu hapus instalannya.

```azurepowershell-interactive
$AzModules |
  ForEach-Object {
    Remove-Module -Name $_ -ErrorAction SilentlyContinue
    Write-Output "Attempting to uninstall module: $_"
    Uninstall-Module -Name $_ -AllVersions
  }
```

Langkah terakhir adalah menghapus modul Az PowerShell.

```azurepowershell-interactive
Remove-Module -Name Az -ErrorAction SilentlyContinue
Uninstall-Module -Name Az -AllVersions
```

## <a name="uninstall-the-azurerm-module"></a>Menghapus instalan modul AzureRM

Jika modul Az sudah terinstal di sistem Anda dan ingin menghapus instalan AzureRM, ada dua opsi. Metode mana yang Anda ikuti bergantung pada cara Anda menginstal modul AzureRM. Jika tidak yakin dengan metode penginstalan asli, ikuti langkah-langkah MSI untuk menghapus instalan terlebih dahulu.

### <a name="option-1-uninstall-the-azurerm-powershell-module-from-msi"></a>Opsi 1: Menghapus instalan modul PowerShell AzureRM dari MSI

Jika menginstal modul PowerShell AzureRM menggunakan paket MSI, Anda harus menghapus instalan melalui sistem Windows, bukan PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Memulai > Pengaturan > Baru                                |
| Windows 7 </br>Windows 8 | Memulai > Panel Kontrol > Program > Menghapus instalan program |

Setelah berada di layar ini, Anda akan **melihat Azure PowerShell** Microsoft Azure PowerShell - **Tahun Bulan** di daftar program. Ini adalah aplikasi untuk menghapus instalasi. Jika anda tidak melihat program ini dicantumkan, maka Anda menginstal melalui PowerShellGet, dan harus mengikuti kumpulan instruksi berikutnya.

### <a name="option-2-uninstall-the-azurerm-powershell-module-from-powershellget"></a>Opsi 2: Menghapus instalan modul PowerShell AzureRM dari PowerShellGet

Jika menginstal AzureRM dengan PowerShellGet, Anda dapat menghapus modul menggunakan cmdlet [AzureRM Hapus](/powershell/module/az.accounts/uninstall-azurerm) Instalan, yang tersedia sebagai bagian `Az.Accounts` dari modul.

Untuk menggunakan `Uninstall-AzureRM` dari modul `Az.Accounts` tersebut, Anda harus menginstal modul Az PowerShell. Menginstal modul AzureRM dan Az secara bersamaan tidak didukung, namun modul Az dapat digunakan untuk langsung menghapus instalan modul AzureRM. Anda bisa menginstal modul Az dan melewati peringatan modul AzureRM dengan perintah berikut ini jika Anda belum menginstal modul Az:

```powershell-interactive
Install-Module -Name Az -AllowClobber -Scope CurrentUser
```

Setelah modul Az diinstal, perintah berikut ini akan menghapus _semua modul_ AzureRM dari komputer Anda. Situs ini membutuhkan hak istimewa administrator.

```powershell-interactive
Uninstall-AzureRm
```
