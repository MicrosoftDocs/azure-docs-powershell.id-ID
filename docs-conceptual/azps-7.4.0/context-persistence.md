---
description: Pelajari cara menggunakan kembali info masuk Azure dan informasi lainnya di beberapa sesi PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 04/05/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Konteks Azure dan informasi masuk
ms.openlocfilehash: 4e3b8b3f60fa59e710e1651a5f4a4bb6f2ab04b3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141848318"
---
# <a name="azure-powershell-context-objects"></a>Objek konteks Azure PowerShell

Azure PowerShell menggunakan _objek konteks Azure PowerShell_ (konteks Azure) untuk menyimpan informasi langganan dan autentikasi. Jika Anda memiliki lebih dari satu langganan, konteks Azure memungkinkan Anda memilih langganan untuk menjalankan cmdlet Azure PowerShell. Konteks Azure juga digunakan untuk menyimpan informasi masuk di beberapa sesi PowerShell dan menjalankan proses di latar belakang.

Artikel ini membahas pengelolaan konteks Azure, bukan manajemen langganan atau akun. Jika Anda ingin mengelola pengguna, langganan, penyewa, atau informasi akun lainnya, lihat dokumentasi [Azure Active Directory](/azure/active-directory). Untuk mempelajari penggunaan konteks untuk menjalankan tugas latar belakang atau paralel, lihat [Menggunakan cmdlet Azure PowerShell dalam pekerjaan PowerShell](using-psjobs.md) setelah terbiasa dengan konteks Azure.

## <a name="overview-of-azure-context-objects"></a>Gambaran umum objek konteks Azure

Konteks Azure adalah objek PowerShell yang mewakili langganan aktif Anda untuk menjalankan perintah, dan informasi autentikasi yang diperlukan untuk tersambung ke cloud Azure. Dengan konteks Azure, Azure PowerShell tidak perlu mengautentikasi ulang akun Anda setiap kali beralih langganan. Konteks Azure terdiri dari:

* _Akun_ yang digunakan untuk masuk ke Azure dengan [Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount). Konteks Azure memperlakukan pengguna, ID aplikasi, dan perwakilan layanan secara sama dari perspektif akun.
* _Langganan_ aktif, perjanjian layanan dengan Microsoft untuk membuat dan menjalankan sumber daya Azure, yang terkait dengan _penyewa_. Penyewa sering disebut sebagai _organisasi_ dalam dokumentasi atau ketika bekerja dengan Active Directory.
* Referensi ke _cache token_, token autentikasi yang disimpan untuk mengakses cloud Azure. Di mana token ini disimpan dan berapa lama token ini bertahan ditentukan oleh [pengaturan penyimpanan otomatis konteks](#save-azure-contexts-across-powershell-sessions).

Untuk informasi selengkapnya mengenai istilah-istilah ini, lihat [Terminologi Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis#terminology).
Token autentikasi yang digunakan oleh konteks Azure sama dengan token lainnya yang disimpan yang merupakan bagian dari sesi persisten.

Saat Anda masuk dengan `Connect-AzAccount`, setidaknya satu konteks Azure dibuat untuk langganan default Anda. Objek yang dikembalikan oleh `Connect-AzAccount` adalah konteks Azure default yang digunakan hingga sesi PowerShell berakhir.

## <a name="get-azure-contexts"></a>Mendapatkan konteks Azure

Konteks Azure yang tersedia diambil dengan cmdlet [Get-AzContext](/powershell/module/az.accounts/get-azcontext). Cantumkan semua konteks yang tersedia dengan parameter `ListAvailable`:

```azurepowershell-interactive
Get-AzContext -ListAvailable
```

Atau dapatkan konteks berdasarkan nama:

```azurepowershell-interactive
Get-AzContext -Name 'mycontext'
```

Nama konteks mungkin berbeda dari nama langganan terkait.

> [!IMPORTANT]
> Konteks Azure yang tersedia __tidak__ selalu merupakan langganan Anda yang tersedia. Konteks Azure hanya mewakili informasi yang disimpan secara lokal. Anda bisa mendapatkan langganan Anda menggunakan cmdlet [Get-AzSubscription](/powershell/module/Az.Accounts/Get-AzSubscription).

## <a name="create-a-new-azure-context-from-subscription-information"></a>Membuat konteks Azure baru dari informasi langganan

Cmdlet [Set-AzContext](/powershell/module/Az.Accounts/Set-AzContext) digunakan untuk membuat konteks Azure baru serta mengaturnya sebagai konteks aktif. Cara termudah untuk membuat konteks Azure baru adalah dengan menggunakan informasi langganan yang ada. Cmdlet dirancang untuk mengambil objek output dari `Get-AzSubscription` sebagai nilai yang disalurkan dan mengonfigurasi konteks Azure baru:

```azurepowershell-interactive
Get-AzSubscription -SubscriptionName 'MySubscriptionName' |
  Set-AzContext -Name 'MyContextName'
```

Atau berikan nama atau ID langganan dan ID penyewa jika perlu:

```azurepowershell-interactive
Set-AzContext -Name 'MyContextName' -Subscription 'MySubscriptionName' -Tenant '00000000-0000-0000-0000-000000000000'
```

Jika parameter `Name` dihilangkan, maka nama dan ID langganan digunakan sebagai nama konteks dalam format `Subscription Name (subscription-id)`.

## <a name="change-the-active-azure-context"></a>Mengubah konteks Azure aktif

Baik `Set-AzContext` maupun [Select-AzContext](/powershell/module/az.accounts/set-azcontext) dapat digunakan untuk mengubah konteks Azure aktif. Seperti yang dijelaskan dalam [Membuat konteks Azure baru](#create-a-new-azure-context-from-subscription-information), `Set-AzContext` membuat konteks Azure baru untuk langganan jika konteks belum ada, kemudian mengalihkan konteks aktif ke konteks tersebut.

`Select-AzContext` dimaksudkan untuk digunakan hanya dengan konteks Azure yang ada dan berfungsi mirip dengan menggunakan `Set-AzContext -Context`, tetapi dirancang untuk digunakan dengan penyaluran:

```azurepowershell-interactive
Set-AzContext -Context $(Get-AzContext -Name 'mycontext') # Set a context with an inline Azure context object
Get-AzContext -Name 'mycontext' | Select-AzContext # Set a context with a piped Azure context object
```

Seperti banyak perintah manajemen akun dan konteks lainnya dalam Azure PowerShell, `Set-AzContext` dan `Select-AzContext` mendukung parameter `Scope` sehingga Anda dapat mengontrol berapa lama konteks tersebut aktif. `Scope` memungkinkan Anda mengubah konteks aktif satu sesi tanpa mengubah default Anda:

```azurepowershell-interactive
Get-AzContext -Name 'mycontext' | Select-AzContext -Scope Process
```

Untuk menghindari pengalihan konteks untuk seluruh sesi PowerShell, semua perintah Azure PowerShell dapat dijalankan terhadap konteks tertentu dengan parameter `AzContext`:

```azurepowershell-interactive
$context = Get-AzContext -Name "mycontext"
New-AzVM -Name ExampleVM -AzContext $context
```

Penggunaan utama lain dari konteks dengan cmdlet Azure PowerShell adalah untuk menjalankan perintah latar belakang. Untuk mempelajari selengkapnya menjalankan Pekerjaan PowerShell menggunakan Azure PowerShell, lihat [Menjalankan cmdlet Azure PowerShell di Pekerjaan PowerShell](using-psjobs.md).

## <a name="save-azure-contexts-across-powershell-sessions"></a>Menyimpan konteks Azure di seluruh sesi PowerShell

Secara default, konteks Azure disimpan untuk digunakan di antara sesi PowerShell. Anda mengubah perilaku ini dengan cara berikut:

* Masuk menggunakan `-Scope Process` dengan `Connect-AzAccount`.

  ```azurepowershell
  Connect-AzAccount -Scope Process
  ```

  Konteks Azure yang dikembalikan sebagai bagian dari proses masuk ini _hanya_ berlaku untuk sesi saat ini dan tidak akan disimpan secara otomatis, terlepas dari pengaturan simpan-otomatis konteks Azure PowerShell.
* Nonaktifkan simpan-otomatis konteks di Azure PowerShell dengan cmdlet [Disable-AzContextAutosave](/powershell/module/az.accounts/disable-azcontextautosave).
  Menonaktifkan simpan-otomatis konteks __tidak__ menghapus token yang disimpan. Untuk mempelajari cara menghapus informasi konteks Azure yang disimpan, lihat [Menghapus konteks dan info masuk Azure](#remove-azure-contexts-and-stored-credentials).
* Mengaktifkan simpan-otomatis konteks Azure secara eksplisit dapat diaktifkan dengan cmdlet [Enable-AzContextAutosave](/powershell/module/az.accounts/enable-azcontextautosave). Dengan diaktifkannya simpan-otomatis, semua konteks pengguna disimpan secara lokal untuk sesi PowerShell di kemudian hari.
* Simpan konteks secara manual dengan [Save-AzContext](/powershell/module/az.accounts/save-azcontext) untuk digunakan di sesi PowerShell mendatang, di mana mereka dapat dimuat dengan [Import-AzContext](/powershell/module/az.accounts/import-azcontext):

  ```azurepowershell
  Save-AzContext -Path current-context.json # Save the current context
  Save-AzContext -Profile $profileObject -Path other-context.json # Save a context object
  Import-AzContext -Path other-context.json # Load the context from a file and set it to the current context
  ```

> [!WARNING]
> Menonaktifkan simpan-otomatis konteks __tidak__ menghapus informasi konteks tersimpan yang disimpan. Untuk menghapus informasi yang tersimpan, gunakan cmdlet [Clear-AzContext](/powershell/module/az.accounts/Clear-AzContext). Untuk informasi selengkapnya mengenai menghapus konteks yang disimpan, lihat [Menghapus konteks dan info masuk](#remove-azure-contexts-and-stored-credentials).

Masing-masing perintah ini mendukung parameter `Scope`, yang dapat mengambil nilai `Process` untuk hanya berlaku untuk proses yang sedang berjalan saat ini. Misalnya, untuk memastikan bahwa konteks yang baru dibuat tidak disimpan setelah keluar dari sesi PowerShell:

```azurepowershell-interactive
Disable-AzContextAutosave -Scope Process
$context2 = Set-AzContext -Subscription "sub-id" -Tenant "other-tenant"
```

Informasi konteks dan token disimpan di direktori `$env:USERPROFILE\.Azure` pada Windows, dan di `$HOME/.Azure` pada platform lainnya. Informasi sensitif seperti ID langganan dan ID penyewa mungkin masih terekspos dalam informasi yang disimpan, melalui log, atau konteks yang disimpan. Untuk mempelajari cara menghapus informasi yang disimpan, lihat bagian [Menghapus konteks dan info masuk](#remove-azure-contexts-and-stored-credentials).

## <a name="remove-azure-contexts-and-stored-credentials"></a>Menghapus konteks Azure dan info masuk yang disimpan

Untuk menghapus konteks dan info masuk Azure:

* Keluar dari akun menggunakan [Disconnect-AzAccount](/powershell/module/az.accounts/disconnect-azaccount). Anda dapat keluar dari akun apa pun baik melalui akun atau konteks:

  ```azurepowershell-interactive
  Disconnect-AzAccount # Disconnect active account
  Disconnect-AzAccount -Username 'user@contoso.com' # Disconnect by account name

  Disconnect-AzAccount -ContextName 'subscription2' # Disconnect by context name
  Disconnect-AzAccount -AzureContext $contextObject # Disconnect using context object information
  ```

  Memutuskan sambungan selalu menghapus token autentikasi yang disimpan dan menghapus konteks yang disimpan yang terkait dengan pengguna atau konteks yang terputus.
* Gunakan [Clear-AzContext](/powershell/module/az.accounts/Clear-AzContext). Cmdlet ini selalu menghapus konteks yang tersimpan, token autentikasi, dan mengeluarkan Anda.
* Hapus konteks dengan [Remove-AzContext](/powershell/module/az.accounts/remove-azcontext):

  ```azurepowershell-interactive
  Remove-AzContext -Name 'mycontext' # Remove by name
  Get-AzContext -Name 'mycontext' | Remove-AzContext # Remove by piping Azure context object
  ```

  Jika menghapus konteks aktif, Anda akan terputus dari Azure dan perlu mengautentikasi ulang menggunakan `Connect-AzAccount`.

## <a name="see-also"></a>Lihat juga

* [Menjalankan cmdlet Azure PowerShell di Pekerjaan PowerShell](using-psjobs.md)
* [Terminologi Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis#terminology)
* [Referensi Az.Accounts](/powershell/module/az.accounts)
