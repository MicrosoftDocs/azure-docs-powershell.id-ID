---
title: Menginstal Azure PowerShell di Windows dengan PowerShellGet
description: Cara menginstal Azure PowerShell dengan PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/15/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: c03c6ee3782b68de8a237b3c215405ff6513dbca
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421094"
---
# <a name="install-azure-powershell-on-windows-with-powershellget"></a>Menginstal Azure PowerShell di Windows dengan PowerShellGet

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini menjelaskan langkah-langkah untuk menginstal modul Azure PowerShell untuk PowerShell 5.x untuk Windows menggunakan PowerShellGet. Manajemen modul dan PowerShellGet adalah cara yang lebih disukai untuk menginstal Azure PowerShell tetapi jika Anda lebih suka menginstal dengan Penginstal Platform Web atau paket MSI, lihat [Metode penginstalan lainnya](other-install.md).

Model penyebaran klasik Azure tidak didukung oleh versi uji Azure PowerShell. Untuk dukungan untuk penyebaran klasik, ikuti instruksi dalam [Menginstal Azure PowerShell Manajemen Layanan .](/powershell/azure/servicemanagement/install-azure-ps)

> [!IMPORTANT]
> Modul AzureRM tidak didukung untuk macOS atau Linux. Untuk menggunakan Azure PowerShell cmdlets mengenai platform ini, [Instal modul Az](/powershell/azure/install-az-ps).

## <a name="requirements"></a>Persyaratan

Untuk menginstal Azure PowerShell, Anda memerlukan PowerShellGet versi 1.1.2.0 atau yang lebih tinggi. Untuk memeriksa apakah tersedia di sistem Anda, jalankan perintah berikut:

```powershell-interactive
Get-InstalledModule -Name PowerShellGet -AllVersions | Select-Object -Property Name,Version,Path
```

Anda akan melihat sesuatu yang mirip dengan output berikut:

```output
Name          Version Path
----          ------- ----
Name          Version Path
----          ------- ----
PowerShellGet 1.6.0   C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.6.0\PowerShellGet.psd1
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

Jika Anda perlu memperbarui instalasi PowerShellGet, jalankan perintah berikut ini:

```powershell-interactive
Install-Module PowerShellGet -Force
```

Jika tidak memiliki instalasi PowerShellGet, ikuti instruksi dalam tabel di bawah ini untuk sistem Anda.

|Skenario|Instruksi instalasi|
|---|---|
|Windows 10<br/>Windows Server 2016|Disertakan dalam Windows Management Framework (WMF) 5.0 yang disertakan di OS|
|Memutakhirkan ke PowerShell 5| <ol><li>[Instal versi terbaru WMF](https://www.microsoft.com/download/details.aspx?id=54616)</li><li>Jalankan perintah berikut:<br/>```Install-Module PowerShellGet -Force```</li></ol>|

> [!NOTE]
> Menggunakan PowerShellGet memerlukan Kebijakan Eksekusi yang memungkinkan Anda menjalankan skrip. Untuk informasi selengkapnya tentang Kebijakan Eksekusi PowerShell, lihat [Tentang Kebijakan Eksekusi](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
>
> [!IMPORTANT]
> Modul yang dijelaskan dalam dokumen ini, AzureRM, menggunakan .NET Framework. Hal ini membuatnya tidak kompatibel dengan PowerShell 6.0, yang menggunakan .NET Core. Jika Anda menggunakan PowerShell 6.0, ikuti instruksi [instalasi untuk macOS dan Linux](/powershell/azure/install-az-ps).

## <a name="install-the-azure-powershell-module"></a>Menginstal modul Azure PowerShell

Anda memerlukan hak istimewa yang tinggi untuk menginstal modul dari Galeri PowerShell. Untuk menginstal Azure PowerShell, jalankan perintah berikut dalam sesi yang ditingkatkan:

```powershell-interactive
Install-Module -Name AzureRM
```

> [!NOTE]
> Jika Memiliki versi NuGet yang lebih lama dari 2.8.5.201, Anda akan diminta untuk mengunduh dan menginstal versi terbaru NuGet.

Secara default, galeri PowerShell tidak dikonfigurasi sebagai penyimpanan tepercaya untuk PowerShellGet. Saat pertama kali menggunakan PSGallery Anda melihat perintah berikut ini:

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Jawab `Yes` `Yes to All` atau lanjutkan dengan penginstalan.

Modul `AzureRM` ini adalah modul rollup untuk Azure PowerShell cmdlet. Menginstalnya akan mengunduh semua modul Azure Resource Manager yang tersedia, dan membuat cmdlet mereka tersedia untuk digunakan.

## <a name="sign-in"></a>Tandatangan

Untuk mulai bekerja dengan Azure PowerShell, Anda perlu memuat ke sesi PowerShell Anda saat ini dengan `AzureRM` cmdlet [Import-Module,](/powershell/module/Microsoft.PowerShell.Core/Import-Module) lalu masuk dengan kredensial Azure Anda.

```powershell-interactive
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

