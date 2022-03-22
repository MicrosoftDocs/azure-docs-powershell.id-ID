---
title: Mempertahankan info masuk pengguna di seluruh sesi PowerShell
description: Pelajari cara menggunakan kembali info masuk Azure dan informasi lainnya di beberapa sesi PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 2e32dbda062c2642fcdb01c68998ac400fd3fed7
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429373"
---
# <a name="persist-user-credentials-across-powershell-sessions"></a>Mempertahankan info masuk pengguna di seluruh sesi PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Azure PowerShell menawarkan fitur yang disebut **Azure Context Autosave**, yang memberikan fitur-fitur berikut:

- Retensi informasi masuk untuk digunakan kembali di sesi PowerShell baru.
- Penggunaan tugas latar belakang yang lebih mudah untuk menjalankan cmdlet yang sudah berjalan lama.
- Beralih antar akun, langganan, dan lingkungan tanpa masuk terpisah.
- Eksekusi tugas menggunakan info masuk dan langganan yang berbeda, secara bersamaan, dari sesi PowerShell yang sama.

## <a name="azure-contexts-defined"></a>Konteks Azure yang ditentukan

*Konteks Azure* adalah kumpulan informasi yang menentukan target cmdlet Azure PowerShell. Konteks Azure terdiri dari lima bagian:

- *Akun* - Nama Pengguna atau Perwakilan Layanan yang digunakan untuk mengautentikasi komunikasi dengan Azure
- *Langganan* - Langganan Azure dengan Sumber Daya yang ditindaklanjuti.
- *Penyewa* - Penyewa Azure Active Directory yang berisi langganan Anda. Penyewa lebih penting untuk autentikasi ServicePrincipal.
- *Lingkungan* - Azure Cloud tertentu yang menjadi target, biasanya Azure global Cloud.
  Namun, pengaturan lingkungan memungkinkan Anda untuk menargetkan cloud (Azure Stack) Nasional, Pemerintah, dan lokal juga.
- *Info masuk* - Informasi yang digunakan oleh Azure untuk memverifikasi identitas Anda dan mengonfirmasi otorisasi Anda untuk mengakses sumber daya di Azure

Dalam rilis sebelumnya, Azure Context harus dibuat setiap kali Anda membuka sesi PowerShell baru. Dimulai dengan Azure PowerShell v4.4.0, Azure Contexts dapat secara otomatis disimpan setiap kali membuka sesi PowerShell baru.

## <a name="automatically-save-the-context-for-the-next-sign-in"></a>Secara otomatis menyimpan konteks untuk masuk berikutnya

Di versi 6.3.0 dan versi lebih baru, Azure PowerShell menyimpan informasi konteks Anda secara otomatis di antara sesi. Untuk mengatur PowerShell agar lupa konteks dan info masuk Anda, gunakan `Disable-AzureRmContextAutoSave`. Anda harus masuk ke Azure setiap kali membuka sesi PowerShell.

Untuk mengizinkan Azure PowerShell mengingat konteks Anda setelah sesi PowerShell ditutup, gunakan `Enable-AzureRmContextAutosave`. Informasi konteks dan info masuk secara otomatis disimpan dalam folder tersembunyi khusus di direktori pengguna Anda (`%AppData%\Roaming\Windows Azure PowerShell`). Setiap sesi PowerShell baru menargetkan konteks yang digunakan di sesi terakhir Anda.

