---
title: Menginstal dan mengonfigurasi Azure PowerShell | Microsoft Docs
description: Cara menginstal dan mengonfigurasi Azure PowerShell untuk penggunaan pertama kali.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/27/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: c4aa030a7d95f5b22ceeff9438af506ced5c8cb5
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423165"
---
# <a name="install-azure-powershell-on-windows-with-powershellget"></a>Menginstal Azure PowerShell di Windows dengan PowerShellGet

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini menjelaskan langkah-langkah untuk menginstal modul Azure PowerShell untuk PowerShell 5.x untuk Windows menggunakan PowerShellGet. PowerShellGet dan manajemen modul adalah cara yang lebih disukai untuk menginstal Azure PowerShell tetapi jika Anda lebih suka menginstal dengan Installer Platform Web atau paket MSI, lihat [Metode penginstalan lainnya](other-install.md).

Model penyebaran klasik Azure tidak didukung oleh versi Azure PowerShell ini. Untuk dukungan untuk penyebaran klasik, ikuti petunjuk di [Menginstal modul Manajemen Layanan Azure PowerShell](/powershell/azure/servicemanagement/install-azure-ps).

> [!IMPORTANT]
> Modul AzureRM tidak didukung untuk macOS atau Linux. Untuk menggunakan cmdlet Azure PowerShell pada platform ini, [Instal modul Az](/powershell/azure/install-az-ps).

## <a name="step-1-install-powershellget"></a>Langkah 1: Instal PowerShellGet

Menginstal item dari Galeri PowerShell memerlukan modul PowerShellGet. Pastikan Anda memiliki versi PowerShellGet yang sesuai dan persyaratan sistem lainnya. Jalankan perintah berikut untuk melihat apakah Anda telah menginstal PowerShellGet di sistem Anda.


```powershell-interactive
Get-InstalledModule -Name PowerShellGet -ListAvailable | Select-Object -Property Name,Version,Path
```

Sekarang, Anda akan melihat sesuatu yang mirip dengan output berikut:

```Output
Name          Version Path
----          ------- ----
Name          Version Path
----          ------- ----
PowerShellGet 1.6.0   C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.6.0\PowerShellGet.psd1
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

Anda memerlukan PowerShellGet versi 1.1.2.0 atau lebih tinggi. Untuk memperbarui PowerShellGet, gunakan perintah berikut:

```powershell-interactive
Install-Module PowerShellGet -Force
```

Jika Anda tidak menginstal PowerShellGet, lihat bagian [Cara mendapatkan PowerShellGet](#how-to-get-powershellget) di artikel ini.

> [!NOTE]
> Menggunakan PowerShellGet memerlukan Kebijakan Eksekusi yang memungkinkan Anda menjalankan skrip. Untuk informasi selengkapnya tentang Kebijakan Eksekusi PowerShell, lihat [Tentang Kebijakan Eksekusi](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
>
> [!IMPORTANT]
> Modul yang dijelaskan dalam dokumen ini, AzureRM, menggunakan .NET Framework. Ini membuatnya tidak kompatibel dengan PowerShell 6.0, yang menggunakan .NET Core. Jika Anda menggunakan PowerShell 6.0, ikuti [petunjuk penginstalan untuk macOS dan Linux](/powershell/azure/install-az-ps).

## <a name="step-2-install-azure-powershell"></a>Langkah 2: Instal Azure PowerShell

Menginstal Azure PowerShell dari Galeri PowerShell memerlukan hak istimewa yang ditinggikan. Jalankan perintah berikut dari sesi PowerShell yang ditinggikan:

```powershell-interactive
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module -Name AzureRM -AllowClobber
```

Secara default, galeri PowerShell tidak dikonfigurasi sebagai Repositori tepercaya untuk PowerShellGet. Pertama kali Anda menggunakan PSGallery, Anda akan melihat perintah berikut:

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
```

Jawab 'Ya' atau 'Ya untuk Semua' untuk melanjutkan penginstalan.

> [!NOTE]
> Jika Anda memiliki versi NuGet yang lebih lama dari 2.8.5.201, Anda akan diminta untuk mengunduh dan menginstal NuGet versi terbaru.

Modul AzureRM adalah modul rollup untuk cmdlet Azure Resource Manager. Saat Anda menginstal modul AzureRM, modul Azure PowerShell apa pun yang sebelumnya tidak diinstal diunduh dan dari Galeri PowerShell.

