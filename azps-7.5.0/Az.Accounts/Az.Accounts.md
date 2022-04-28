---
Module Name: Az.Accounts
Module Guid: 342714fc-4009-4863-8afb-a9067e3db04b
Download Help Link: https://docs.microsoft.com/powershell/module/az.accounts
Help Version: 4.6.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Az.Accounts.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Az.Accounts.md
ms.openlocfilehash: 40de141b041837ab06ebef434f24c43c29f95695
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144205787"
---
# Modul Az.Accounts
## Deskripsi
Mengelola kredensial dan konfigurasi umum untuk semua modul Azure.

## Cmdlet Az.Accounts
### [Add-AzEnvironment](Add-AzEnvironment.md)
Menambahkan titik akhir dan metadata untuk instans Azure Resource Manager.

### [Clear-AzContext](Clear-AzContext.md)
Hapus semua informasi masuk, akun, dan langganan Azure.

### [Clear-AzDefault](Clear-AzDefault.md)
Menghapus default yang ditetapkan oleh pengguna dalam konteks saat ini.

### [Connect-AzAccount](Connect-AzAccount.md)
Koneksi ke Azure dengan akun terautentikasi untuk digunakan dengan cmdlet dari modul Az PowerShell.

### [Disable-AzContextAutosave](Disable-AzContextAutosave.md)
Nonaktifkan simpan otomatis kredensial Azure.  Informasi masuk Anda akan dilupakan saat berikutnya Anda membuka jendela PowerShell

### [Disable-AzDataCollection](Disable-AzDataCollection.md)
Memilih untuk tidak mengumpulkan data untuk meningkatkan cmdlet Azure PowerShell. Data dikumpulkan secara default kecuali Anda secara eksplisit memilih keluar.

### [Disable-AzureRmAlias](Disable-AzureRmAlias.md)
Menonaktifkan alias awalan AzureRm untuk modul Az.

### [Disconnect-AzAccount](Disconnect-AzAccount.md)
Memutuskan sambungan akun Azure yang tersambung dan menghapus semua kredensial dan konteks yang terkait dengan akun tersebut.

### [Enable-AzContextAutosave](Enable-AzContextAutosave.md)
Konteks Azure adalah objek PowerShell yang mewakili langganan aktif Anda untuk menjalankan perintah, dan informasi autentikasi yang diperlukan untuk tersambung ke cloud Azure. Dengan konteks Azure, Azure PowerShell tidak perlu mengautentikasi ulang akun Anda setiap kali beralih langganan. Untuk informasi selengkapnya, lihat [Azure PowerShell objek konteks](https://docs.microsoft.com/powershell/azure/context-persistence).

Cmdlet ini memungkinkan informasi konteks Azure disimpan dan dimuat secara otomatis saat Anda memulai proses PowerShell. Misalnya, saat membuka jendela baru.

### [Enable-AzDataCollection](Enable-AzDataCollection.md)
Memungkinkan Azure PowerShell mengumpulkan data untuk meningkatkan pengalaman pengguna dengan cmdlet Azure PowerShell. Menjalankan cmdlet ini memilih untuk pengumpulan data untuk pengguna saat ini pada komputer saat ini. Data dikumpulkan secara default kecuali Anda secara eksplisit memilih keluar.

### [Enable-AzureRmAlias](Enable-AzureRmAlias.md)
Mengaktifkan alias awalan AzureRm untuk modul Az.

### [Get-AzAccessToken](Get-AzAccessToken.md)
Mendapatkan token akses mentah. Saat menggunakan -ResourceUrl, pastikan nilainya cocok dengan lingkungan Azure saat ini. Anda dapat merujuk ke nilai `(Get-AzContext).Environment`.

### [Get-AzContext](Get-AzContext.md)
Mendapatkan metadata yang digunakan untuk mengautentikasi permintaan Azure Resource Manager.

### [Get-AzContextAutosaveSetting](Get-AzContextAutosaveSetting.md)
Tampilkan metadata tentang fitur penyimpanan otomatis konteks, termasuk apakah konteks disimpan secara otomatis, dan di mana konteks dan informasi kredensial yang disimpan dapat ditemukan.

### [Get-AzDefault](Get-AzDefault.md)
Dapatkan default yang ditetapkan oleh pengguna dalam konteks saat ini.

### [Get-AzEnvironment](Get-AzEnvironment.md)
Dapatkan titik akhir dan metadata untuk instans layanan Azure.

### [Get-AzSubscription](Get-AzSubscription.md)
Dapatkan langganan yang dapat diakses akun saat ini.

### [Get-AzTenant](Get-AzTenant.md)
Mendapatkan penyewa yang diotorisasi untuk pengguna saat ini.

### [Import-AzContext](Import-AzContext.md)
Memuat informasi autentikasi Azure dari file.

### [Invoke-AzRestMethod](Invoke-AzRestMethod.md)
Membuat dan melakukan permintaan HTTP ke titik akhir manajemen sumber daya Azure saja

### [Open-AzSurveyLink](Open-AzSurveyLink.md)
Buka tautan survei di browser default.

### [Register-AzModule](Register-AzModule.md)
HANYA UNTUK PENGGUNAAN INTERNAL - Berikan Dukungan Runtime untuk cmdlet Yang Dihasilkan AutoRest

### [Remove-AzContext](Remove-AzContext.md)
Menghapus konteks dari kumpulan konteks yang tersedia

### [Remove-AzEnvironment](Remove-AzEnvironment.md)
Menghapus titik akhir dan metadata untuk menyambungkan ke instans Azure tertentu.

### [Rename-AzContext](Rename-AzContext.md)
Mengganti nama konteks Azure.  Secara default konteks dinamai oleh akun pengguna dan langganan.

### [Resolve-AzError](Resolve-AzError.md)
Tampilkan informasi terperinci tentang kesalahan PowerShell, dengan detail yang diperluas untuk kesalahan Azure PowerShell.

### [Save-AzContext](Save-AzContext.md)
Menyimpan informasi autentikasi saat ini untuk digunakan dalam sesi PowerShell lainnya.

### [Select-AzContext](Select-AzContext.md)
Pilih langganan dan akun yang akan ditargetkan dalam cmdlet Azure PowerShell

### [Kirim-Tanggapan](Send-Feedback.md)
Mengirim umpan balik ke tim Azure PowerShell melalui serangkaian perintah terpandu.

### [Set-AzContext](Set-AzContext.md)
Mengatur penyewa, langganan, dan lingkungan untuk cmdlet yang akan digunakan dalam sesi saat ini.

### [Set-AzDefault](Set-AzDefault.md)
Mengatur default dalam konteks saat ini

### [Set-AzEnvironment](Set-AzEnvironment.md)
Mengatur properti untuk lingkungan Azure.

### [Hapus instalan-AzureRm](Uninstall-AzureRm.md)
Menghapus semua modul AzureRm dari komputer.

