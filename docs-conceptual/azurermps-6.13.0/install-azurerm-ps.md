---
title: Menginstal Azure PowerShell di Windows dengan PowerShellGet
description: Cara menginstal Azure PowerShell dengan PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: d8cf94e63268396ffa42192fef5f5ef1da91c586
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429358"
---
# <a name="install-azure-powershell-on-windows-with-powershellget"></a>Menginstal Azure PowerShell di Windows dengan PowerShellGet

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini menjelaskan langkah-langkah untuk menginstal modul Azure PowerShell untuk PowerShell 5.x untuk Windows menggunakan PowerShellGet. Manajemen modul dan PowerShellGet adalah cara yang lebih disukai untuk menginstal Azure PowerShell tetapi jika Anda lebih suka menginstal dengan Penginstal Platform Web atau paket MSI, lihat [Metode penginstalan lainnya](other-install.md).

Model penyebaran klasik Azure tidak didukung oleh versi uji coba Azure PowerShell. Untuk dukungan untuk penyebaran klasik, ikuti instruksi dalam [Menginstal modul Azure PowerShell Manajemen Layanan](/powershell/azure/servicemanagement/install-azure-ps).

> [!IMPORTANT]
> Modul AzureRM tidak didukung untuk macOS atau Linux. Untuk menggunakan Azure PowerShell cmdlet pada platform ini, [Instal modul Az](/powershell/azure/install-az-ps).

## <a name="requirements"></a>Persyaratan

Dimulai dengan Azure PowerShell 6.0, Azure PowerShell memerlukan PowerShell versi 5.0. Untuk memeriksa versi PowerShell yang berjalan di komputer, jalankan perintah berikut:

```powershell
$PSVersionTable.PSVersion
```

Jika Anda memiliki versi usang, lihat [Memutakhirkan versi yang sudah Windows PowerShell](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).

> [!IMPORTANT]
> Modul yang dijelaskan dalam dokumen ini, AzureRM, menggunakan .NET Framework. Hal ini membuatnya tidak kompatibel dengan PowerShell 6.0, yang menggunakan .NET Core. Jika Anda menggunakan PowerShell 6.0, ikuti instruksi [instalasi untuk macOS dan Linux](/powershell/azure/install-az-ps).

## <a name="install-the-azure-powershell-module"></a>Menginstal modul Azure PowerShell

Anda memerlukan hak istimewa yang tinggi untuk menginstal modul dari Galeri PowerShell. Untuk menginstal Azure PowerShell, jalankan perintah berikut dalam sesi yang ditinggikan:

```azurepowershell
Install-Module -Name AzureRM -AllowClobber
```

> [!NOTE]
> Jika Memiliki versi NuGet yang lebih lama dari 2.8.5.201, Anda akan diminta untuk mengunduh dan menginstal versi terbaru NuGet.

Secara default, galeri PowerShell tidak dikonfigurasi sebagai penyimpanan tepercaya untuk PowerShellGet. Saat pertama kali menggunakan PSGallery Anda melihat perintah berikut ini:

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Jawab `Yes` `Yes to All` atau lanjutkan dengan penginstalan.

Modul `AzureRM` ini adalah modul rollup untuk cmdlet Azure PowerShell baru. Menginstalnya akan mengunduh semua modul Azure Resource Manager yang tersedia, dan membuat cmdlet mereka tersedia untuk digunakan.

## <a name="sign-in"></a>Tandatangan

Untuk mulai bekerja dengan Azure PowerShell, masuk dengan kredensial Azure Anda.

```azurepowershell
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

> [!NOTE]
> Jika Anda telah menonaktifkan muatan otomatis modul, Anda perlu mengimpor modul secara manual dengan `Import-Module AzureRM` . Karena cara modul disusun, ini dapat memakan waktu beberapa detik.

Anda harus mengulangi langkah-langkah ini untuk setiap sesi PowerShell baru yang anda mulai. Untuk mempelajari cara tetap masuk ke Azure di seluruh sesi PowerShell, lihat Tetap [menggunakan kredensial pengguna di seluruh sesi PowerShell.](context-persistence.md)

## <a name="update-the-azure-powershell-module"></a>Memperbarui modul Azure PowerShell

Anda bisa memperbarui instalasi Azure PowerShell Anda dengan menjalankan [Update-Module](/powershell/module/powershellget/update-module). Perintah ini tidak **menghapus** instalan versi yang lebih lama.

```powershell
Update-Module -Name AzureRM
```

Jika Anda ingin menghapus versi aplikasi yang lebih Azure PowerShell dari sistem Anda, lihat [Menghapus Azure PowerShell modul](uninstall-azurerm-ps.md).

## <a name="use-multiple-versions-of-azure-powershell"></a>Menggunakan beberapa versi Azure PowerShell

Anda dapat menginstal lebih dari satu versi Azure PowerShell. Untuk memeriksa apakah Anda memiliki beberapa versi Azure PowerShell diinstal, gunakan perintah berikut:

```powershell
Get-InstalledModule -Name AzureRM -AllVersions |
  Select-Object -Property Name, Version
```

Untuk menghapus versi yang Azure PowerShell, lihat [Menghapus instalan Azure PowerShell modul](uninstall-azurerm-ps.md).

Anda mungkin memerlukan lebih dari satu versi jika bekerja dengan sumber daya Azure Stack lokal, menjalankan versi Windows yang lebih lama, atau menggunakan model penyebaran klasik Azure. Untuk menginstal versi yang lebih lama, berikan `-RequiredVersion` argumen saat menginstal.

```powershell
# Install version 2.3.0 of Azure PowerShell
Install-Module -Name AzureRM -RequiredVersion 2.3.0
```

Saat memuat modul Azure PowerShell, versi terbaru dimuat secara default. Untuk memuat versi yang berbeda, tentukan `RequiredVersion` parameter.

```powershell
# Load version 2.3.0 of Azure PowerShell
Import-Module -Name AzureRM -RequiredVersion 2.3.0
```

## <a name="provide-feedback"></a>Berikan umpan balik

Jika menemukan bug saat menggunakan Azure Powershell, [terjadi masalah di GitHub](https://github.com/Azure/azure-powershell/issues). Untuk memberikan umpan balik dari baris perintah, gunakan cmdlet [Kirim-Umpan](/powershell/module/azurerm.profile/send-feedback) Balik.

## <a name="next-steps"></a>Langkah Berikutnya

Untuk mulai menggunakan Azure PowerShell, [lihat Mulai dengan Azure PowerShell](get-started-azureps.md) untuk mempelajari selengkapnya tentang modul dan fiturnya.
