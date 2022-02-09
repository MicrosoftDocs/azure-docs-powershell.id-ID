---
title: Instal Azure PowerShell dengan MSI
description: Cara menginstal Azure PowerShell tanpa PowerShellGet menggunakan MSI
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/04/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 931bc58a0b6da886d5f0e65aa48f09848abcb4de
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138335103"
---
# <a name="install-azure-powershell-on-windows-with-msi"></a>Instal Azure PowerShell di Windows dengan MSI

Artikel ini menjelaskan cara menginstal Azure PowerShell di Windows menggunakan penginstal MSI. Penginstal MSI disediakan untuk lingkungan di mana Galeri PowerShell dapat diblokir oleh firewall, atau penginstal offline diperlukan. Cara yang disarankan untuk menginstal Azure PowerShell adalah dengan PowerShellGet. Untuk petunjuk tentang penggunaan PowerShellGet untuk menginstal Azure PowerShell, lihat [Menginstal Azure PowerShell dengan PowerShellGet](install-az-ps.md).

## <a name="requirements"></a>Persyaratan

Penginstal MSI pada Windows dirancang untuk menginstal Azure PowerShell hanya untuk PowerShell 5.1. Untuk instalasi pada platform non-Windows atau versi PowerShell yang lebih baru, [Instal dengan PowerShellGet](install-az-ps.md). Untuk memeriksa versi PowerShell Anda, jalankan perintah:

```powershell-interactive
$PSVersionTable.PSVersion
```

Untuk menggunakan Azure PowerShell di PowerShell 5.1, Anda perlu:

1. Perbarui ke [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell) jika diperlukan. Jika Anda berada di Windows 10, Anda sudah menginstal PowerShell 5.1.
2. Instal [.NET Framework 4.7.2 atau versi lebih baru](/dotnet/framework/install).

## <a name="install-or-update-on-windows-using-the-msi-package"></a>Menginstal atau memperbarui Windows menggunakan Paket MSI

Paket MSI untuk Azure PowerShell tersedia dari [GitHub](https://github.com/Azure/azure-powershell/releases):

1. Buka https://github.com/Azure/azure-powershell/releases.
1. Carilah Modul Galeri terbaru untuk Azure PowerShell (ini terdaftar secara kronologis dan biasanya hanya versi rilis tanpa nama seperti "4.7.0").
1. Gulir ke bawah ke bagian bawah catatan patch dan klik panah di samping "Aset" untuk mengungkapkan opsi MSI.
1. Klik pada Az-Cmdlets MSI pilihan Anda untuk memulai unduhan.

Jika Anda telah menginstal versi Azure PowerShell yang lebih lama menggunakan MSI, penginstal secara otomatis menghapusnya. Paket MSI menginstal modul di `${env:ProgramFiles}\WindowsPowerShell\Modules`.

Untuk mulai bekerja dengan Azure PowerShell, masuk dengan kredensial Azure Anda.

```powershell-interactive
# Connect to Azure with an interactive dialog for sign-in
Connect-AzAccount
```

> [!NOTE]
> Jika Anda telah menonaktifkan autoloading modul, Anda perlu mengimpor modul secara manual dengan `Import-Module Az`. Karena cara modul terstruktur, ini bisa memakan waktu hingga satu menit.

Anda harus mengulangi langkah ini untuk setiap sesi PowerShell baru yang Anda mulai. Untuk mempelajari cara mempertahankan login Azure anda di seluruh sesi PowerShell, lihat [Mempertahankan kredensial pengguna di seluruh sesi PowerShell](context-persistence.md).

## <a name="provide-feedback"></a>Berikan umpan balik

Jika Anda menemukan bug di Azure PowerShell, [ajukan masalah di GitHub](https://github.com/Azure/azure-powershell/issues). Untuk memberikan umpan balik dari baris perintah, gunakan cmdlet [Kirim Umpan Balik](/powershell/module/az.accounts/send-feedback) .

## <a name="next-steps"></a>Langkah berikutnya

Untuk mempelajari lebih lanjut tentang modul Azure PowerShell dan fitur-fiturnya, lihat [Mulai dengan Azure PowerShell](get-started-azureps.md). Jika Anda terbiasa dengan Azure PowerShell dan perlu bermigrasi dari AzureRM, lihat [Bermigrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).
