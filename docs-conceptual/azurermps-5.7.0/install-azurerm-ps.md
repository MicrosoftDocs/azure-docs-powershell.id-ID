---
title: Menginstal Azure PowerShell di Windows dengan PowerShellGet
description: Cara menginstal Azure PowerShell dengan PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/15/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: c03c6ee3782b68de8a237b3c215405ff6513dbca
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421094"
---
# <a name="install-azure-powershell-on-windows-with-powershellget"></a>Menginstal Azure PowerShell di Windows dengan PowerShellGet

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Artikel ini menjelaskan langkah-langkah menginstal modul Azure PowerShell untuk PowerShell 5.x di Windows menggunakan PowerShellGet. PowerShellGet dan manajemen modul adalah cara yang diutamakan untuk menginstal Azure PowerShell, tetapi jika Anda ingin menginstal dengan Installer Platform Web atau paket MSI, lihat [Metode penginstalan lainnya](other-install.md).

Model penyebaran klasik Azure tidak didukung oleh versi Azure PowerShell ini. Untuk dukungan penyebaran klasik, ikuti petunjuk di [Menginstal modul Manajemen Layanan Azure PowerShell](/powershell/azure/servicemanagement/install-azure-ps).

> [!IMPORTANT]
> Modul AzureRM tidak didukung untuk macOS atau Linux. Untuk menggunakan cmdlet Azure PowerShell pada platform ini, [Instal modul Az](/powershell/azure/install-az-ps).

## <a name="requirements"></a>Persyaratan

Untuk menginstal Azure PowerShell, Anda memerlukan PowerShellGet versi 1.1.2.0 atau yang lebih tinggi. Untuk memeriksa ketersediaannya di sistem Anda, jalankan perintah berikut:

```powershell-interactive
Get-InstalledModule -Name PowerShellGet -AllVersions | Select-Object -Property Name,Version,Path
```

Anda akan melihat output seperti berikut:

```output
Name          Version Path
----          ------- ----
Name          Version Path
----          ------- ----
PowerShellGet 1.6.0   C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.6.0\PowerShellGet.psd1
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

Jika Anda perlu memperbarui penginstalan PowerShellGet, jalankan perintah berikut:

```powershell-interactive
Install-Module PowerShellGet -Force
```

Jika Anda belum menginstal PowerShellGet, ikuti petunjuk pada tabel berikut untuk sistem Anda.

|Skenario|Petunjuk penginstalan|
|---|---|
|Windows 10<br/>Server Windows 2016|Bawaan Windows Management Framework (WMF) 5.0 yang disertakan dalam OS|
|Meningkatkan ke PowerShell 5| <ol><li>[Menginstal WMF versi terbaru](https://www.microsoft.com/download/details.aspx?id=54616)</li><li>Jalankan perintah berikut:<br/>```Install-Module PowerShellGet -Force```</li></ol>|

> [!NOTE]
> Untuk menggunakan PowerShellGet, diperlukan Kebijakan Eksekusi yang memungkinkan Anda menjalankan skrip. Untuk informasi selengkapnya tentang Kebijakan Eksekusi PowerShell, lihat [Tentang Kebijakan Eksekusi](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
>
> [!IMPORTANT]
> Modul yang dijelaskan dalam dokumen ini, AzureRM, menggunakan .NET Framework. Artinya, modul ini tidak kompatibel dengan PowerShell 6.0 yang menggunakan .NET Core. Jika Anda menggunakan PowerShell 6.0, ikuti [petunjuk penginstalan untuk macOS dan Linux](/powershell/azure/install-az-ps).

## <a name="install-the-azure-powershell-module"></a>Menginstal modul Azure PowerShell

Anda memerlukan hak istimewa yang lebih tinggi untuk menginstal modul dari Galeri PowerShell. Untuk menginstal Azure PowerShell, jalankan perintah berikut di sesi yang lebih tinggi:

```powershell-interactive
Install-Module -Name AzureRM
```

> [!NOTE]
> Jika Anda memiliki versi NuGet yang lebih lama dari 2.8.5.201, Anda akan diminta untuk mengunduh dan menginstal NuGet versi terbaru.

Secara default, galeri PowerShell tidak dikonfigurasi sebagai repositori tepercaya untuk PowerShellGet. Pertama kali Anda menggunakan PSGallery, Anda akan melihat perintah berikut:

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Jawab `Yes` atau `Yes to All` untuk melanjutkan pemasangan.

Modul `AzureRM` ini adalah modul rollup untuk cmdlet Azure PowerShell. Menginstalnya berarti mengunduh semua modul Azure Resource Manager yang tersedia, dan membuat cmdlet-nya tersedia untuk digunakan.

## <a name="sign-in"></a>Masuk

Untuk mulai menggunakan Azure PowerShell, Anda perlu memuat `AzureRM` ke sesi PowerShell saat ini dengan cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module), lalu masuk dengan kredensial Azure Anda.

```powershell-interactive
# Import the module into the PowerShell session
Import-Module AzureRM
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

