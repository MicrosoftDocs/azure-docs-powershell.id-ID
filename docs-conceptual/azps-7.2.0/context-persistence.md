---
title: Konteks Azure dan kredensial masuk
description: Pelajari cara menggunakan kembali kredensial Azure dan informasi lainnya di beberapa sesi PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/04/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 540207a0124fbfd1f5a06f656ac909aeba093e0c
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138335058"
---
# <a name="azure-powershell-context-objects"></a>objek konteks Azure PowerShell

Azure PowerShell menggunakan _objek konteks Azure PowerShell_ (konteks Azure) untuk menyimpan informasi langganan dan autentikasi. Jika Anda memiliki lebih dari satu langganan, konteks Azure memungkinkan Anda memilih langganan untuk menjalankan cmdlet Azure PowerShell. Konteks Azure juga digunakan untuk menyimpan informasi masuk di beberapa sesi PowerShell dan menjalankan tugas latar belakang.

Artikel ini mencakup pengelolaan konteks Azure, bukan pengelolaan langganan atau akun. Jika Anda ingin mengelola pengguna, langganan, penyewa, atau informasi akun lainnya, lihat [dokumentasi Azure Active Directory](/azure/active-directory). Untuk mempelajari tentang menggunakan konteks untuk menjalankan tugas latar belakang atau paralel, lihat [Menggunakan cmdlet Azure PowerShell di pekerjaan PowerShell](using-psjobs.md) setelah terbiasa dengan konteks Azure.

## <a name="overview-of-azure-context-objects"></a>Gambaran umum objek konteks Azure

Konteks Azure adalah objek PowerShell yang mewakili langganan aktif Anda untuk menjalankan perintah, dan informasi autentikasi yang diperlukan untuk menyambungkan ke cloud Azure. Dengan konteks Azure, Azure PowerShell tidak perlu mengotorisasi ulang akun Anda setiap kali Anda beralih langganan. Konteks Azure terdiri dari:

* _Akun_ yang digunakan untuk masuk ke Azure dengan [Koneksi-AzAccount](/powershell/module/az.accounts/connect-azaccount). Konteks Azure memperlakukan pengguna, ID aplikasi, dan prinsipal layanan sama dari perspektif akun.
* _Langganan_ aktif, perjanjian layanan dengan Microsoft untuk membuat dan menjalankan sumber daya Azure, yang terkait dengan _penyewa_. Penyewa sering disebut sebagai _organisasi_ dalam dokumentasi atau ketika bekerja dengan Active Directory.
* Referensi ke _cache token_, token otentikasi tersimpan untuk mengakses cloud Azure. Di mana token ini disimpan dan berapa lama bertahan ditentukan oleh [pengaturan simpan otomatis konteks](#save-azure-contexts-across-powershell-sessions).

Untuk informasi selengkapnya tentang istilah-istilah ini, lihat [terminologi Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis#terminology).
Token otentikasi yang digunakan oleh konteks Azure sama dengan token tersimpan lainnya yang merupakan bagian dari sesi persisten.

Saat Anda masuk `Connect-AzAccount`, setidaknya satu konteks Azure dibuat untuk langganan default Anda. Objek yang dikembalikan `Connect-AzAccount` adalah konteks Azure default yang digunakan untuk sisa sesi PowerShell.

## <a name="get-azure-contexts"></a>Dapatkan konteks Azure

Konteks Azure yang tersedia diambil dengan cmdlet [Get-AzContext](/powershell/module/az.accounts/get-azcontext) . Daftar semua konteks yang tersedia dengan `ListAvailable` parameter:

```azurepowershell-interactive
Get-AzContext -ListAvailable
```

Atau dapatkan konteks dengan nama:

```azurepowershell-interactive
Get-AzContext -Name 'mycontext'
```

Nama konteks mungkin berbeda dari nama langganan terkait.

> [!IMPORTANT]
> Konteks Azure yang __tersedia tidak__ selalu menjadi langganan Anda yang tersedia. Konteks Azure hanya mewakili informasi yang disimpan secara lokal. Anda bisa mendapatkan langganan Anda dengan cmdlet [Get-AzSubscription](/powershell/module/Az.Accounts/Get-AzSubscription) .

## <a name="create-a-new-azure-context-from-subscription-information"></a>Membuat konteks Azure baru dari informasi langganan

Cmdlet [Set-AzContext](/powershell/module/Az.Accounts/Set-AzContext) digunakan untuk membuat konteks Azure baru dan mengaturnya sebagai konteks aktif. Cara termudah untuk membuat konteks Azure baru adalah dengan menggunakan informasi langganan yang ada. Cmdlet dirancang untuk mengambil objek output dari `Get-AzSubscription` sebagai nilai piped dan mengkonfigurasi konteks Azure baru:

```azurepowershell-interactive
Get-AzSubscription -SubscriptionName 'MySubscriptionName' |
  Set-AzContext -Name 'MyContextName'
```

Atau berikan nama atau ID langganan dan ID penyewa jika perlu:

```azurepowershell-interactive
Set-AzContext -Name 'MyContextName' -Subscription 'MySubscriptionName' -Tenant '00000000-0000-0000-0000-000000000000'
```

`Name` Jika parameter dihilangkan, maka nama dan ID langganan digunakan sebagai nama konteks dalam format `Subscription Name (subscription-id)`.

## <a name="change-the-active-azure-context"></a>Mengubah konteks Azure aktif

Keduanya `Set-AzContext` dan [Select-AzContext](/powershell/module/az.accounts/set-azcontext) dapat digunakan untuk mengubah konteks Azure aktif. Seperti yang dijelaskan dalam [Membuat konteks Azure baru](#create-a-new-azure-context-from-subscription-information), `Set-AzContext` membuat konteks Azure baru untuk langganan jika tidak ada, lalu mengalihkan konteks aktif ke konteks tersebut.

`Select-AzContext` dimaksudkan untuk digunakan hanya dengan konteks Azure yang ada dan bekerja mirip dengan menggunakan `Set-AzContext -Context`, tetapi dirancang untuk digunakan dengan perpipaan:

```azurepowershell-interactive
Set-AzContext -Context $(Get-AzContext -Name 'mycontext') # Set a context with an inline Azure context object
Get-AzContext -Name 'mycontext' | Select-AzContext # Set a context with a piped Azure context object
```

Seperti banyak perintah manajemen akun dan konteks lainnya di Azure PowerShell, `Set-AzContext` dan `Select-AzContext` mendukung `Scope` parameter sehingga Anda dapat mengontrol berapa lama konteks aktif. `Scope` memungkinkan Anda mengubah konteks aktif satu sesi tanpa mengubah default:

```azurepowershell-interactive
Get-AzContext -Name 'mycontext' | Select-AzContext -Scope Process
```

Untuk menghindari pengalihan konteks untuk seluruh sesi PowerShell, semua perintah Azure PowerShell dapat dijalankan terhadap konteks tertentu dengan `AzContext` parameter:

```azurepowershell-interactive
$context = Get-AzContext -Name "mycontext"
New-AzVM -Name ExampleVM -AzContext $context
```

Penggunaan utama lainnya dari konteks dengan cmdlet Azure PowerShell adalah untuk menjalankan perintah latar belakang. Untuk mempelajari selengkapnya tentang menjalankan Pekerjaan PowerShell menggunakan Azure PowerShell, lihat [Menjalankan cmdlet Azure PowerShell di PowerShell Jobs](using-psjobs.md).

## <a name="save-azure-contexts-across-powershell-sessions"></a>Menyimpan konteks Azure di seluruh sesi PowerShell

Secara default, konteks Azure disimpan untuk digunakan di antara sesi PowerShell. Anda mengubah perilaku ini dengan cara berikut:

* Masuk menggunakan `-Scope Process` dengan `Connect-AzAccount`.

  ```azurepowershell
  Connect-AzAccount -Scope Process
  ```

  Konteks Azure yang dikembalikan sebagai bagian dari masuk ini _hanya_ berlaku untuk sesi saat ini dan tidak akan disimpan secara otomatis, terlepas dari pengaturan simpan otomatis konteks Azure PowerShell.
* Nonaktifkan simpan otomatis konteks dalam Azure PowerShell dengan cmdlet [Disable-AzContextAutosave](/powershell/module/az.accounts/disable-azcontextautosave).
  Menonaktifkan penyimpanan otomatis konteks __tidak__ menghapus token yang disimpan. Untuk mempelajari cara menghapus informasi konteks Azure yang disimpan, lihat [Menghapus konteks dan kredensial Azure](#remove-azure-contexts-and-stored-credentials).
* Secara eksplisit mengaktifkan autosave konteks Azure dapat diaktifkan dengan cmdlet [Enable-AzContextAutosave](/powershell/module/az.accounts/enable-azcontextautosave) . Dengan mengaktifkan simpan otomatis, semua konteks pengguna disimpan secara lokal untuk sesi PowerShell nanti.
* Menyimpan konteks secara manual dengan [Save-AzContext](/powershell/module/az.accounts/save-azcontext) untuk digunakan dalam sesi PowerShell mendatang, di mana konteksnya dapat dimuat dengan [Import-AzContext](/powershell/module/az.accounts/import-azcontext):

  ```azurepowershell
  Save-AzContext -Path current-context.json # Save the current context
  Save-AzContext -Profile $profileObject -Path other-context.json # Save a context object
  Import-AzContext -Path other-context.json # Load the context from a file and set it to the current context
  ```

> [!WARNING]
> Menonaktifkan penyimpanan otomatis konteks __tidak__ menghapus informasi konteks tersimpan yang disimpan. Untuk menghapus informasi yang tersimpan, gunakan cmdlet [Clear-AzContext](/powershell/module/az.accounts/Clear-AzContext) . Untuk selengkapnya tentang menghapus konteks yang disimpan, lihat [Menghapus konteks dan kredensial](#remove-azure-contexts-and-stored-credentials).

Masing-masing perintah ini mendukung `Scope` parameter, yang dapat mengambil nilai `Process` untuk hanya berlaku untuk proses berjalan saat ini. Misalnya, untuk memastikan bahwa konteks yang baru dibuat tidak disimpan setelah keluar dari sesi PowerShell:

```azurepowershell-interactive
Disable-AzContextAutosave -Scope Process
$context2 = Set-AzContext -Subscription "sub-id" -Tenant "other-tenant"
```

Informasi konteks dan token disimpan di `$env:USERPROFILE\.Azure` direktori di Windows, dan di `$HOME/.Azure` platform lain. Informasi sensitif seperti ID langganan dan ID penyewa mungkin masih akan diekspos dalam informasi yang disimpan, melalui log, atau konteks yang disimpan. Untuk mempelajari cara menghapus informasi yang disimpan, lihat bagian [Hapus konteks dan kredensial](#remove-azure-contexts-and-stored-credentials) .

## <a name="remove-azure-contexts-and-stored-credentials"></a>Menghapus konteks Azure dan kredensial tersimpan

Untuk menghapus konteks dan kredensial Azure:

* Keluar dari akun dengan [Disconnect-AzAccount](/powershell/module/az.accounts/disconnect-azaccount). Anda dapat keluar dari akun apa pun baik berdasarkan akun atau konteks:

  ```azurepowershell-interactive
  Disconnect-AzAccount # Disconnect active account
  Disconnect-AzAccount -Username 'user@contoso.com' # Disconnect by account name

  Disconnect-AzAccount -ContextName 'subscription2' # Disconnect by context name
  Disconnect-AzAccount -AzureContext $contextObject # Disconnect using context object information
  ```

  Memutuskan sambungan selalu menghapus token autentikasi yang disimpan dan menghapus konteks tersimpan yang terkait dengan pengguna atau konteks yang terputus.
* Gunakan [Clear-AzContext](/powershell/module/az.accounts/Clear-AzContext). Cmdlet ini selalu menghapus konteks yang tersimpan, token otentikasi, dan tanda-tanda Anda keluar.
* Menghapus konteks dengan [Remove-AzContext](/powershell/module/az.accounts/remove-azcontext):

  ```azurepowershell-interactive
  Remove-AzContext -Name 'mycontext' # Remove by name
  Get-AzContext -Name 'mycontext' | Remove-AzContext # Remove by piping Azure context object
  ```

  Jika Anda menghapus konteks aktif, Anda akan terputus dari Azure dan perlu mengotorisasi ulang dengan `Connect-AzAccount`.

## <a name="see-also"></a>Lihat juga

* [Jalankan cmdlet Azure PowerShell di Pekerjaan PowerShell](using-psjobs.md)
* [Terminologi Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis#terminology)
* [Referensi Az.Accounts](/powershell/module/az.accounts)