Cmdlet yang memungkinkan Anda mengelola konteks Azure juga memungkinkan Anda mengontrol berbutir halus. Jika Anda ingin perubahan hanya berlaku untuk sesi PowerShell saat ini (cakupan `Process`) atau setiap sesi PowerShell (cakupan `CurrentUser`). Opsi ini dibahas secara detail dalam [Menggunakan Cakupan Konteks](#using-context-scopes).

## <a name="running-azure-powershell-cmdlets-as-background-jobs"></a>Menjalankan cmdlet Azure PowerShell sebagai pekerjaan latar belakang

Fitur **Azure Context Autosave** juga memungkinkan Anda berbagi konteks dengan pekerjaan latar belakang PowerShell. PowerShell memungkinkan Anda memulai dan memantau tugas yang telah lama dijalankan sebagai pekerjaan latar belakang tanpa harus menunggu tugas selesai. Anda dapat berbagi info masuk dengan pekerjaan latar belakang dengan dua cara berbeda:

- Meneruskan konteks sebagai argumen

  Sebagian besar cmdlet AzureRM memungkinkan Anda meneruskan konteks sebagai parameter ke cmdlet. Anda dapat meneruskan konteks ke pekerjaan latar belakang seperti yang ditunjukkan dalam contoh berikut:

  ```powershell
 $job = Start-Job { param ($ctx) New-AzureRmVm -AzureRmContext $ctx [... Additional parameters ...]} -ArgumentList (Get-AzureRmContext)
  ```

- Menggunakan konteks default dengan Simpan-otomatis diaktifkan

  Jika Anda telah mengaktifkan **Simpan-otomatis Konteks**, pekerjaan latar belakang secara otomatis menggunakan konteks tersimpan default.

  ```powershell
  $job = Start-Job { New-AzureRmVm [... Additional parameters ...]}
  ```

Saat Anda perlu mengetahui hasil dari tugas latar belakang, gunakan `Get-Job` untuk memeriksa status pekerjaan dan `Wait-Job` untuk menunggu Pekerjaan selesai. Gunakan `Receive-Job` untuk menangkap atau menampilkan output dari pekerjaan latar belakang. Untuk informasi selengkapnya, lihat [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).

## <a name="creating-selecting-renaming-and-removing-contexts"></a>Membuat, memilih, mengganti nama, dan menghapus konteks

Untuk membuat konteks, Anda harus masuk ke Azure. Cmdlet `Connect-AzureRmAccount` (atau aliasnya, `Login-AzureRmAccount`) menetapkan konteks default yang digunakan oleh cmdlet Azure PowerShell, dan memungkinkan Anda mengakses penyewa atau langganan apa pun yang diizinkan oleh info masuk Anda.

Untuk menambahkan konteks baru setelah masuk, gunakan `Set-AzureRmContext` (atau aliasnya, `Select-AzureRmSubscription`).

```azurepowershell
Set-AzureRMContext -Subscription 'Contoso Subscription 1' -Name 'Contoso1'
```

Contoh sebelumnya menambahkan konteks baru yang menargetkan 'Contoso Subscription 1' menggunakan info masuk Anda saat ini. Konteks baru ini diberi nama 'Contoso1'. Jika Anda tidak memberikan nama untuk konteks tersebut, nama default, menggunakan ID akun dan ID langganan digunakan.

Untuk mengganti nama konteks yang ada, gunakan cmdlet `Rename-AzureRmContext`. Contohnya:

```azurepowershell
Rename-AzureRmContext '[user1@contoso.org; 123456-7890-1234-564321]' 'Contoso2'
```

Contoh ini mengganti nama konteks dengan nama `[user1@contoso.org; 123456-7890-1234-564321]` otomatis menjadi nama sederhana 'Contoso2'. Cmdlet yang mengelola konteks juga menggunakan penyelesaian tab, memungkinkan Anda memilih konteks dengan cepat.

Terakhir, untuk menghapus konteks, gunakan cmdlet `Remove-AzureRmContext`.  Contohnya:

```azurepowershell
Remove-AzureRmContext Contoso2
```

Lupa konteks yang diberi nama 'Contoso2'. Anda dapat membuat ulang konteks ini menggunakan `Set-AzureRmContext`

## <a name="removing-credentials"></a>Menghapus info masuk

Anda dapat menghapus semua info masuk dan konteks terkait untuk pengguna atau perwakilan layanan yang menggunakan `Disconnect-AzureRmAccount` (juga dikenal sebagai `Logout-AzureRmAccount`). Saat dijalankan tanpa parameter, cmdlet `Disconnect-AzureRmAccount` menghapus semua info masuk dan konteks yang terkait dengan Pengguna atau Perwakilan Layanan dalam konteks saat ini. Anda dapat meneruskan Nama Pengguna, Nama Perwakilan Layanan, atau konteks untuk menargetkan perwakilan tertentu.

```azurepowershell
Disconnect-AzureRmAccount user1@contoso.org
```

## <a name="using-context-scopes"></a>Menggunakan cakupan konteks

Terkadang, Anda mungkin ingin memilih, mengubah, atau menghapus konteks dalam sesi PowerShell tanpa memengaruhi sesi lain. Untuk mengubah perilaku default cmdlet konteks, gunakan parameter `Scope`. Cakupan `Process` menimpa perilaku default dengan membuatnya hanya berlaku untuk sesi saat ini. Sebaliknya, cakupan `CurrentUser` mengubah konteks di semua sesi, bukan hanya sesi saat ini.

Misalnya, untuk mengubah konteks default dalam sesi PowerShell saat ini tanpa memengaruhi jendela lain, atau konteks yang digunakan saat sesi dibuka, gunakan:

```azurepowershell
Select-AzureRmContext Contoso1 -Scope Process
```

## <a name="how-the-context-autosave-setting-is-remembered"></a>Cara pengaturan simpan otomatis konteks diingat

Pengaturan Simpan-otomatis konteks disimpan ke direktori Azure PowerShell pengguna (`%AppData%\Roaming\Windows Azure PowerShell`). Beberapa jenis akun komputer mungkin tidak memiliki akses ke direktori ini. Untuk skenario seperti itu, Anda dapat menggunakan variabel lingkungan

```azurepowershell
$env:AzureRmContextAutoSave=$true
```

Saat diatur ke `$true`, konteks disimpan secara otomatis. Jika diatur ke `$false`, konteks tidak disimpan.

## <a name="changes-to-the-azurermprofile-module"></a>Perubahan pada modul AzureRM.Profile

Cmdlet baru untuk mengelola konteks

- [Enable-AzureRmContextAutosave][enable] - Mengizinkan penyimpanan konteks antara sesi powershell.
  Setiap perubahan mengubah konteks global.
- [Disable-AzureRmContextAutosave][disable] - Menonaktifkan penyimpanan otomatis konteks. Setiap sesi PowerShell baru diperlukan untuk masuk lagi.
- [Select-AzureRmContext][select] - Memilih konteks sebagai default. Semua cmdlet menggunakan info masuk dalam konteks ini untuk autentikasi.
- [Disconnect-AzureRmAccount][remove-cred] - Menghapus semua info masuk dan konteks yang terkait dengan akun.
- [Remove-AzureRmContext][remove-context] - Menghapus konteks bernama.
- [Rename-AzureRmContext][rename] - Mengganti nama konteks yang ada.

Perubahan pada cmdlet profil yang ada

- [Add-AzureRmAccount][login] - Mengizinkan cakupan masuk ke proses atau pengguna saat ini.
  Izinkan penamaan konteks default setelah autentikasi.
- [Import-AzureRmContext][import] - Mengizinkan cakupan masuk ke proses atau pengguna saat ini.
- [Set-AzureRmContext][set-context] - Mengizinkan pemilihan konteks bernama yang ada, dan perubahan cakupan pada proses atau pengguna saat ini.

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
