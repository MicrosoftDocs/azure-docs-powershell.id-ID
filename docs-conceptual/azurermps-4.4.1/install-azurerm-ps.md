---
title: Menginstal dan mengonfigurasi Azure PowerShell | Microsoft Docs
description: Cara menginstal dan mengonfigurasi Azure PowerShell untuk penggunaan pertama.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/27/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: c4aa030a7d95f5b22ceeff9438af506ced5c8cb5
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423165"
---
# <a name="install-azure-powershell-on-windows-with-powershellget"></a>Menginstal Azure PowerShell di Windows dengan PowerShellGet

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini menjelaskan langkah-langkah untuk menginstal modul Azure PowerShell untuk PowerShell 5.x untuk Windows menggunakan PowerShellGet. Manajemen modul dan PowerShellGet adalah cara yang lebih disukai untuk menginstal Azure PowerShell tetapi jika Anda lebih suka menginstal dengan Penginstal Platform Web atau paket MSI, lihat [Metode penginstalan lainnya](other-install.md).

Model penyebaran klasik Azure tidak didukung oleh versi uji coba Azure PowerShell. Untuk dukungan untuk penyebaran klasik, ikuti instruksi dalam [Menginstal Azure PowerShell Manajemen Layanan .](/powershell/azure/servicemanagement/install-azure-ps)

> [!IMPORTANT]
> Modul AzureRM tidak didukung untuk macOS atau Linux. Untuk menggunakan Azure PowerShell cmdlets mengenai platform ini, [Instal modul Az](/powershell/azure/install-az-ps).

## <a name="step-1-install-powershellget"></a>Langkah 1: Instal PowerShellGet

Menginstal item dari Galeri PowerShell memerlukan modul PowerShellGet. Pastikan Anda memiliki versi PowerShellGet yang sesuai dan persyaratan sistem lainnya. Jalankan perintah berikut ini untuk melihat apakah PowerShellGet terinstal di sistem Anda.


```powershell-interactive
Get-InstalledModule -Name PowerShellGet -ListAvailable | Select-Object -Property Name,Version,Path
```

Anda akan melihat sesuatu yang mirip dengan output berikut:

```Output
Name          Version Path
----          ------- ----
Name          Version Path
----          ------- ----
PowerShellGet 1.6.0   C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.6.0\PowerShellGet.psd1
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

Anda memerlukan PowerShellDapatkan versi 1.1.2.0 atau yang lebih tinggi. Untuk memperbarui PowerShellGet, gunakan perintah berikut ini:

```powershell-interactive
Install-Module PowerShellGet -Force
```

Jika belum menginstal PowerShell, lihat bagian [Cara mendapatkan PowerShellGet](#how-to-get-powershellget) di artikel ini.

> [!NOTE]
> Menggunakan PowerShellGet memerlukan Kebijakan Eksekusi yang memungkinkan Anda menjalankan skrip. Untuk informasi selengkapnya tentang Kebijakan Eksekusi PowerShell, lihat [Tentang Kebijakan Eksekusi](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
>
> [!IMPORTANT]
> Modul yang diuraikan dalam dokumen ini, AzureRM, menggunakan .NET Framework. Hal ini membuatnya tidak kompatibel dengan PowerShell 6.0, yang menggunakan .NET Core. Jika Anda menggunakan PowerShell 6.0, ikuti instruksi [instalasi untuk macOS dan Linux](/powershell/azure/install-az-ps).

## <a name="step-2-install-azure-powershell"></a>Langkah 2: Instal Azure PowerShell

Menginstal Azure PowerShell dari Galeri PowerShell memerlukan hak istimewa tinggi. Jalankan perintah berikut dari sesi PowerShell yang ditingkatkan:

```powershell-interactive
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module -Name AzureRM -AllowClobber
```

Secara default, galeri PowerShell tidak dikonfigurasi sebagai penyimpanan Tepercaya untuk PowerShellGet. Saat pertama kali menggunakan PSGallery Anda melihat perintah berikut ini:

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
```

Jawab 'Ya' atau 'Ya untuk Semua' untuk melanjutkan penginstalan.

> [!NOTE]
> Jika Memiliki versi NuGet yang lebih lama dari 2.8.5.201, Anda akan diminta untuk mengunduh dan menginstal versi terbaru NuGet.

Modul AzureRM adalah modul rollup untuk cmdlet Azure Resource Manager. Saat Anda menginstal modul AzureRM, modul Azure PowerShell apa pun yang belum diinstal diunduh dan dari Galeri PowerShell.