Jika Anda memiliki versi Azure PowerShell sebelumnya yang diinstal, Anda mungkin menerima kesalahan. Untuk mengatasi masalah ini, lihat bagian [Memperbarui ke versi baru Azure PowerShell](#update-azps) artikel ini.

## <a name="step-3-load-the-azurerm-module"></a>Langkah 3: Muat modul AzureRM

Setelah modul diinstal, Anda perlu memuat modul ke sesi PowerShell Anda. Anda harus melakukan ini dalam sesi PowerShell normal (tidak ditinggikan). Modul dimuat menggunakan cmdlet `Import-Module`, sebagai berikut:

```powershell-interactive
Import-Module -Name AzureRM
```

## <a name="next-steps"></a>Langkah berikutnya

Untuk informasi selengkapnya tentang menggunakan Azure PowerShell, lihat artikel berikut ini:

* [Mulai menggunakan Azure PowerShell](get-started-azureps.md)

## <a name="reporting-issues-and-feedback"></a>Melaporkan masalah dan umpan balik

Jika Anda menemukan bug dengan alat ini, ajukan masalah di bagian [Masalah](https://github.com/Azure/azure-powershell/issues) di repo GitHub kami. Untuk memberikan umpan balik dari baris perintah, gunakan cmdlet `Send-Feedback`.

## <a name="frequently-asked-questions"></a>Tanya jawab umum

### <a name="how-to-get-powershellget"></a>Cara mendapatkan PowerShellGet

|Versi OS|Intruksi penginstalan|
|---|---|
|Saya memiliki Windows 10 atau Windows Server 2016|Dibuat ke dalam Windows Management Framework (WMF) 5.0 termasuk dalam OS|
|Saya ingin meningkatkan ke PowerShell 5|[Menginstal WMF versi terbaru](https://www.microsoft.com/download/details.aspx?id=54616)|

### <a name="div-idhelpmechoosechecking-the-version-of-azure-powershell"></a><div id="helpmechoose"/>Memeriksa versi Azure PowerShell

Meskipun kami mendorong Anda untuk meningkatkan ke versi terbaru sedini mungkin, beberapa versi Azure PowerShell didukung. Untuk menentukan versi Azure PowerShell yang telah Anda instal, jalankan `Get-InstalledModule AzureRM` dari baris perintah Anda.

```powershell-interactive
Get-InstalledModule AzureRM -AllVersions | Select-Object -Property Name,Version,Path
```

### <a name="support-for-classic-deployment-methods"></a>Dukungan untuk metode penyebaran klasik

Jika Anda memiliki penyebaran yang menggunakan model penyebaran klasik, Anda dapat menginstal versi Manajemen Layanan Azure PowerShell. Untuk informasi selengkapnya, lihat [Menginstal modul Azure PowerShell Service Management](/powershell/azure/servicemanagement/install-azure-ps). Modul Azure dan AzureRM berbagi dependensi umum. Jika menggunakan modul Azure dan AzureRM, Anda harus menginstal versi yang sama dari setiap paket.

### <a name="div-idupdate-azpsupdating-to-a-new-version-of-azure-powershell"></a><div id="update-azps"/>Memperbarui ke versi baru Azure PowerShell

Jika memiliki versi Azure PowerShell sebelumnya yang diinstal yang mencakup modul Manajemen Layanan, Anda mungkin menerima kesalahan berikut:

```Output
PackageManagement\Install-Package : A command with name 'Get-AzureStorageContainerAcl' is already
available on this system. This module 'Azure.Storage' may override the existing commands. If you
still want to install this module 'Azure.Storage', use -AllowClobber parameter.

At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1772 char:21
+ ...          $null = PackageManagement\Install-Package @PSBoundParameters
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (Microsoft.Power....InstallPackage:InstallPackage) [Install-Package], Exception
    + FullyQualifiedErrorId : CommandAlreadyAvailable,Validate-ModuleCommandAlreadyAvailable,Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage
```

Seperti yang dinyatakan oleh pesan kesalahan, Anda perlu menggunakan parameter -AllowClobber untuk menginstal modul. Gunakan perintah berikut:

```powershell-interactive
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module -Name AzureRM -AllowClobber
```

Untuk informasi selengkapnya, lihat topik bantuan untuk [Install-Module](/powershell/module/powershellget/install-module).

### <a name="installing-module-versions-side-by-side"></a>Menginstal versi modul berdampingan

Metode penginstalan PowerShellGet adalah satu-satunya metode yang mendukung penginstalan beberapa versi. Misalnya, Anda mungkin memiliki skrip yang ditulis menggunakan versi Azure PowerShell sebelumnya yang tidak memiliki waktu atau sumber daya untuk diperbarui. Perintah berikut mengilustrasikan cara menginstal beberapa versi Azure PowerShell:

```powershell-interactive
Install-Module -Name AzureRM -RequiredVersion 3.7.0
Install-Module -Name AzureRM -RequiredVersion 2.3.0
```

Hanya satu versi modul yang dapat dimuat dalam sesi PowerShell. Anda harus membuka jendela PowerShell baru dan menggunakan `Import-Module` untuk mengimpor versi tertentu dari cmdlet AzureRM:

```powershell-interactive
Import-Module -Name AzureRM -RequiredVersion 2.3.0
```

> [!NOTE]
> Versi 2.1.0 dan versi 1.2.6 adalah versi modul pertama yang dirancang untuk diinstal dan digunakan berdampingan. Saat memuat versi Azure PowerShell yang lebih lama, versi modul **AzureRM.Profile** yang tidak kompatibel dimuat. Ini mengakibatkan cmdlet mendorong Anda untuk masuk setiap kali Anda mengeksekusi cmdlet.

### <a name="other-installation-methods"></a>Metode penginstalan lainnya

Untuk informasi tentang menginstal menggunakan Penginstal Platform Web atau Paket MSI, lihat [Metode penginstalan lainnya](other-install.md)