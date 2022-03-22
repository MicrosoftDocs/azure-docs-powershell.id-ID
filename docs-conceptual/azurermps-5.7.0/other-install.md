---
title: Cara lain untuk menginstal Azure PowerShell
description: Cara menginstal Azure PowerShell tanpa PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/20/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 7148188603e84efbcd784264de4c78819edf6833
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422890"
---
# <a name="install-azure-powershell-on-windows-with-msi-or-web-platform-installer"></a>Menginstal Azure PowerShell di Windows dengan MSI atau Penginstal Platform Web

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini menjelaskan cara menginstal Azure PowerShell di Windows menggunakan MSI atau Penginstal Platform Web (Windows).
Gunakan metode penginstalan ini hanya jika metode ini diperlukan untuk sistem Anda. Cara yang disarankan untuk menginstal Azure PowerShell di Windows adalah dengan PowerShellGet. Untuk petunjuk tentang menggunakan PowerShellGet untuk menginstal Azure PowerShell, lihat [Menginstal Azure PowerShell dengan PowerShellGet](install-azurerm-ps.md).

## <a name="install-or-update-on-windows-using-the-msi-package"></a>Menginstal atau memperbarui di Windows menggunakan Paket MSI

Azure PowerShell dapat diinstal menggunakan file MSI yang tersedia dari [GitHub](https://github.com/Azure/azure-powershell/releases/tag/v5.7.0-April2018). Jika Anda telah menginstal versi modul Azure sebelumnya sebagai MSI, penginstal akan menghapusnya secara otomatis. Paket MSI menginstal modul di `${env:ProgramFiles}\WindowsPowerShell\Modules`. Baik modul `AzureRM` maupun `Azure` diinstal.

> [!NOTE]
> Hanya gunakan modul `Azure` jika Anda bekerja dengan model penyebaran klasik Azure.

Untuk mulai menggunakan Azure PowerShell, Anda perlu memuat `AzureRM` ke sesi PowerShell saat ini dengan cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), lalu masuk dengan kredensial Azure Anda.

```powershell-interactive
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

Anda harus mengulangi langkah-langkah ini untuk setiap sesi PowerShell baru yang Anda mulai. Untuk mengimpor modul `AzureRM` secara otomatis, Anda harus mengatur profil PowerShell, yang dapat dipelajari di [Tentang Profil](/powershell/module/microsoft.powershell.core/about/about_profiles).
Untuk mempelajari cara mempertahankan info masuk Azure di seluruh sesi, lihat [Mempertahankan kredensial pengguna di seluruh sesi PowerShell](context-persistence.md).

## <a name="install-or-update-on-windows-using-the-web-platform-installer"></a>Menginstal atau memperbarui di Windows menggunakan Alat Penginstal Platform Web

Unduh [paket Webpi Azure PowerShell](https://aka.ms/webpi-azps) dan mulai penginstalan. Jika Anda telah menginstal versi modul Azure sebelumnya dari MSI atau dengan WebPI, penginstal akan menghapusnya secara otomatis. Modul diinstal ke dalam `${env:ProgramFiles}\WindowsPowerShell\Modules`. Baik modul `AzureRM` maupun `Azure` diinstal.

> [!NOTE]
> Hanya gunakan modul `Azure` jika Anda bekerja dengan model penyebaran klasik Azure.

Untuk mulai menggunakan Azure PowerShell, Anda perlu memuat `AzureRM` ke sesi PowerShell saat ini dengan cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), lalu masuk dengan kredensial Azure Anda.

```powershell-interactive
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

Anda harus mengulangi langkah-langkah ini untuk setiap sesi PowerShell baru yang Anda mulai. Untuk mengimpor modul `AzureRM` secara otomatis, Anda harus mengatur profil PowerShell, yang dapat dipelajari di [Tentang Profil](/powershell/module/microsoft.powershell.core/about/about_profiles).
Untuk mempelajari cara mempertahankan info masuk Azure di seluruh sesi, lihat [Mempertahankan kredensial pengguna di seluruh sesi PowerShell](context-persistence.md).
