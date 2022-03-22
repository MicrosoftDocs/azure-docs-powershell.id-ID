---
title: Cara lain untuk menginstal Azure PowerShell
description: Cara menginstal Azure PowerShell tanpa PowerShellGet menggunakan MSI
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 91ef655591aade9a9a640d1e72503bdd147251fa
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429354"
---
# <a name="install-azure-powershell-on-windows-with-msi"></a>Menginstal Azure PowerShell di Windows dengan MSI

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini menjelaskan cara menginstal Azure PowerShell di Windows menggunakan penginstal MSI. Gunakan metode penginstalan ini hanya jika metode ini diperlukan untuk sistem Anda. Cara yang disarankan untuk menginstal Azure PowerShell di Windows adalah dengan PowerShellGet. Untuk petunjuk tentang menggunakan PowerShellGet untuk menginstal Azure PowerShell, lihat [Menginstal Azure PowerShell dengan PowerShellGet](install-azurerm-ps.md).

> [!NOTE]
> Metode Penginstal Platform Web pada penginstalan tidak lagi tersedia untuk versi Azure PowerShell 6.x dan yang lebih tinggi. Jika Anda memerlukan penggunaan Penginstal Platform Web, silakan pertimbangkan menggunakan MSI sebagai gantinya, atau Anda dapat menginstal versi Azure PowerShell yang lebih lama.

## <a name="install-or-update-on-windows-using-the-msi-package"></a>Menginstal atau memperbarui di Windows menggunakan Paket MSI

Azure PowerShell untuk Windows PowerShell 5.x dapat diinstal menggunakan file MSI yang tersedia dari [GitHub](https://github.com/Azure/azure-powershell/releases/tag/v6.13.1-November2018). Jika Anda telah menginstal versi modul Azure sebelumnya sebagai MSI, penginstal akan menghapusnya secara otomatis.
Paket MSI menginstal modul di `${env:ProgramFiles}\WindowsPowerShell\Modules`. Baik modul `AzureRM` maupun `Azure` diinstal.

> [!NOTE]
> Hanya gunakan modul `Azure` jika Anda bekerja dengan model penyebaran klasik Azure.

Untuk mulai bekerja dengan Azure PowerShell, masuk dengan info masuk Azure Anda.

```azurepowershell
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

> [!NOTE]
> Jika Anda telah menonaktifkan pemuatan otomatis modul, Anda harus mengimpor modul secara manual dengan `Import-Module -Name AzureRM`. Karena cara modul disusun, ini bisa memakan waktu beberapa detik.

Anda harus mengulangi langkah ini untuk setiap sesi PowerShell baru yang Anda mulai. Untuk mempelajari cara mempertahankan masuk Azure Anda di seluruh sesi PowerShell, lihat [Mempertahankan info masuk pengguna di seluruh sesi PowerShell](context-persistence.md).
