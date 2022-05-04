---
description: Cara menginstal Azure PowerShell tanpa PowerShellGet menggunakan MSI
ms.custom: devx-track-azurepowershell
ms.date: 04/26/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Menginstal Azure PowerShell dengan MSI
ms.openlocfilehash: 47d61dac17b87c5516afbc1cfee663ed8248949b
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144726262"
---
# <a name="install-azure-powershell-on-windows-with-msi"></a>Menginstal Azure PowerShell di Windows dengan MSI

Artikel ini menjelaskan cara menginstal Azure PowerShell di Windows menggunakan penginstal MSI. Penginstal MSI disediakan untuk lingkungan tempat Galeri PowerShell dapat diblokir oleh firewall, atau penginstal offline diperlukan. Cara yang disarankan untuk menginstal Azure PowerShell adalah dengan PowerShellGet. Untuk petunjuk tentang menggunakan PowerShellGet untuk menginstal Azure PowerShell, lihat [Menginstal Azure PowerShell dengan PowerShellGet](install-az-ps.md).

## <a name="requirements"></a>Persyaratan

Penginstal MSI di Windows dirancang untuk menginstal Azure PowerShell hanya untuk PowerShell 5.1. Untuk penginstalan di platform non-Windows atau versi PowerShell yang lebih baru, [Instal dengan PowerShellGet](install-az-ps.md). Untuk memeriksa versi PowerShell Anda, jalankan perintah:

```powershell-interactive
$PSVersionTable.PSVersion
```

Untuk menggunakan Azure PowerShell di PowerShell 5.1, Anda harus:

1. Perbarui ke [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell) jika diperlukan. Jika Anda menggunakan Windows 10, PowerShell 5.1 sudah terinstal di dalamnya.
2. Instal [.NET Framework 4.7.2 or versi lebih baru](/dotnet/framework/install).

## <a name="install-or-update-on-windows-using-the-msi-package"></a>Menginstal atau memperbarui di Windows menggunakan Paket MSI

Paket MSI untuk Azure PowerShell tersedia dari [GitHub](https://github.com/Azure/azure-powershell/releases):

1. Buka https://github.com/Azure/azure-powershell/releases.
1. Cari Modul Galeri terbaru untuk Azure PowerShell (modul ini tercantum secara kronologis dan biasanya hanya berupa versi rilis tanpa nama seperti "4.7.0").
1. Gulir ke bawah ke bagian bawah catatan patch dan klik tanda panah di samping "Aset" untuk membuka opsi MSI.
1. Klik MSI Az-Cmdlet pilihan Anda untuk memulai unduhan.

Jika Anda telah menginstal versi Azure PowerShell yang lebih lama menggunakan MSI, penginstal akan menghapusnya secara otomatis. Paket MSI menginstal modul di `${env:ProgramFiles}\WindowsPowerShell\Modules`.

Untuk mulai bekerja dengan Azure PowerShell, masuk dengan info masuk Azure Anda.

```powershell-interactive
# Connect to Azure with an interactive dialog for sign-in
Connect-AzAccount
```

> [!NOTE]
> Jika Anda telah menonaktifkan pemuatan otomatis modul, Anda harus mengimpor modul secara manual dengan `Import-Module Az`. Karena cara modul disusun, hal ini dapat memakan waktu hingga satu menit.

Anda harus mengulangi langkah ini untuk setiap sesi PowerShell baru yang Anda mulai. Untuk mempelajari cara mempertahankan masuk Azure Anda di seluruh sesi PowerShell, lihat [Mempertahankan info masuk pengguna di seluruh sesi PowerShell](context-persistence.md).

## <a name="provide-feedback"></a>Berikan umpan balik

Jika Anda menemukan bug di Azure PowerShell, [ajukan masalah di GitHub](https://github.com/Azure/azure-powershell/issues). Untuk memberikan umpan balik dari baris perintah, gunakan cmdlet [Send-Feedback](/powershell/module/az.accounts/send-feedback).

## <a name="next-steps"></a>Langkah berikutnya

Untuk mempelajari selengkapnya tentang modul Azure PowerShell dan fiturnya, lihat [Memulai dengan Azure PowerShell](get-started-azureps.md). Jika Anda terbiasa dengan Azure PowerShell dan perlu bermigrasi dari AzureRM, lihat [Memigrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).
