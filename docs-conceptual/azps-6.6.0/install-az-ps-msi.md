---
title: Menginstal Azure PowerShell dengan MSI
description: Cara menginstal Azure PowerShell tanpa PowerShellGet menggunakan MSI
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/02/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: fd55dcaad84f458ca9e11b9d4accbe90e4f508cf
ms.sourcegitcommit: b7ef209e489945ce397bbbba2c5f34fa6b2ca22e
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429514"
---
# <a name="install-azure-powershell-on-windows-with-msi"></a>Menginstal Azure PowerShell di Windows dengan MSI

Artikel ini menjelaskan cara menginstal Azure PowerShell pada Windows menggunakan penginstal MSI. Penginstal MSI disediakan untuk lingkungan di mana Galeri PowerShell mungkin diblokir oleh firewall, atau penginstal offline diperlukan. Cara yang disarankan untuk Azure PowerShell diinstal adalah dengan PowerShellGet. Untuk instruksi tentang cara menggunakan PowerShellGet to install Azure PowerShell, lihat [Install Azure PowerShell with PowerShellGet](install-az-ps.md).

## <a name="requirements"></a>Persyaratan

Penginstal MSI pada Windows didesain untuk menginstal Azure PowerShell hanya untuk PowerShell 5.1. Untuk penginstalan di platform non-Windows atau versi PowerShell yang lebih baru, [Instal dengan PowerShellGet](install-az-ps.md). Untuk memeriksa versi PowerShell, jalankan perintah:

```powershell-interactive
$PSVersionTable.PSVersion
```

Untuk menggunakan Azure PowerShell PowerShell 5.1, Anda perlu:

1. Perbarui ke [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell) jika diperlukan. Jika menggunakan Windows 10, Anda sudah menginstal PowerShell 5.1.
2. Instal [.NET Framework 4.7.2 atau yang lebih baru.](/dotnet/framework/install)

## <a name="install-or-update-on-windows-using-the-msi-package"></a>Menginstal atau memperbarui Windows menggunakan Paket MSI

Paket MSI untuk Azure PowerShell tersedia dari [GitHub:](https://github.com/Azure/azure-powershell/releases)

1. Buka https://github.com/Azure/azure-powershell/releases .
1. Cari Modul Galeri terbaru untuk Azure PowerShell (tercantum secara kronologis dan biasanya hanya versi rilis tanpa nama seperti "4.7.0").
1. Gulir ke bawah ke bagian bawah catatan patch dan klik panah di samping "Aset" untuk mengungkapkan opsi MSI.
1. Klik ikon Az-Cmdlets MSI pilihan Anda untuk memulai pengunduhan.

Jika Anda telah menginstal versi lama Azure PowerShell menggunakan MSI, penginstal secara otomatis akan menghapusnya. Modul penginstalan paket MSI di `${env:ProgramFiles}\WindowsPowerShell\Modules` .

Untuk mulai bekerja dengan Azure PowerShell, masuk dengan kredensial Azure Anda.

```powershell-interactive
# Connect to Azure with an interactive dialog for sign-in
Connect-AzAccount
```

> [!NOTE]
> Jika Anda telah menonaktifkan muatan otomatis modul, Anda perlu mengimpor modul secara manual dengan `Import-Module Az` . Karena cara modul disusun, ini bisa memakan waktu hingga satu menit.

Anda harus mengulangi langkah ini untuk setiap sesi PowerShell baru yang anda mulai. Untuk mempelajari cara tetap masuk ke Azure di seluruh sesi PowerShell, lihat Tetap [menggunakan kredensial pengguna di seluruh sesi PowerShell.](context-persistence.md)

## <a name="provide-feedback"></a>Berikan umpan balik

Jika menemukan bug dalam Azure PowerShell, [kan ada masalah di GitHub](https://github.com/Azure/azure-powershell/issues). Untuk memberikan umpan balik dari baris perintah, gunakan cmdlet [Kirim-Umpan](/powershell/module/az.accounts/send-feedback) Balik.

## <a name="next-steps"></a>Langkah Berikutnya

Untuk mempelajari selengkapnya tentang modul Azure PowerShell fiturnya, lihat Mulai [dengan Azure PowerShell](get-started-azureps.md). Jika Anda sudah terbiasa dengan lebih Azure PowerShell dan perlu melakukan migrasi dari AzureRM, lihat Melakukan [migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).
