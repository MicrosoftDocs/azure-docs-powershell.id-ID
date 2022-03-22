---
title: Menghapus instalan Azure PowerShell
description: Cara melakukan penghapusan instalan Azure PowerShell secara menyeluruh
ms.date: 09/27/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: a2f48db0373435b964deac5a52a469537c44c31b
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429483"
---
# <a name="how-to-uninstall-azure-powershell-modules"></a>Cara menghapus instalan modul Azure PowerShell

Artikel ini menjelaskan cara menghapus instalan Azure PowerShell, atau menghapusnya secara menyeluruh dari sistem Anda.
Jika Anda memutuskan untuk menghapus instalan Azure PowerShell sepenuhnya dan tidak berencana untuk menginstal ulang, kirimkan umpan balik kepada kami melalui cmdlet [Send-Feedback](/powershell/module/az.accounts/send-feedback). Jika Anda menemukan bug, [laporkan masalah di GitHub](https://github.com/azure/azure-powershell/issues).

## <a name="uninstall-the-az-module"></a>Menghapus instalan modul Az

Jika modul Az terinstal di sistem Anda dan Anda ingin menghapus instalannya, terdapat dua opsi. Metode yang diikuti bergantung pada cara Anda menginstal modul Az. Jika tidak yakin dengan metode penginstalan awal, ikuti langkah MSI untuk menghapus instalan terlebih dahulu.

### <a name="option-1-uninstall-the-az-powershell-module-from-msi"></a>Opsi 1: Menghapus instalan modul Az PowerShell dari MSI

Jika Anda menginstal modul Az PowerShell menggunakan paket MSI, Anda harus menghapus instalan melalui sistem Windows, bukan PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Mulai > Pengaturan > Aplikasi                                |
| Windows 7 </br>Windows 8 | Mulai > Panel Kontrol > Program > Hapus instalan program |

Setelah tiba di layar ini, Anda akan melihat **Azure PowerShell** di daftar program. Ini adalah aplikasi untuk menghapus instalannya. Jika program tidak tercantum dalam daftar, maka Anda harus menghapus instalan melalui PowerShellGet dan ikuti petunjuk yang diuraikan dalam opsi 2.

### <a name="option-2-uninstall-the-az-powershell-module-from-powershellget"></a>Opsi 2: Menghapus instalan modul Az PowerShell dari PowerShellGet

Saat modul Az PowerShell diinstal, proses ini juga menginstal beberapa modul PowerShell untuk berbagai layanan Azure. Semua modul dimulai dengan awalan Az.

> [!IMPORTANT]
> Jalankan PowerShell yang lebih tinggi sebagai admin jika ada versi modul Az PowerShell yang diinstal di semua pengguna `$env:PSModulePath`.

Untuk menghapus instalan modul Az PowerShell, Anda dapat menggunakan cmdlet [Uninstall-Module](/powershell/module/powershellget/uninstall-module). Namun, `Uninstall-Module` hanya menghapus instalan modul yang ditentukan untuk parameter **Nama**. Untuk menghapus modul Az PowerShell seluruhnya, Anda harus menghapus instalan setiap modul satu per satu.

> [!NOTE]
> Penghapusan instalan mungkin menjadi rumit jika Anda menginstal lebih dari satu versi modul Az PowerShell. Karena kerumitan ini, kami hanya mendukung penghapusan instalan semua versi modul Az PowerShell yang saat ini terinstal.

Pertama, Anda memerlukan daftar semua versi modul Az PowerShell yang terinstal di sistem Anda.

```azurepowershell-interactive
Get-InstalledModule -Name Az -AllVersions -OutVariable AzVersions
```

Anda dapat menggunakan contoh berikut untuk membuat daftar semua modul Az PowerShell yang perlu dihapus instalannya selain modul Az.

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

Jika modul Az terinstal di sistem Anda dan Anda ingin menghapus instalan AzureRM, terdapat dua opsi. Metode yang diikuti bergantung pada cara Anda menginstal modul AzureRM. Jika tidak yakin dengan metode penginstalan awal, ikuti langkah MSI untuk menghapus instalan terlebih dahulu.

### <a name="option-1-uninstall-the-azurerm-powershell-module-from-msi"></a>Opsi 1: Menghapus instalan modul AzureRM PowerShell dari MSI

Jika Anda menginstal modul AzureRM PowerShell menggunakan paket MSI, Anda harus menghapus instalan melalui sistem Windows, bukan PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Mulai > Pengaturan > Aplikasi                                |
| Windows 7 </br>Windows 8 | Mulai > Panel Kontrol > Program > Hapus instalan program |

Setelah tiba di layar ini, Anda akan melihat **Azure PowerShell** atau **Microsoft Azure PowerShell - Bulan Tahun** di daftar program. Ini adalah aplikasi untuk menghapus instalannya. Jika program tidak tercantum dalam daftar, maka Anda harus menghapus instalan melalui PowerShellGet dan ikuti rangkaian petunjuk selanjutnya.

### <a name="option-2-uninstall-the-azurerm-powershell-module-from-powershellget"></a>Opsi 2: Menghapus instalan modul AzureRM PowerShell dari PowerShellGet

Jika Anda menginstal AzureRM dengan PowerShellGet, Anda dapat menghapus modul dengan cmdlet [Uninstall-AzureRM](/powershell/module/az.accounts/uninstall-azurerm), yang tersedia sebagai bagian dari modul `Az.Accounts`.

Untuk menggunakan `Uninstall-AzureRM` dari modul `Az.Accounts`, Anda harus menginstal modul Az PowerShell. Menginstal modul AzureRM dan Az secara bersamaan tidak didukung, tetapi modul Az dapat digunakan untuk segera menghapus instalan modul AzureRM. Anda dapat menginstal modul Az dan melewati peringatan modul AzureRM dengan perintah berikut jika Anda belum menginstal modul Az:

```powershell-interactive
Install-Module -Name Az -AllowClobber -Scope CurrentUser
```

Setelah modul Az diinstal, perintah berikut akan menghapus _semua_ modul AzureRM dari komputer Anda. Tindakan ini memerlukan hak istimewa administrator.

```powershell-interactive
Uninstall-AzureRm
```
