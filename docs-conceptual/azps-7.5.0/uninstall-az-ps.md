---
description: Cara melakukan penghapusan instalan Azure PowerShell secara menyeluruh
ms.custom: devx-track-azurepowershell
ms.date: 04/26/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Menghapus instalan Azure PowerShell
ms.openlocfilehash: 9bd7a7ee102e5fcda063d456fc8b23f2e6cb344e
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144685743"
---
# <a name="how-to-uninstall-azure-powershell-modules"></a>Cara menghapus instalan modul Azure PowerShell

Artikel ini menjelaskan cara menghapus instalan Azure PowerShell, atau menghapusnya secara menyeluruh dari sistem Anda.
Jika Anda memutuskan untuk menghapus instalan Azure PowerShell sepenuhnya dan tidak berencana untuk menginstal ulang, berikan beberapa umpan balik kepada kami melalui cmdlet [Send-Feedback](/powershell/module/az.accounts/send-feedback). Jika Anda menemukan bug, [ajukan masalah GitHub](https://github.com/azure/azure-powershell/issues).

## <a name="uninstall-the-az-module"></a>Menghapus instalan modul Az

Jika modul Az terinstal di sistem Anda dan Anda ingin menghapus instalannya, terdapat dua opsi. Metode yang diikuti bergantung pada cara Anda menginstal modul Az. Jika Anda tidak yakin dengan metode penginstalan awal Anda, ikuti langkah MSI untuk menghapus instalan terlebih dahulu.

### <a name="option-1-uninstall-the-az-powershell-module-from-msi"></a>Opsi 1: Menghapus instalan modul Az PowerShell dari MSI

Jika Anda menginstal modul Az PowerShell menggunakan paket MSI, Anda harus menghapus instalan melalui sistem Windows bukan PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Mulai > Pengaturan > Aplikasi                                |
| Windows 7 </br>Windows 8 | Mulai > Panel Kontrol > Program > Hapus instalan program |

Setelah tiba di layar ini, Anda akan melihat **Azure PowerShell** di daftar program. Daftar ini adalah aplikasi yang akan dihapus instalannya. Jika Anda tidak melalui program tercantum ini, Anda menghapus instalan melalui PowerShellGet, dan harus mengikuti instruksi yang diuraikan dalam opsi 2.

### <a name="option-2-uninstall-the-az-powershell-module-from-powershellget"></a>Opsi 2: Menghapus instalan modul Az PowerShell dari PowerShellGet

Ketika modul Az PowerShell diinstal, ini menginstal banyak modul PowerShell untuk berbagai layanan Azure. Semua modul dimulai dengan awalan Az.

> [!IMPORTANT]
> Jalankan PowerShell yang ditinggikan sebagai admin jika ada versi modul Az PowerShell yang diinstal di semua pengguna `$env:PSModulePath`.

Untuk menghapus instalan modul Az PowerShell, Anda dapat menggunakan cmdlet [Uninstall-Module](/powershell/module/powershellget/uninstall-module). Akan tetapi, `Uninstall-Module` hanya menghapus instalan modul yang ditentukan untuk parameter **Nama**. Untuk menghapus modul Az PowerShell seluruhnya, Anda harus menghapus instalan setiap modul satu per satu.

> [!NOTE]
> Penghapusan instalan dapat menjadi rumit jika Anda memiliki lebih dari satu versi modul Az PowerShell yang terinstal. Karena kompleksitas ini, kami hanya mendukung penghapusan instalan semua versi modul Az PowerShell yang saat ini terinstal.

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

Hapus modul Az dari memori lalu hapus instalannya.

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

Jika modul Az terinstal di sistem Anda dan Anda ingin menghapus instalan AzureRM, terdapat dua opsi. Metode yang diikuti bergantung pada cara Anda menginstal modul AzureRM. Jika Anda tidak yakin dengan metode penginstalan awal Anda, ikuti langkah MSI untuk menghapus instalan terlebih dahulu.

### <a name="option-1-uninstall-the-azurerm-powershell-module-from-msi"></a>Opsi 1: Menghapus instalan modul AzureRM PowerShell dari MSI

Jika Anda menginstal modul AzureRM PowerShell menggunakan paket MSI, Anda harus menghapus instalan melalui sistem Windows bukan PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Mulai > Pengaturan > Aplikasi                                |
| Windows 7 </br>Windows 8 | Mulai > Panel Kontrol > Program > Hapus instalan program |

Setelah tiba di layar ini, Anda akan melihat **Azure PowerShell** atau **Microsoft Azure PowerShell - Bulan Tahun** di daftar program. Daftar ini adalah aplikasi yang akan dihapus instalannya. Jika Anda tidak melalui program tercantum ini, Anda menghapus instalan melalui PowerShellGet, dan harus mengikuti set instruksi berikutnya.

### <a name="option-2-uninstall-the-azurerm-powershell-module-from-powershellget"></a>Opsi 2: Menghapus instalan modul AzureRM PowerShell dari PowerShellGet

Jika Anda menginstal AzureRM dengan PowerShellGet, Anda dapat menghapus modul dengan cmdlet [Uninstall-AzureRM](/powershell/module/az.accounts/uninstall-azurerm), yang tersedia sebagai bagian dari modul `Az.Accounts`.

Untuk menggunakan `Uninstall-AzureRM` dari modul `Az.Accounts`, Anda harus menginstal modul Az PowerShell. Modul AzureRM dan Az yang diinstal pada saat yang sama tidak didukung, namun modul Az dapat digunakan untuk segera menghapus instalan modul AzureRM. Anda dapat menginstal modul Az dan melewati peringatan modul AzureRM dengan perintah berikut jika Anda belum menginstal modul Az:

```powershell-interactive
Install-Module -Name Az -AllowClobber -Scope CurrentUser
```

Setelah modul Az diinstal, perintah berikut menghapus _semua_ modul AzureRM dari komputer Anda. Tindakan ini memerlukan hak istimewa administrator.

```powershell-interactive
Uninstall-AzureRm
```
