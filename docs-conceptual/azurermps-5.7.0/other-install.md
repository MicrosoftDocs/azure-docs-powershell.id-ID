---
title: Cara lain untuk menginstal Azure PowerShell
description: Cara menginstal Azure PowerShell tanpa PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/20/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 7148188603e84efbcd784264de4c78819edf6833
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422890"
---
# <a name="install-azure-powershell-on-windows-with-msi-or-web-platform-installer"></a>Instal Azure PowerShell di Windows dengan Penginstal Platform MSI atau Web

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini menjelaskan cara menginstal Azure PowerShell di Windows menggunakan Penginstal Platform MSI atau Web (WebPI).
Gunakan metode instalasi ini hanya jika diperlukan untuk sistem Anda. Cara yang disarankan untuk Azure PowerShell di Windows adalah dengan PowerShellGet. Untuk instruksi tentang cara menggunakan PowerShellGet to install Azure PowerShell, lihat [Menginstal Azure PowerShell dengan PowerShellGet](install-azurerm-ps.md).

## <a name="install-or-update-on-windows-using-the-msi-package"></a>Menginstal atau memperbarui Windows menggunakan Paket MSI

Azure PowerShell bisa diinstal menggunakan file MSI yang tersedia dari [GitHub](https://github.com/Azure/azure-powershell/releases/tag/v5.7.0-April2018). Jika Anda telah menginstal versi modul Azure sebelumnya sebagai MSI, penginstal secara otomatis akan menghapusnya. Modul penginstalan paket MSI di `${env:ProgramFiles}\WindowsPowerShell\Modules` . Modul `AzureRM` dan `Azure` program telah diinstal.

> [!NOTE]
> Gunakan modul `Azure` hanya jika Anda bekerja dengan model penyebaran klasik Azure.

Untuk mulai bekerja dengan Azure PowerShell, Anda perlu memuat ke sesi PowerShell Anda saat ini dengan `AzureRM` cmdlet [Import-Module,](/powershell/module/Microsoft.PowerShell.Core/Import-Module) lalu masuk dengan kredensial Azure Anda.

```powershell-interactive
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

Anda harus mengulangi langkah-langkah ini untuk setiap sesi PowerShell baru yang anda mulai. Mengimpor modul secara `AzureRM` otomatis memerlukan penyiapan profil PowerShell, yang dapat Anda pelajari di Tentang [Profil](/powershell/module/microsoft.powershell.core/about/about_profiles).
Untuk mempelajari cara tetap masuk ke Azure di seluruh sesi, lihat Tetap [menggunakan kredensial pengguna di seluruh sesi PowerShell.](context-persistence.md)

## <a name="install-or-update-on-windows-using-the-web-platform-installer"></a>Menginstal atau memperbarui Windows menggunakan Penginstal Platform Web

Unduh paket [Azure PowerShell WebPI](https://aka.ms/webpi-azps) Anda dan mulai menginstal. Jika Anda telah menginstal versi modul Azure sebelumnya dari MSI atau dengan WebPI, penginstal akan menghapusnya secara otomatis. Modul diinstal ke `${env:ProgramFiles}\WindowsPowerShell\Modules` dalam . Modul `AzureRM` dan `Azure` program telah diinstal.

> [!NOTE]
> Gunakan modul `Azure` hanya jika Anda bekerja dengan model penyebaran klasik Azure.

Untuk mulai bekerja dengan Azure PowerShell, Anda perlu memuat ke sesi PowerShell Anda saat ini dengan `AzureRM` cmdlet [Import-Module,](/powershell/module/Microsoft.PowerShell.Core/Import-Module) lalu masuk dengan kredensial Azure Anda.

```powershell-interactive
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

Anda harus mengulangi langkah-langkah ini untuk setiap sesi PowerShell baru yang anda mulai. Mengimpor modul secara `AzureRM` otomatis memerlukan penyiapan profil PowerShell, yang dapat Anda pelajari di Tentang [Profil](/powershell/module/microsoft.powershell.core/about/about_profiles).
Untuk mempelajari cara tetap masuk ke Azure di seluruh sesi, lihat Tetap [menggunakan kredensial pengguna di seluruh sesi PowerShell.](context-persistence.md)
