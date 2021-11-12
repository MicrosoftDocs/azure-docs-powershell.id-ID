---
title: Cara lain untuk menginstal Azure PowerShell | Microsoft Docs
description: Cara menginstal Azure PowerShell menggunakan paket MSI atau Penginstal Platform Web.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/06/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 3a52201f6fd45de171d6a6b1088e12eb204192ae
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427987"
---
# <a name="other-installation-methods"></a>Metode instalasi lainnya

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Azure PowerShell memiliki beberapa metode penginstalan. Menggunakan PowerShellGet dengan Galeri PowerShell adalah metode yang lebih disukai. Azure PowerShell dapat diinstal di Windows menggunakan Penginstal Platform Web (WebPI) atau dengan menggunakan file MSI yang tersedia dari GitHub.

## <a name="install-on-windows-using-the-web-platform-installer"></a>Instal di Windows menggunakan Penginstal Platform Web

Menginstal versi Azure PowerShell dari WebPI sama seperti menginstal untuk versi sebelumnya.
Unduh paket [Azure PowerShell WebPI](https://aka.ms/webpi-azps) Anda dan mulai menginstal.

> [!NOTE]
> Jika sebelumnya Anda telah menginstal modul Azure dari Galeri PowerShell, penginstal akan menghapusnya secara otomatis. Ini menyederhanakan lingkungan Anda dengan memastikan bahwa hanya satu versi Azure PowerShell saja yang diinstal. Namun, ada skenario di mana Anda mungkin membutuhkan beberapa versi yang diinstal pada saat yang sama.
>
> Modul instalasi Galeri PowerShell modul di `$env:ProgramFiles\WindowsPowerShell\Modules` . Sebaliknya, penginstal WebPI menginstal modul Azure di `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\` .
>
> Jika terjadi kesalahan selama penginstalan, Anda dapat menghapus folder Azure dalam \* folder secara `$env:ProgramFiles\WindowsPowerShell\Modules` manual, lalu mencoba penginstalan kembali.

Setelah instalasi selesai, pengaturan `$env:PSModulePath` Anda harus menyertakan direktori yang berisi cmdlet Azure PowerShell. Perintah berikut ini dapat digunakan untuk memverifikasi bahwa Azure PowerShell diinstal dengan benar.

```powershell-interactive
# To make sure the Azure PowerShell module is available after you install
Get-InstalledModule -Name AzureRM -AllVersions | Select-Object Name, Version, Path
```

> [!NOTE]
> Terdapat masalah umum yang dapat terjadi ketika menginstal dari WebPI. Jika komputer Anda memerlukan mulai ulang karena pembaruan sistem atau penginstalan lain, mungkin menyebabkan pembaruan gagal menyertakan jalur `$env:PSModulePath` tempat Azure PowerShell diinstal.

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

Kesalahan ini dapat diperbaiki dengan memulai ulang mesin atau mengimpor modul menggunakan jalur yang sepenuhnya memenuhi syarat. Misalnya:

```powershell-interactive
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## <a name="install-on-windows-using-the-msi-package"></a>Instal di Windows Anda menggunakan Paket MSI

Azure PowerShell bisa diinstal menggunakan file MSI yang tersedia dari [GitHub](https://github.com/Azure/azure-powershell/releases/latest). Jika Anda telah menginstal versi modul Azure sebelumnya, penginstal secara otomatis akan menghapusnya. Paket MSI menginstal modul tetapi `$env:ProgramFiles\WindowsPowerShell\Modules` tidak membuat folder khusus versi.

