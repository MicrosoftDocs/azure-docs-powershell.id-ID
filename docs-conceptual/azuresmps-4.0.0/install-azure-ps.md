---
title: Menginstal dan mengonfigurasi modul Manajemen Layanan Azure PowerShell | Microsoft Docs
description: Cara menginstal dan mengonfigurasi Azure PowerShell untuk penggunaan pertama kali.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: f8a77db1c4e7ed9d0ec2ef70531ea8e7c2068464
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429339"
---
# <a name="installing-the-azure-powershell-service-management-module"></a>Menginstal modul Manajemen Layanan Azure PowerShell

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

Menginstal Azure PowerShell dari [Galeri PowerShell](https://www.powershellgallery.com/) adalah metode penginstalan yang diutamakan.

## <a name="step-1-install-powershellget"></a>Langkah 1: Instal PowerShellGet

Menginstal item dari Galeri PowerShell memerlukan modul PowerShellGet. Pastikan Anda memiliki versi PowerShellGet yang sesuai dan persyaratan sistem lainnya. Jalankan perintah berikut untuk melihat apakah Anda telah menginstal PowerShellGet di sistem Anda.

```powershell
Get-InstalledModule PowerShellGet -AllVersions |
  Select-Object -Property Name, Version, Path
```

Sekarang, Anda akan melihat sesuatu yang mirip dengan output berikut:

```Output
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

Jika Anda tidak menginstal PowerShellGet, lihat [Cara mendapatkan PowerShellGet](#how-to-get-powershellget).

## <a name="step-2-install-azure-powershell"></a>Langkah 2: Instal Azure PowerShell

Jalankan perintah berikut dari konsol Windows PowerShell yang berjalan sebagai Administrator:

```powershell
Install-Module -Name Azure
```

Modul Azure adalah modul rollup untuk cmdlet Manajemen Layanan Azure. Saat menginstal modul AzureRM, modul Azure lainnya mana pun yang sebelumnya belum diinstal akan diunduh dan diinstal dari Galeri PowerShell.

Modul Manajemen Layanan Azure berbagi dependensi dengan modul Azure PowerShell Resource Manager. Jika Anda telah menginstal modul Azure PowerShell Resource Manager, Anda akan harus menambahkan parameter `AllowClobber` ke perintah penginstalan. Hal ini memungkinkan dependensi bersama yang ada untuk diperbarui. Tanpa parameter ini, penginstalan modul gagal.

```powershell
Install-Module -Name Azure -AllowClobber
```

Setelah Menginstal modul ini, Anda dapat mengimpor modul dengan menjalankan perintah berikut:

```powershell
Import-Module -Name Azure
```

## <a name="to-use-the-cmdlets"></a>Untuk menggunakan cmdlet

Untuk mulai bekerja dengan cmdlet Manajemen Layanan Azure, pertama masuk ke akun Azure Anda. Untuk masuk ke akun Anda, jalankan perintah berikut:

```powershell
Add-AzureAccount
```

Setelah masuk ke Azure, Azure PowerShell akan membuat konteks untuk sesi tertentu. Konteks tersebut berisi lingkungan Azure PowerShell, akun, penyewa, dan langganan yang akan digunakan untuk semua cmdlet dalam sesi tersebut. Sekarang Anda siap untuk menggunakan modul di bawah ini.

## <a name="azure-service-management-cmdlets"></a>Cmdlet Manajemen Layanan Azure

Jika Anda menyadari bahwa bantuan cmdlet online menyertakan cmdlet atau parameter yang tidak ada dalam modul Anda, Unduh dan pasang versi terbaru modul.

Untuk skrip sampel yang dapat membantu Anda mengotomatiskan beberapa tugas umum di Azure, lihat [Pusat Skrip Windows Azure](https://www.windowsazure.com/documentation/scripts/).

Untuk informasi umum tentang menginstal, mempelajari, menggunakan, dan menyesuaikan Windows PowerShell, lihat [Membuat skrip dengan Windows PowerShell](/powershell/scripting/learn/ps101/00-introduction).

### <a name="how-to-get-powershellget"></a>Cara mendapatkan PowerShellGet

|                    Versi OS                     |                                     Intruksi penginstalan                                      |
| ------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Saya memiliki Windows 10, Windows Server 2016, atau yang lebih tinggi | Dibuat dalam Windows Management Framework (WMF) 5.x termasuk dalam OS                          |
| Saya ingin meningkatkan ke PowerShell 5                 | [Menginstal WMF versi terbaru](https://www.microsoft.com/download/details.aspx?id=54616) |

### <a name="checking-the-version-of-azure-powershell"></a>Memeriksa versi Azure PowerShell

Untuk menentukan versi Azure PowerShell yang telah Anda pasang, jalankan `Get-InstalledModule -Name Azure` dari PowerShell.

```powershell
Get-InstalledModule -Name Azure -AllVersions |
  Select-Object -Property Name,Version,Path
```