Jika memiliki versi instalan Azure PowerShell sebelumnya, Anda mungkin akan menerima pesan kesalahan. Untuk mengatasi masalah ini, lihat [bagian Memperbarui ke versi Azure PowerShell](#update-azps) baru artikel ini.

## <a name="step-3-load-the-azurerm-module"></a>Langkah 3: Muat modul AzureRM

Setelah modul diinstal, Anda perlu memuat modul ke dalam sesi PowerShell. Anda harus melakukan ini dalam sesi PowerShell normal (non-tinggi). Modul dimuat menggunakan `Import-Module` cmdlet, seperti berikut:

```powershell-interactive
Import-Module -Name AzureRM
```

## <a name="next-steps"></a>Langkah Berikutnya

Untuk informasi selengkapnya tentang penggunaan Azure PowerShell, lihat artikel berikut ini:

* [Mulai menggunakan Azure PowerShell](get-started-azureps.md)

## <a name="reporting-issues-and-feedback"></a>Melaporkan masalah dan umpan balik

Jika Anda menemukan bug dengan alat, masalah file di bagian [Masalah](https://github.com/Azure/azure-powershell/issues) di bagian GitHub masalah GitHub masalah. Untuk memberikan umpan balik dari baris perintah, gunakan `Send-Feedback` cmdlet.

## <a name="frequently-asked-questions"></a>Tanya jawab umum

### <a name="how-to-get-powershellget"></a>Cara mendapatkan PowerShellGet

|Versi OS|Instruksi instalasi|
|---|---|
|Saya memiliki Windows 10 atau Windows Server 2016|Bawaan Windows Management Framework (WMF) 5,0 disertakan di OS|
|Saya ingin memutakhirkan ke PowerShell 5|[Instal versi terbaru WMF](https://www.microsoft.com/download/details.aspx?id=54616)|

### <a name="div-idhelpmechoosechecking-the-version-of-azure-powershell"></a><div id="helpmechoose"/>Memeriksa versi Azure PowerShell

Meskipun kami mendorong Anda untuk memutakhirkan ke versi terbaru sesegera mungkin, beberapa versi Azure PowerShell akan didukung. Untuk menentukan versi versi Azure PowerShell diinstal, jalankan `Get-InstalledModule AzureRM` dari baris perintah.

```powershell-interactive
Get-InstalledModule AzureRM -AllVersions | Select-Object -Property Name,Version,Path
```

### <a name="support-for-classic-deployment-methods"></a>Dukungan untuk metode penyebaran klasik

Jika memiliki penyebaran yang menggunakan model penyebaran klasik, Anda dapat menginstal versi Manajemen Layanan Azure PowerShell. Untuk informasi selengkapnya, [lihat Menginstal Azure PowerShell Service Management.](/powershell/azure/servicemanagement/install-azure-ps) Modul Azure dan AzureRM berbagi dependensi umum. Jika menggunakan modul Azure dan AzureRM, Anda harus menginstal versi yang sama untuk setiap paket.

### <a name="div-idupdate-azpsupdating-to-a-new-version-of-azure-powershell"></a><div id="update-azps"/>Memperbarui ke versi baru Azure PowerShell

Jika Memiliki versi instalan yang Azure PowerShell, Anda mungkin menerima kesalahan berikut:

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

Saat pesan kesalahan muncul, Anda harus menggunakan parameter -AllowClobber untuk menginstal modul. Gunakan perintah berikut:

```powershell-interactive
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module -Name AzureRM -AllowClobber
```

Untuk informasi selengkapnya, lihat topik bantuan [untuk Install-Module](/powershell/module/powershellget/install-module).

### <a name="installing-module-versions-side-by-side"></a>Menginstal versi modul secara berdampingan

Metode penginstalan PowerShellGet adalah satu-satunya metode yang mendukung penginstalan beberapa versi. Misalnya, Anda mungkin memiliki skrip yang ditulis menggunakan versi skrip Azure PowerShell anda tidak memiliki waktu atau sumber daya untuk diperbarui. Perintah berikut ini menggambarkan cara menginstal beberapa versi Azure PowerShell:

```powershell-interactive
Install-Module -Name AzureRM -RequiredVersion 3.7.0
Install-Module -Name AzureRM -RequiredVersion 2.3.0
```

Hanya satu versi modul yang dapat dimuat dalam sesi PowerShell. Anda harus membuka jendela PowerShell baru dan `Import-Module` menggunakannya untuk mengimpor versi cmdlet AzureRM tertentu:

```powershell-interactive
Import-Module -Name AzureRM -RequiredVersion 2.3.0
```

> [!NOTE]
> Versi 2.1.0 dan versi 1.2.6 adalah versi modul pertama yang dirancang untuk diinstal dan digunakan secara berdampingan. Saat memuat versi lama modul Azure PowerShell, versi modul **AzureRM.Profile** yang tidak kompatibel dimuat. Hal ini akan menghasilkan cmdlet yang meminta Anda untuk masuk setiap kali menjalankan cmdlet.

### <a name="other-installation-methods"></a>Metode instalasi lainnya

Untuk informasi tentang menginstal menggunakan Penginstal Platform Web atau Paket MSI, lihat [Metode penginstalan lainnya](other-install.md)