Anda harus mengulangi langkah-langkah ini untuk setiap sesi PowerShell baru yang anda mulai. Mengimpor modul secara `AzureRM` otomatis memerlukan penyiapan profil PowerShell, yang dapat Anda pelajari di Tentang [Profil](/powershell/module/microsoft.powershell.core/about/about_profiles).
Untuk mempelajari cara tetap masuk ke Azure di seluruh sesi, lihat Tetap [menggunakan kredensial pengguna di seluruh sesi PowerShell.](context-persistence.md)

## <a name="update-the-azure-powershell-module"></a>Memperbarui Azure PowerShell otomatis

Anda bisa memperbarui instalasi Azure PowerShell Anda dengan menjalankan [Update-Module](/powershell/module/powershellget/update-module). Perintah ini tidak __menghapus__ instalan versi yang lebih lama.

```powershell-interactive
Update-Module -Name AzureRM
```

Jika Anda ingin menghapus versi komputer yang lebih Azure PowerShell dari sistem, lihat [Menghapus instalan Azure PowerShell modul](uninstall-azurerm-ps.md).

## <a name="use-multiple-versions-of-azure-powershell"></a>Menggunakan beberapa versi Azure PowerShell

Anda dapat menginstal beberapa versi Azure PowerShell. Anda mungkin memerlukan lebih dari satu versi jika bekerja dengan sumber daya Azure Stack lokal, menjalankan versi Windows yang lebih lama yang tidak dapat diperbarui ke PowerShell 5.0, atau menggunakan model penyebaran klasik Azure. Untuk menginstal versi yang lebih lama, berikan `-RequiredVersion` argumen saat menginstal.

```powershell-interactive
# Install version 2.3.0 of Azure PowerShell
Install-Module -Name AzureRM -RequiredVersion 2.3.0
```

Saat memuat modul Azure PowerShell, versi terbaru dimuat secara default. Untuk memuat versi yang berbeda, sediakan `-RequiredVersion` argumennya.

```powershell-interactive
# Load version 2.3.0 of Azure PowerShell
Import-Module -Name AzureRM -RequiredVersion 2.3.0
```

## <a name="provide-feedback"></a>Berikan umpan balik

Jika menemukan bug ketika menggunakan Azure Powershell, silakan [mengajukan masalah di GitHub](https://github.com/Azure/azure-powershell/issues).
Untuk memberikan umpan balik dari baris perintah, gunakan cmdlet [Kirim-Umpan](/powershell/module/azurerm.profile/send-feedback) Balik.

## <a name="next-steps"></a>Langkah Berikutnya

Untuk mulai menggunakan Azure PowerShell, [lihat Mulai dengan Azure PowerShell](get-started-azureps.md) untuk mempelajari selengkapnya tentang modul dan fiturnya.
