---
title: Menginstal dan mengonfigurasi modul Azure PowerShell Service Management | Microsoft Docs
description: Cara menginstal dan mengonfigurasi Azure PowerShell untuk penggunaan pertama.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: f8a77db1c4e7ed9d0ec2ef70531ea8e7c2068464
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429339"
---
# <a name="installing-the-azure-powershell-service-management-module"></a>Menginstal modul Azure PowerShell Manajemen Layanan

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

Menginstal Azure PowerShell dari [Galeri PowerShell](https://www.powershellgallery.com/) adalah metode penginstalan yang lebih disukai.

## <a name="step-1-install-powershellget"></a>Langkah 1: Instal PowerShellGet

Menginstal item dari Galeri PowerShell memerlukan modul PowerShellGet. Pastikan Anda memiliki versi PowerShellGet yang sesuai dan persyaratan sistem lainnya. Jalankan perintah berikut ini untuk melihat apakah PowerShellGet terinstal di sistem Anda.

```powershell
Get-InstalledModule PowerShellGet -AllVersions |
  Select-Object -Property Name, Version, Path
```

Anda akan melihat sesuatu yang mirip dengan output berikut:

```Output
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

Jika belum menginstal PowerShellGet, lihat cara [mendapatkan PowerShellGet](#how-to-get-powershellget).

## <a name="step-2-install-azure-powershell"></a>Langkah 2: Instal Azure PowerShell

Jalankan perintah berikut ini dari Windows PowerShell pelanggan yang dijalankan sebagai Administrator:

```powershell
Install-Module -Name Azure
```

Modul Azure adalah modul rollup untuk cmdlet Manajemen Layanan Azure. Ketika menginstal modul AzureRM, modul Azure lainnya yang belum diinstal akan diunduh dan diinstal dari Galeri PowerShell.

Modul Azure Service Management berbagi dependensi dengan modul Azure PowerShell Resource Manager. Jika telah menginstal modul Azure PowerShell Resource Manager, Anda perlu menambahkan `AllowClobber` parameter ke perintah penginstalan. Ini memungkinkan dependensi bersama yang sudah ada diperbarui. Tanpa parameter ini, penginstalan modul akan gagal.

```powershell
Install-Module -Name Azure -AllowClobber
```

Setelah menginstal modul ini, Anda dapat mengimpor modul dengan menjalankan perintah berikut:

```powershell
Import-Module -Name Azure
```

## <a name="to-use-the-cmdlets"></a>Untuk menggunakan cmdlet

Untuk mulai bekerja dengan cmdlet Manajemen Layanan Azure, masuk terlebih dahulu ke akun Azure Anda. Untuk masuk ke akun Anda, jalankan perintah berikut:

```powershell
Add-AzureAccount
```

Setelah masuk ke Azure, Azure PowerShell membuat konteks untuk sesi tertentu. Konteks tersebut berisi Azure PowerShell lingkungan, akun, penyewa, dan langganan yang akan digunakan untuk semua cmdlet dalam sesi tersebut. Sekarang Anda siap untuk menggunakan modul di bawah ini.

## <a name="azure-service-management-cmdlets"></a>Cmdlet Azure Service Management

Jika Anda menyadari bahwa bantuan cmdlet online mencakup cmdlet atau parameter yang tidak ada dalam modul, unduh dan instal versi terbaru modul.

Untuk sampel skrip yang bisa membantu Anda mengotomatisasi beberapa tugas umum di Azure, [lihat Windows Azure Script Center](https://www.windowsazure.com/documentation/scripts/).

Untuk informasi umum tentang menginstal, mempelajari, menggunakan, dan Windows PowerShell, lihat [Scripting with Windows PowerShell](/powershell/scripting/learn/ps101/00-introduction).

### <a name="how-to-get-powershellget"></a>Cara mendapatkan PowerShellGet

|                    Versi OS                     |                                     Instruksi instalasi                                      |
| ------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Saya telah Windows 10, Windows Server 2016, atau lebih baru | Disertakan dalam Windows Management Framework (WMF) 5.x yang disertakan di OS                          |
| Saya ingin memutakhirkan ke PowerShell 5                 | [Instal versi terbaru WMF](https://www.microsoft.com/download/details.aspx?id=54616) |

### <a name="checking-the-version-of-azure-powershell"></a>Memeriksa versi Azure PowerShell

Untuk menentukan versi versi Azure PowerShell yang telah diinstal, jalankan `Get-InstalledModule -Name Azure` dari PowerShell.

```powershell
Get-InstalledModule -Name Azure -AllVersions |
  Select-Object -Property Name,Version,Path
```
