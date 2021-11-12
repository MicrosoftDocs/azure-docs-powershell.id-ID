---
title: Persist user credentials across PowerShell sessions
description: Pelajari cara menggunakan kembali kredensial Azure dan informasi lainnya di beberapa sesi PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 2e32dbda062c2642fcdb01c68998ac400fd3fed7
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429373"
---
# <a name="persist-user-credentials-across-powershell-sessions"></a>Persist user credentials across PowerShell sessions

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Azure PowerShell menawarkan fitur yang disebut Simpan Otomatis Konteks **Azure,** yang memberikan fitur berikut ini:

- Penyimpanan informasi masuk untuk digunakan kembali di sesi PowerShell yang baru.
- Penggunaan tugas latar belakang yang lebih mudah untuk menjalankan cmdlet yang berjalan dalam waktu lama.
- Beralih antar akun, langganan, dan lingkungan tanpa masuk terpisah.
- Eksekusi tugas menggunakan kredensial dan langganan yang berbeda, secara bersamaan, dari sesi PowerShell yang sama.

## <a name="azure-contexts-defined"></a>Konteks Azure yang ditentukan

Konteks *Azure* adalah kumpulan informasi yang menentukan target cmdlet Azure PowerShell lanjut. Konteksnya terdiri dari lima bagian:

- Akun *-* Nama Pengguna atau Prinsipal Layanan yang digunakan untuk mengautentikasi komunikasi dengan Azure
- Langganan  - Langganan Azure dengan Sumber Daya yang sedang ditindaklanjuti.
- Penyewa  - Penyewa Azure Active Directory yang berisi langganan Anda. Penyewa lebih penting pada autentikasi ServicePrincipal.
- Lingkungan  - Azure Cloud tertentu yang ditargetkan, biasanya Azure global Cloud.
  Namun, pengaturan lingkungan memungkinkan Anda menargetkan awan Nasional, Pemerintah, dan lokal (Azure Stack).
- *Kredensial* - Informasi yang digunakan oleh Azure untuk memverifikasi identitas Anda dan mengonfirmasi otorisasi Anda untuk mengakses sumber daya di Azure

Dalam rilis sebelumnya, Konteks Azure harus dibuat setiap kali Anda membuka sesi PowerShell baru. Dimulai dengan Azure PowerShell v4.4.0, Azure Contexts dapat disimpan secara otomatis setiap kali membuka sesi PowerShell baru.

## <a name="automatically-save-the-context-for-the-next-sign-in"></a>Menyimpan konteks untuk masuk berikutnya secara otomatis

Di versi 6.3.0 dan yang lebih baru, Azure PowerShell mempertahankan informasi konteks Anda secara otomatis antar sesi. Untuk mengatur PowerShell agar lupa konteks dan kredensial Anda, gunakan `Disable-AzureRmContextAutoSave` . Anda harus masuk ke Azure setiap kali membuka sesi PowerShell.

Untuk memungkinkan Azure PowerShell mengingat konteks Anda setelah sesi PowerShell ditutup, gunakan `Enable-AzureRmContextAutosave` . Informasi konteks dan kredensial secara otomatis disimpan dalam folder tersembunyi khusus di direktori pengguna Anda ( `%AppData%\Roaming\Windows Azure PowerShell` ). Setiap sesi PowerShell baru menargetkan konteks yang digunakan di sesi terakhir Anda.

