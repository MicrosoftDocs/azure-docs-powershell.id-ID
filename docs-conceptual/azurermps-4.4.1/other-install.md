---
title: Cara lain untuk menginstal Azure PowerShell | Microsoft Docs
description: Cara menginstal Azure PowerShell menggunakan paket MSI atau Penginstal Platform Web.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 3a52201f6fd45de171d6a6b1088e12eb204192ae
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427987"
---
# <a name="other-installation-methods"></a>Metode penginstalan lainnya

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Azure PowerShell memiliki beberapa metode penginstalan. Menggunakan PowerShellGet dengan PowerShell Gallery adalah metode yang diutamakan. Azure PowerShell dapat diinstal di Windows menggunakan Alat Penginstal Platform Web (WebPI) atau dengan menggunakan file MSI yang tersedia dari GitHub.

## <a name="install-on-windows-using-the-web-platform-installer"></a>Menginstal di Windows menggunakan Alat Penginstal Platform Web

Menginstal Azure PowerShell terbaru dari WebPI sama dengan penginstalan untuk versi sebelumnya.
Unduh [paket Webpi Azure PowerShell](https://aka.ms/webpi-azps) dan mulai penginstalan.

> [!NOTE]
> Jika sebelumnya Anda telah menginstal modul Azure dari Galeri PowerShell, alat penginstal akan menghapusnya secara otomatis. Hal ini menyederhanakan lingkungan Anda dengan memastikan bahwa hanya satu versi Azure PowerShell yang diinstal. Namun, terdapat skenario di mana Anda mungkin memerlukan beberapa versi yang diinstal bersamaan.
>
> Modul Galeri PowerShell menginstal modul di `$env:ProgramFiles\WindowsPowerShell\Modules`. Sebaliknya, penginstal WebPI menginstal modul Azure di `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.
>
> Jika terjadi kesalahan selama penginstalan, Anda dapat menghapus secara manual folder Azure\* di folder `$env:ProgramFiles\WindowsPowerShell\Modules` Anda, dan coba penginstalan lagi.

Setelan penginstalan selesai, pengaturan `$env:PSModulePath` Anda harus menyertakan direktori yang berisi cmdlet Azure PowerShell. Perintah berikut dapat digunakan untuk memverifikasi bahwa Azure PowerShell diinstal dengan benar.

```powershell-interactive
# To make sure the Azure PowerShell module is available after you install
Get-InstalledModule -Name AzureRM -AllVersions | Select-Object Name, Version, Path
```

> [!NOTE]
> Terdapat masalah yang diketahui yang dapat terjadi saat menginstal dari WebPI. Jika komputer Anda memerlukan hidupkan ulang karena pembaruan sistem atau penginstalan lainnya, hal ini dapat menyebabkan pembaruan pada `$env:PSModulePath` gagal untuk menyertakan jalur tempat Azure PowerShell diinstal.

Saat mencoba memuat atau menjalankan cmdlet setelah penginstalan, Anda dapat menerima pesan kesalahan berikut:

```output
PS C:\> Login-AzureRmAccount
Login-AzureRmAccount : The term 'Login-AzureRmAccount' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:1
+ Login-AzureRmAccount
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Login-AzureRmAccount:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

Kesalahan ini dapat diperbaiki dengan menghidupkan ulang mesin atau mengimpor modul menggunakan jalur yang memenuhi syarat sepenuhnya. Contohnya:

```powershell-interactive
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <a name="install-on-windows-using-the-msi-package"></a>Menginstal di Windows menggunakan Paket MSI

Azure PowerShell dapat diinstal menggunakan file MSI yang tersedia dari [GitHub](https://github.com/Azure/azure-powershell/releases/latest). Jika Anda telah menginstal versi modul Azure sebelumnya, penginstal akan menghapusnya secara otomatis. Paket MSI menginstal modul di `$env:ProgramFiles\WindowsPowerShell\Modules` tetapi tidak membuat folder khusus versi.