Anda harus mengulangi langkah-langkah ini untuk setiap sesi PowerShell baru yang Anda mulai. Untuk mengimpor modul `AzureRM` secara otomatis, Anda harus mengatur profil PowerShell, yang dapat dipelajari di [Tentang Profil](/powershell/module/microsoft.powershell.core/about/about_profiles).
Untuk mempelajari cara mempertahankan info masuk Azure di seluruh sesi, lihat [Mempertahankan kredensial pengguna di seluruh sesi PowerShell](context-persistence.md).

## <a name="update-the-azure-powershell-module"></a>Memperbarui modul Azure PowerShell

Anda dapat memperbarui penginstalan Azure PowerShell dengan menjalankan [Update-Module](/powershell/module/powershellget/update-module). Perintah ini __tidak__ menghapus instalan versi sebelumnya.

```powershell-interactive
Update-Module -Name AzureRM
```

Jika Anda ingin menghapus versi Azure PowerShell yang sebelumnya dari sistem, lihat [Menghapus instalan modul Azure PowerShell](uninstall-azurerm-ps.md).

## <a name="use-multiple-versions-of-azure-powershell"></a>Menggunakan beberapa versi Azure PowerShell

Anda dapat menginstal beberapa versi Azure PowerShell. Anda mungkin memerlukan lebih dari satu versi jika menggunakan sumber daya Azure Stack lokal, menjalankan versi Windows lama yang tidak dapat diperbarui ke PowerShell 5.0, atau menggunakan model penyebaran klasik Azure. Untuk menginstal versi yang lebih lama, berikan argumen `-RequiredVersion` saat menginstal.

```powershell-interactive
# Install version 2.3.0 of Azure PowerShell
Install-Module -Name AzureRM -RequiredVersion 2.3.0
```

Saat memuat modul Azure PowerShell, versi terbaru dimuat secara default. Untuk memuat versi yang berbeda, berikan argumen `-RequiredVersion`.

```powershell-interactive
# Load version 2.3.0 of Azure PowerShell
Import-Module -Name AzureRM -RequiredVersion 2.3.0
```

## <a name="provide-feedback"></a>Berikan umpan balik

Jika Anda menemukan bug saat menggunakan Azure Powershell, [laporkan masalah di GitHub](https://github.com/Azure/azure-powershell/issues).
Untuk memberikan umpan balik dari baris perintah, gunakan cmdlet [Send-Feedback](/powershell/module/azurerm.profile/send-feedback).

## <a name="next-steps"></a>Langkah berikutnya

Untuk mulai menggunakan Azure PowerShell, lihat [Mulai menggunakan Azure PowerShell](get-started-azureps.md) untuk mempelajari modul dan fiturnya lebih lanjut.
