---
title: Menginstal Azure PowerShell di Windows dengan PowerShellGet
description: Cara menginstal Azure PowerShell dengan PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: d8cf94e63268396ffa42192fef5f5ef1da91c586
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429358"
---
# <a name="install-azure-powershell-on-windows-with-powershellget"></a>Menginstal Azure PowerShell di Windows dengan PowerShellGet

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini menjelaskan langkah-langkah untuk menginstal modul Azure PowerShell untuk PowerShell 5.x untuk Windows menggunakan PowerShellGet. PowerShellGet dan manajemen modul adalah cara yang lebih disukai untuk menginstal Azure PowerShell tetapi jika Anda lebih suka menginstal dengan Installer Platform Web atau paket MSI, lihat [Metode penginstalan lainnya](other-install.md).

Model penyebaran klasik Azure tidak didukung oleh versi Azure PowerShell ini. Untuk dukungan untuk penyebaran klasik, ikuti petunjuk di [Menginstal modul Manajemen Layanan Azure PowerShell](/powershell/azure/servicemanagement/install-azure-ps).

> [!IMPORTANT]
> Modul AzureRM tidak didukung untuk macOS atau Linux. Untuk menggunakan cmdlet Azure PowerShell pada platform ini, [Instal modul Az](/powershell/azure/install-az-ps).

## <a name="requirements"></a>Persyaratan

Memulai dengan Azure PowerShell versi 6.0, Azure PowerShell memerlukan PowerShell versi 5.0. Untuk memeriksa versi PowerShell yang berjalan di komputer Anda, jalankan perintah berikut:

```powershell
$PSVersionTable.PSVersion
```

Jika Anda memiliki versi yang lama, lihat [Memperbarui Windows PowerShell yang sudah ada](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).

> [!IMPORTANT]
> Modul yang dijelaskan dalam dokumen ini, AzureRM, menggunakan .NET Framework. Ini membuatnya tidak kompatibel dengan PowerShell 6.0, yang menggunakan .NET Core. Jika Anda menggunakan PowerShell 6.0, ikuti [petunjuk penginstalan untuk macOS dan Linux](/powershell/azure/install-az-ps).

## <a name="install-the-azure-powershell-module"></a>Menginstal modul Azure PowerShell

Anda memerlukan peningkatan hak istimewa untuk menginstal modul dari Galeri PowerShell. Untuk menginstal Azure PowerShell, jalankan perintah berikut di peningkatan sesi:

```azurepowershell
Install-Module -Name AzureRM -AllowClobber
```

> [!NOTE]
> Jika Anda memiliki versi NuGet yang lebih lama dari 2.8.5.201, Anda akan diminta untuk mengunduh dan menginstal NuGet versi terbaru.

Secara default, galeri PowerShell tidak dikonfigurasi sebagai repositori tepercaya untuk PowerShellGet. Pertama kali Anda menggunakan PSGallery, Anda akan melihat perintah berikut:

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Jawab `Yes` atau `Yes to All` untuk melanjutkan pemasangan.

Modul `AzureRM` ini adalah modul rollup untuk cmdlet Azure PowerShell. Memasangnya berarti mengunduh semua modul Azure Resource Manager yang tersedia, dan membuat cmdlet-nya tersedia untuk digunakan.

## <a name="sign-in"></a>Masuk

Untuk mulai bekerja dengan Azure PowerShell, masuk dengan info masuk Azure Anda.

```azurepowershell
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

> [!NOTE]
> Jika Anda telah menonaktifkan pemuatan otomatis modul, Anda harus mengimpor modul secara manual dengan `Import-Module AzureRM`. Karena cara modul disusun, ini bisa memakan waktu beberapa detik.

Anda harus mengulangi langkah-langkah ini untuk setiap sesi PowerShell baru yang Anda mulai. Untuk mempelajari cara mempertahankan masuk Azure Anda di seluruh sesi PowerShell, lihat [Mempertahankan info masuk pengguna di seluruh sesi PowerShell](context-persistence.md).

## <a name="update-the-azure-powershell-module"></a>Memperbarui modul Azure PowerShell

Anda dapat memperbarui penginstalan Azure PowerShell Anda dengan menjalankan [Update-Module](/powershell/module/powershellget/update-module). Perintah ini **tidak** menghapus instalan versi sebelumnya.

```powershell
Update-Module -Name AzureRM
```

Jika Anda ingin menghapus versi Azure PowerShell yang lebih lama dari sistem Anda, lihat [Modul Menghapus instalan Azure PowerShell](uninstall-azurerm-ps.md).

## <a name="use-multiple-versions-of-azure-powershell"></a>Menggunakan beberapa versi Azure PowerShell

Anda dapat menginstal lebih dari satu versi Azure PowerShell. Untuk memeriksa apakah Anda telah menginstal beberapa versi Azure PowerShell, gunakan perintah berikut:

```powershell
Get-InstalledModule -Name AzureRM -AllVersions |
  Select-Object -Property Name, Version
```

Untuk menghapus versi Azure PowerShell, lihat [Modul Menghapus instalan Azure PowerShell](uninstall-azurerm-ps.md).

Anda mungkin memerlukan lebih dari satu versi jika Anda bekerja dengan sumber daya Azure Stack lokal, jalankan versi Windows yang lebih lama, atau gunakan model penyebaran klasik Azure. Untuk menginstal versi yang lebih lama, berikan argumen `-RequiredVersion` saat menginstal.

```powershell
# Install version 2.3.0 of Azure PowerShell
Install-Module -Name AzureRM -RequiredVersion 2.3.0
```

Saat memuat modul Azure PowerShell, versi terbaru dimuat secara default. Untuk memuat versi yang berbeda, tentukan parameter `RequiredVersion`.

```powershell
# Load version 2.3.0 of Azure PowerShell
Import-Module -Name AzureRM -RequiredVersion 2.3.0
```

## <a name="provide-feedback"></a>Berikan umpan balik

Jika Anda menemukan bug saat menggunakan Azure Powershell, [ajukan masalah di GitHub](https://github.com/Azure/azure-powershell/issues). Untuk memberikan umpan balik dari baris perintah, gunakan cmdlet [Send-Feedback](/powershell/module/azurerm.profile/send-feedback).

## <a name="next-steps"></a>Langkah berikutnya

Untuk memulai menggunakan Azure PowerShell, lihat [Memulai dengan Azure PowerShell](get-started-azureps.md) untuk mempelajari selengkapnya tentang modul dan fiturnya.
