---
description: Cara melakukan uninstall lengkap Azure PowerShell
ms.custom: devx-track-azurepowershell
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Hapus Azure PowerShell
ms.openlocfilehash: 706fdd3855244ec424b28d0e6a76d6cd7668459e
ms.sourcegitcommit: cdca0d3199eb118c98aafb63ffcacc3dd080f0d4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "138854973"
---
# <a name="how-to-uninstall-azure-powershell-modules"></a>Cara menghapus modul Azure PowerShell

Artikel ini menjelaskan cara menghapus Azure PowerShell, atau menghapusnya sepenuhnya dari sistem Anda.
Jika Anda telah memutuskan untuk menghapus Azure PowerShell sepenuhnya dan tidak berencana untuk menginstalnya kembali, beri kami beberapa umpan balik melalui cmdlet [Kirim Umpan Balik](/powershell/module/az.accounts/send-feedback). Jika Anda menemukan bug, [ajukan masalah GitHub](https://github.com/azure/azure-powershell/issues).

## <a name="uninstall-the-az-module"></a>Menghapus instalan modul Az

Jika Anda memiliki modul Az yang diinstal pada sistem Anda dan ingin menghapusnya, ada dua opsi. Metode mana yang Anda ikuti tergantung pada bagaimana Anda menginstal modul Az. Jika Anda tidak yakin dengan metode instalasi asli Anda, ikuti langkah-langkah MSI untuk menghapus instalasi terlebih dahulu.

### <a name="option-1-uninstall-the-az-powershell-module-from-msi"></a>Opsi 1: Hapus instalan modul Az PowerShell dari MSI

Jika Anda menginstal modul Az PowerShell menggunakan paket MSI, Anda harus menghapus instalasi melalui sistem Windows daripada PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Mulai aplikasi > Pengaturan >                                |
| Windows 7 </br>Windows 8 | Mulai > Panel Kontrol > Program > Uninstall program |

Setelah di layar ini, Anda akan melihat **Azure PowerShell** dalam daftar program. Ini adalah aplikasi untuk dihapus. Jika Anda tidak melihat program ini tercantum, maka Anda menginstal melalui PowerShellGet dan harus mengikuti instruksi yang diuraikan dalam opsi 2.

### <a name="option-2-uninstall-the-az-powershell-module-from-powershellget"></a>Opsi 2: Hapus instalan modul Az PowerShell dari PowerShellGet

Ketika modul Az PowerShell diinstal, ia menginstal banyak modul PowerShell untuk layanan Azure yang berbeda. Semua modul dimulai dengan awalan Az.

> [!IMPORTANT]
> Jalankan PowerShell yang ditinggikan sebagai admin jika ada versi modul Az PowerShell yang diinstal di semua pengguna `$env:PSModulePath`.

Untuk menghapus modul Az PowerShell, Anda dapat menggunakan cmdlet [Uninstall-Module](/powershell/module/powershellget/uninstall-module) . Namun, `Uninstall-Module` hanya menghapus instalan modul yang ditentukan untuk parameter **Nama** . Untuk menghapus modul Az PowerShell sepenuhnya, Anda harus menghapus setiap modul secara individual.

> [!NOTE]
> Penghapusan instalasi bisa rumit jika Anda memiliki lebih dari satu versi modul Az PowerShell yang diinstal. Karena kompleksitas ini, kami hanya mendukung penghapusan semua versi modul Az PowerShell yang saat ini diinstal.

Pertama, Anda memerlukan daftar semua versi modul Az PowerShell yang diinstal pada sistem Anda.

```azurepowershell-interactive
Get-InstalledModule -Name Az -AllVersions -OutVariable AzVersions
```

Anda dapat menggunakan contoh berikut untuk membuat daftar semua modul Az PowerShell yang perlu dihapus selain modul Az.

```azurepowershell-interactive
($AzVersions |
  ForEach-Object {
    Import-Clixml -Path (Join-Path -Path $_.InstalledLocation -ChildPath PSGetModuleInfo.xml)
  }).Dependencies.Name | Sort-Object -Descending -Unique -OutVariable AzModules
```

Hapus modul Az dari memori dan kemudian uninstall mereka.

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

Jika Anda memiliki modul Az yang diinstal pada sistem Anda dan ingin menghapus AzureRM, ada dua opsi. Metode mana yang Anda ikuti tergantung pada cara Anda menginstal modul AzureRM. Jika Anda tidak yakin dengan metode instalasi asli Anda, ikuti langkah-langkah MSI untuk menghapus instalasi terlebih dahulu.

### <a name="option-1-uninstall-the-azurerm-powershell-module-from-msi"></a>Opsi 1: Hapus instalan modul AzureRM PowerShell dari MSI

Jika Anda menginstal modul AzureRM PowerShell menggunakan paket MSI, Anda harus menghapus instalasi melalui sistem Windows daripada PowerShell.

|         Platform         |                      Instruksi                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Mulai aplikasi > Pengaturan >                                |
| Windows 7 </br>Windows 8 | Mulai > Panel Kontrol > Program > Uninstall program |

Setelah di layar ini, Anda akan melihat **Azure PowerShell** atau **Microsoft Azure PowerShell - Tahun Bulan** dalam daftar program. Ini adalah aplikasi untuk dihapus. Jika Anda tidak melihat program ini tercantum, maka Anda menginstal melalui PowerShellGet, dan harus mengikuti serangkaian instruksi berikutnya.

### <a name="option-2-uninstall-the-azurerm-powershell-module-from-powershellget"></a>Opsi 2: Hapus instalan modul AzureRM PowerShell dari PowerShellGet

Jika Anda menginstal AzureRM dengan PowerShellGet, maka Anda dapat menghapus modul dengan cmdlet [Uninstall-AzureRM](/powershell/module/az.accounts/uninstall-azurerm) , tersedia sebagai bagian dari `Az.Accounts` modul.

Untuk digunakan `Uninstall-AzureRM` dari `Az.Accounts` modul, Anda harus menginstal modul Az PowerShell. Memiliki modul AzureRM dan Az yang diinstal pada saat yang sama tidak didukung, namun modul Az dapat digunakan untuk segera menghapus modul AzureRM. Anda dapat menginstal modul Az dan memotong peringatan modul AzureRM dengan perintah berikut jika Anda belum menginstal modul Az:

```powershell-interactive
Install-Module -Name Az -AllowClobber -Scope CurrentUser
```

Setelah modul Az diinstal, perintah berikut menghapus _semua_ modul AzureRM dari mesin Anda. Ini membutuhkan hak administrator.

```powershell-interactive
Uninstall-AzureRm
```
