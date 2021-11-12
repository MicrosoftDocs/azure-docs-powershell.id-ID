---
title: Konteks dan kredensial masuk Azure
description: Pelajari cara menggunakan kembali kredensial Azure dan informasi lainnya di beberapa sesi PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/27/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: c8e2e52bbebd5352e569009a5ba5f6791df5ace7
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429474"
---
# <a name="azure-powershell-context-objects"></a>Azure PowerShell objek konteks

Azure PowerShell menggunakan _Azure PowerShell konteks (konteks_ Azure) untuk menampung informasi langganan dan autentikasi. Jika memiliki lebih dari satu langganan, konteks Azure memungkinkan Anda memilih langganan untuk Azure PowerShell cmdlet. Konteks Azure juga digunakan untuk menyimpan informasi masuk di beberapa sesi PowerShell dan menjalankan tugas latar belakang.

Artikel ini membahas tentang mengelola konteks Azure, bukan manajemen langganan atau akun. Jika Anda ingin mengelola pengguna, langganan, penyewa, atau informasi akun lainnya, lihat dokumentasi [Azure Active Directory](/azure/active-directory) bisnis. Untuk mempelajari tentang menggunakan konteks untuk menjalankan latar belakang atau tugas paralel, lihat Menggunakan cmdlet Azure PowerShell dalam pekerjaan [PowerShell](using-psjobs.md) setelah terbiasa dengan konteks Azure.

## <a name="overview-of-azure-context-objects"></a>Gambaran umum objek konteks Azure

Konteks Azure adalah objek PowerShell yang mewakili langganan aktif untuk dijalankan, dan informasi autentikasi yang diperlukan untuk tersambung ke cloud Azure. Dengan konteks Azure, Azure PowerShell tidak perlu mengautentikasi ulang akun Anda setiap kali beralih langganan. Konteks Azure terdiri dari:

