---
title: Cara lain untuk menginstal Azure PowerShell
description: Cara menginstal Azure PowerShell tanpa PowerShellGet menggunakan MSI
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 91ef655591aade9a9a640d1e72503bdd147251fa
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429354"
---
# <a name="install-azure-powershell-on-windows-with-msi"></a>Menginstal Azure PowerShell di Windows dengan MSI

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini menjelaskan cara menginstal Azure PowerShell di Windows menggunakan penginstal MSI. Gunakan metode instalasi ini hanya jika diperlukan untuk sistem Anda. Cara yang disarankan untuk Azure PowerShell di Windows adalah dengan PowerShellGet. Untuk instruksi tentang cara menggunakan PowerShellGet to install Azure PowerShell, lihat [Menginstal Azure PowerShell with PowerShellGet](install-azurerm-ps.md).

> [!NOTE]
> Metode penginstalan Penginstal Platform Web tidak lagi tersedia untuk versi yang lebih Azure PowerShell 6.x dan lebih tinggi. Jika Anda memerlukan penggunaan Penginstal Platform Web, pertimbangkan untuk menggunakan MSI sebagai gantinya, atau Anda dapat menginstal versi penginstal Azure PowerShell.

## <a name="install-or-update-on-windows-using-the-msi-package"></a>Menginstal atau memperbarui Windows menggunakan Paket MSI

Azure PowerShell untuk Windows PowerShell 5.x bisa diinstal menggunakan file MSI yang tersedia [dari GitHub](https://github.com/Azure/azure-powershell/releases/tag/v6.13.1-November2018). Jika Anda telah menginstal versi modul Azure sebelumnya sebagai MSI, penginstal secara otomatis akan menghapusnya.
Modul penginstalan paket MSI di `${env:ProgramFiles}\WindowsPowerShell\Modules` . Modul `AzureRM` dan `Azure` program telah diinstal.

> [!NOTE]
> Gunakan modul `Azure` hanya jika Anda bekerja dengan model penyebaran klasik Azure.

Untuk mulai bekerja dengan Azure PowerShell, masuk dengan kredensial Azure Anda.

```azurepowershell
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

> [!NOTE]
> Jika Anda telah menonaktifkan muatan otomatis modul, Anda perlu mengimpor modul secara manual dengan `Import-Module -Name AzureRM` . Karena cara modul disusun, ini dapat memakan waktu beberapa detik.

Anda harus mengulangi langkah ini untuk setiap sesi PowerShell baru yang anda mulai. Untuk mempelajari cara tetap masuk ke Azure di seluruh sesi PowerShell, lihat Tetap [menggunakan kredensial pengguna di seluruh sesi PowerShell.](context-persistence.md)