Cmdlet yang memungkinkan Anda mengelola konteks Azure juga memungkinkan kontrol tinggi tinggi. Jika Anda ingin perubahan diterapkan hanya pada sesi PowerShell ( `Process` lingkup) saat ini atau setiap sesi PowerShell ( `CurrentUser` lingkup). Opsi ini dibahas dalam detail mode [dalam Penggunaan Lingkup Konteks](#using-context-scopes).

## <a name="running-azure-powershell-cmdlets-as-background-jobs"></a>Menjalankan Azure PowerShell cmdlet sebagai pekerjaan latar belakang

Fitur **Simpan Otomatis Konteks Azure juga** memungkinkan Anda berbagi konteks dengan pekerjaan latar belakang PowerShell. PowerShell memungkinkan Anda memulai dan memantau tugas yang panjang sebagai pekerjaan latar belakang tanpa harus menunggu tugas selesai. Anda bisa berbagi kredensial dengan pekerjaan latar belakang dalam dua cara berbeda:

- Memberikan konteks sebagai argumen

  Sebagian besar cmdlet AzureRM memungkinkan Anda menyampaikan konteks sebagai parameter ke cmdlet. Anda dapat menyampaikan konteks ke pekerjaan latar belakang seperti yang diperlihatkan dalam contoh berikut:

  ```powershell
 $job = Start-Job { param ($ctx) New-AzureRmVm -AzureRmContext $ctx [... Additional parameters ...]} -ArgumentList (Get-AzureRmContext)
  ```

- Menggunakan konteks default dengan Simpan Otomatis diaktifkan

  Jika Anda telah mengaktifkan **Simpan Otomatis Konteks**, pekerjaan latar belakang secara otomatis menggunakan konteks default yang disimpan.

  ```powershell
  $job = Start-Job { New-AzureRmVm [... Additional parameters ...]}
  ```

Saat Anda perlu mengetahui hasil dari tugas latar belakang, gunakan untuk memeriksa status pekerjaan `Get-Job` dan untuk menunggu Pekerjaan `Wait-Job` selesai. Gunakan `Receive-Job` untuk merekam atau menampilkan output pekerjaan latar belakang. Untuk informasi selengkapnya, lihat [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).

## <a name="creating-selecting-renaming-and-removing-contexts"></a>Membuat, memilih, mengganti nama, dan menghapus konteks

Untuk membuat konteks, Anda harus masuk ke Azure. Cmdlet (atau aliasnya, ) mengatur konteks default yang digunakan oleh cmdlet Azure PowerShell, dan memungkinkan Anda mengakses penyewa atau langganan apa pun yang diizinkan `Connect-AzureRmAccount` `Login-AzureRmAccount` oleh kredensial Anda.

Untuk menambahkan konteks baru setelah masuk, gunakan `Set-AzureRmContext` (atau aliasnya, `Select-AzureRmSubscription` ).

```azurepowershell
Set-AzureRMContext -Subscription 'Contoso Subscription 1' -Name 'Contoso1'
```

Contoh sebelumnya menambahkan konteks baru yang menargetkan 'Langganan Contoso 1' menggunakan kredensial saat ini. Konteks baru diberi nama 'Contoso1'. Jika Anda tidak menyediakan nama untuk konteks, nama default, menggunakan ID akun dan ID langganan digunakan.

Untuk mengganti nama konteks yang sudah ada, gunakan `Rename-AzureRmContext` cmdlet. Misalnya:

```azurepowershell
Rename-AzureRmContext '[user1@contoso.org; 123456-7890-1234-564321]' 'Contoso2'
```

Contoh ini mengganti nama konteks dengan nama otomatis `[user1@contoso.org; 123456-7890-1234-564321]` menjadi nama sederhana 'Contoso2'. Cmdlet yang mengelola konteks juga menggunakan penyelesaian tab, memungkinkan Anda memilih konteks dengan cepat.

Terakhir, untuk menghapus konteks, gunakan `Remove-AzureRmContext` cmdlet.  Misalnya:

```azurepowershell
Remove-AzureRmContext Contoso2
```

Lupa konteks yang bernama 'Contoso2'. Anda dapat membuat ulang konteks ini menggunakan `Set-AzureRmContext`

## <a name="removing-credentials"></a>Menghapus kredensial

Anda bisa menghapus semua kredensial dan konteks terkait untuk pengguna atau prinsipal layanan menggunakan `Disconnect-AzureRmAccount` (juga dikenal sebagai `Logout-AzureRmAccount` ). Saat dijalankan tanpa parameter, cmdlet menghapus semua kredensial dan konteks yang terkait dengan Pengguna atau `Disconnect-AzureRmAccount` Prinsipal Layanan dalam konteks saat ini. Anda dapat menyampaikan Nama Pengguna, Nama Prinsipal Layanan, atau konteks untuk menargetkan pokok tertentu.

```azurepowershell
Disconnect-AzureRmAccount user1@contoso.org
```

## <a name="using-context-scopes"></a>Menggunakan lingkup konteks

Terkadang, Anda mungkin ingin memilih, mengubah, atau menghapus konteks dalam sesi PowerShell tanpa memengaruhi sesi lainnya. Untuk mengubah perilaku default cmdlet konteks, gunakan `Scope` parameter. Lingkup `Process` mengesampingkan perilaku default dengan membuatnya berlaku hanya untuk sesi saat ini. `CurrentUser`Sebaliknya, lingkup mengubah konteks di semua sesi, bukan hanya sesi saat ini.

Sebagai contoh, untuk mengubah konteks default dalam sesi PowerShell saat ini tanpa memengaruhi jendela lain, atau konteks yang digunakan kali berikutnya sesi dibuka, gunakan:

```azurepowershell
Select-AzureRmContext Contoso1 -Scope Process
```

## <a name="how-the-context-autosave-setting-is-remembered"></a>Bagaimana pengaturan simpan otomatis konteks diingat

Pengaturan Simpan Otomatis konteks disimpan ke pengguna atau Azure PowerShell pengguna ( `%AppData%\Roaming\Windows Azure PowerShell` ). Beberapa jenis akun komputer mungkin tidak memiliki akses ke direktori ini. Untuk skenario tersebut, Anda dapat menggunakan variabel lingkungan

```azurepowershell
$env:AzureRmContextAutoSave=$true
```

Ketika diatur ke `$true` , konteks disimpan secara otomatis. Jika diatur `$false` ke , konteks tidak akan disimpan.

## <a name="changes-to-the-azurermprofile-module"></a>Perubahan pada modul AzureRM.Profile

Cmdlet baru untuk mengelola konteks

- [Enable-AzureRmContextAutosave][enable] - Perbolehkan menyimpan konteks antar sesi powershell.
  Setiap perubahan akan mengubah konteks global.
- [Disable-AzureRmContextAutosave][disable] - Menonaktifkan pengarsipan otomatis konteks. Setiap sesi PowerShell yang baru diperlukan untuk masuk lagi.
- [Pilih-AzureRmContext][select] - Pilih konteks sebagai default. Semua cmdlet menggunakan kredensial dalam konteks ini untuk autentikasi.
- [Disconnect-AzureRmAccount][remove-cred] - Hapus semua kredensial dan konteks yang terkait dengan akun.
- [Remove-AzureRmContext][remove-context] - Menghapus konteks bernama.
- [Rename-AzureRmContext][rename] - Mengganti nama konteks yang sudah ada.

Perubahan pada cmdlet profil yang sudah ada

- [Add-AzureRmAccount][login] - Memungkinkan penjedaan akses masuk ke proses atau pengguna saat ini.
  Perbolehkan penamaan konteks default setelah autentikasi.
- [Import-AzureRmContext][import] - Memperbolehkan penjedaan akses masuk ke proses atau pengguna saat ini.
- [Set-AzureRmContext][set-context] - Memperbolehkan pilihan konteks bernama yang sudah ada, dan lingkup perubahan pada proses atau pengguna saat ini.

<!-- Hyperlinks -->
[enable]: /powershell/module/azurerm.profile/Enable-AzureRmContextAutosave
[disable]: /powershell/module/azurerm.profile/Disable-AzureRmContextAutosave
[select]: /powershell/module/azurerm.profile/Select-AzureRmContext
[remove-cred]: /powershell/module/azurerm.profile/Disconnect-AzureRmAccount
[remove-context]: /powershell/module/azurerm.profile/Remove-AzureRmContext
[rename]: /powershell/module/azurerm.profile/Rename-AzureRmContext

<!-- Updated cmdlets -->
[login]: /powershell/module/azurerm.profile/Connect-AzureRmAccount
[import]:  /powershell/module/azurerm.profile/Import-AzureRmContext
[set-context]: /powershell/module/azurerm.profile/Set-AzureRmContext