* Akun _yang_ digunakan untuk masuk ke Azure dengan akun [Koneksi-AzAccount](/powershell/module/az.accounts/connect-azaccount). Konteks Azure memperlakukan pengguna, ID aplikasi, dan prinsipal layanan yang sama dari perspektif akun.
* Langganan aktif _,_ perjanjian layanan dengan Microsoft untuk membuat dan menjalankan sumber daya Azure, yang terkait dengan _penyewa._ Penyewa sering disebut sebagai organisasi _dalam dokumentasi_ atau saat bekerja dengan Direktori Aktif.
* Referensi ke cache _token, token_ autentikasi tersimpan untuk mengakses awan Azure. Di mana token ini disimpan dan berapa lama token tersebut tetap untuk ditentukan oleh [pengaturan simpan otomatis konteks.](#save-azure-contexts-across-powershell-sessions)

Untuk informasi selengkapnya tentang persyaratan ini, lihat [Azure Active Directory Terminologi](/azure/active-directory/fundamentals/active-directory-whatis#terminology).
Token autentikasi yang digunakan oleh konteks Azure sama seperti token tersimpan lainnya yang merupakan bagian dari sesi tetap.

Jika masuk dengan `Connect-AzAccount` , setidaknya satu konteks Azure dibuat untuk langganan default Anda. Objek yang dikembalikan `Connect-AzAccount` adalah konteks default Azure yang digunakan untuk seluruh sesi PowerShell.

## <a name="get-azure-contexts"></a>Mendapatkan konteks Azure

Konteks Azure yang tersedia diambil dengan cmdlet [Get-AzContext.](/powershell/module/az.accounts/get-azcontext) Daftar semua konteks yang tersedia dengan `ListAvailable` parameter:

```azurepowershell-interactive
Get-AzContext -ListAvailable
```

Atau dapatkan konteks berdasarkan nama:

```azurepowershell-interactive
Get-AzContext -Name 'mycontext'
```

Nama konteks mungkin berbeda dari nama langganan terkait.

> [!IMPORTANT]
> Konteks Azure yang __tersedia tidak selalu__ menjadi langganan Anda. Konteks Azure hanya mewakili informasi yang disimpan secara lokal. Anda bisa mendapatkan langganan Anda dengan cmdlet [Get-AzSubscription.](/powershell/module/Az.Accounts/Get-AzSubscription)

## <a name="create-a-new-azure-context-from-subscription-information"></a>Membuat konteks Azure baru dari informasi langganan

Cmdlet [Set-AzContext](/powershell/module/Az.Accounts/Set-AzContext) digunakan untuk membuat konteks Azure baru dan mengaturnya sebagai konteks aktif. Cara termudah untuk membuat konteks Azure baru adalah menggunakan informasi langganan yang sudah ada. Cmdlet dirancang untuk mengambil objek output sebagai `Get-AzSubscription` nilai pipa dan mengonfigurasi konteks Azure baru:

```azurepowershell-interactive
Get-AzSubscription -SubscriptionName 'MySubscriptionName' |
  Set-AzContext -Name 'MyContextName'
```

Atau beri nama langganan atau ID penyewa jika diperlukan:

```azurepowershell-interactive
Set-AzContext -Name 'MyContextName' -Subscription 'MySubscriptionName' -Tenant '00000000-0000-0000-0000-000000000000'
```

Jika `Name` parameter dihilangkan, maka nama dan ID langganan digunakan sebagai nama konteks dalam format `Subscription Name (subscription-id)` .

## <a name="change-the-active-azure-context"></a>Mengubah konteks Azure yang aktif

Keduanya `Set-AzContext` dan [Select-AzContext](/powershell/module/az.accounts/set-azcontext) bisa digunakan untuk mengubah konteks Azure aktif. Seperti yang [diuraikan dalam](#create-a-new-azure-context-from-subscription-information)Membuat konteks Azure baru, membuat konteks Azure baru untuk langganan jika belum ada, lalu mengalihkan konteks `Set-AzContext` aktif ke konteks tersebut.

`Select-AzContext` dimaksudkan untuk digunakan hanya dengan konteks Azure yang sudah ada dan berfungsi serupa dengan menggunakan , tetapi dirancang untuk digunakan `Set-AzContext -Context` dengan pemipaan:

```azurepowershell-interactive
Set-AzContext -Context $(Get-AzContext -Name 'mycontext') # Set a context with an inline Azure context object
Get-AzContext -Name 'mycontext' | Select-AzContext # Set a context with a piped Azure context object
```

Seperti kebanyakan perintah manajemen akun dan konteks Azure PowerShell, serta mendukung parameter sehingga `Set-AzContext` Anda dapat mengontrol berapa lama konteks `Select-AzContext` `Scope` aktif. `Scope` memungkinkan Anda mengubah konteks aktif sesi tunggal tanpa mengubah default Anda:

```azurepowershell-interactive
Get-AzContext -Name 'mycontext' | Select-AzContext -Scope Process
```

Untuk menghindari beralih konteks untuk seluruh sesi PowerShell, semua Azure PowerShell perintah dapat dijalankan berdasarkan konteks yang ada dengan `AzContext` parameter:

```azurepowershell-interactive
$context = Get-AzContext -Name "mycontext"
New-AzVM -Name ExampleVM -AzContext $context
```

Penggunaan utama konteks lainnya dengan cmdlet Azure PowerShell adalah menjalankan perintah latar belakang. Untuk mempelajari selengkapnya tentang menjalankan Pekerjaan PowerShell menggunakan Azure PowerShell, [lihat Menjalankan cmdlet Azure PowerShell cmdlet di PowerShell Jobs](using-psjobs.md).

## <a name="save-azure-contexts-across-powershell-sessions"></a>Menyimpan konteks Azure di seluruh sesi PowerShell

Secara default, konteks Azure disimpan untuk digunakan di antara sesi PowerShell. Anda mengubah perilaku ini dengan cara berikut:

* Masuk menggunakan `-Scope Process` dengan `Connect-AzAccount` .

  ```azurepowershell
  Connect-AzAccount -Scope Process
  ```

  Konteks Azure yang dikembalikan sebagai bagian dari proses masuk  ini hanya valid untuk sesi saat ini dan tidak akan disimpan secara otomatis, terlepas dari pengaturan Azure PowerShell konteks simpan otomatis.
* Nonaktifkan simpan otomatis konteks Azure PowerShell dengan cmdlet [Disable-AzContextAutosave.](/powershell/module/az.accounts/disable-azcontextautosave)
  Menonaktifkan simpan otomatis konteks __tidak akan menghapus__ token yang disimpan. Untuk mempelajari cara menghapus informasi konteks Azure yang disimpan, [lihat Menghapus konteks dan kredensial Azure.](#remove-azure-contexts-and-stored-credentials)
* Aktifkan simpan otomatis konteks Azure secara eksplisit dapat diaktifkan dengan cmdlet [Enable-AzContextAutosave.](/powershell/module/az.accounts/enable-azcontextautosave) Dengan simpan otomatis diaktifkan, semua konteks pengguna disimpan secara lokal untuk sesi PowerShell selanjutnya.
* Simpan konteks secara manual [dengan Save-AzContext](/powershell/module/az.accounts/save-azcontext) untuk digunakan dalam sesi PowerShell yang akan datang, di mana konteks bisa dimuat dengan [Import-AzContext](/powershell/module/az.accounts/import-azcontext):

  ```azurepowershell
  Save-AzContext -Path current-context.json # Save the current context
  Save-AzContext -Profile $profileObject -Path other-context.json # Save a context object
  Import-AzContext -Path other-context.json # Load the context from a file and set it to the current context
  ```

> [!WARNING]
> Menonaktifkan simpan otomatis konteks tidak __akan menghapus informasi__ konteks tersimpan apa pun yang telah disimpan. Untuk menghapus informasi yang disimpan, gunakan cmdlet [Clear-AzContext.](/powershell/module/az.accounts/Clear-AzContext) Untuk informasi selengkapnya tentang menghapus konteks yang disimpan, [lihat Menghapus konteks dan kredensial](#remove-azure-contexts-and-stored-credentials).

Setiap perintah ini mendukung `Scope` parameter, yang dapat mengambil nilai untuk diterapkan `Process` hanya pada proses yang berjalan saat ini. Misalnya, untuk memastikan bahwa konteks yang baru dibuat tidak disimpan setelah keluar dari sesi PowerShell:

```azurepowershell-interactive
Disable-AzContextAutosave -Scope Process
$context2 = Set-AzContext -Subscription "sub-id" -Tenant "other-tenant"
```

Informasi konteks dan token disimpan dalam direktori `$env:USERPROFILE\.Azure` di Windows, dan `$HOME/.Azure` pada platform lain. Informasi sensitif seperti ID langganan dan ID penyewa mungkin masih diekspos dalam informasi yang disimpan, melalui log, atau konteks yang disimpan. Untuk mempelajari cara menghapus informasi yang disimpan, [lihat bagian Menghapus konteks dan](#remove-azure-contexts-and-stored-credentials) kredensial.

## <a name="remove-azure-contexts-and-stored-credentials"></a>Menghapus konteks Azure dan kredensial yang disimpan

Untuk menghapus konteks dan kredensial Azure:

* Keluar dari akun dengan [Disconnect-AzAccount](/powershell/module/az.accounts/disconnect-azaccount). Anda bisa keluar dari akun apa pun baik menurut akun atau konteks:

  ```azurepowershell-interactive
  Disconnect-AzAccount # Disconnect active account
  Disconnect-AzAccount -Username 'user@contoso.com' # Disconnect by account name

  Disconnect-AzAccount -ContextName 'subscription2' # Disconnect by context name
  Disconnect-AzAccount -AzureContext $contextObject # Disconnect using context object information
  ```

  Memutuskan koneksi selalu menghapus token autentikasi yang disimpan dan membersihkan konteks yang disimpan yang terkait dengan pengguna atau konteks yang tidak tersambung.
* Gunakan [Clear-AzContext](/powershell/module/az.accounts/Clear-AzContext). Cmdlet ini selalu menghapus konteks yang disimpan, token autentikasi, dan mengeluarkan Anda.
* Menghapus konteks dengan [Remove-AzContext](/powershell/module/az.accounts/remove-azcontext):

  ```azurepowershell-interactive
  Remove-AzContext -Name 'mycontext' # Remove by name
  Get-AzContext -Name 'mycontext' | Remove-AzContext # Remove by piping Azure context object
  ```

  Jika menghapus konteks aktif, Anda akan diputus dari Azure dan perlu melakukan otentikasi ulang dengan `Connect-AzAccount` .

## <a name="see-also"></a>Lihat juga

* [Menjalankan Azure PowerShell cmdlet dalam Pekerjaan PowerShell](using-psjobs.md)
* [Azure Active Directory Terminologi](/azure/active-directory/fundamentals/active-directory-whatis#terminology)
* [Referensi Az.Accounts](/powershell/module/az.accounts)
