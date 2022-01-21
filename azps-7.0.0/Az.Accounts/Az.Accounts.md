---
Module Name: Az.Accounts
Module Guid: 342714fc-4009-4863-8afb-a9067e3db04b
Download Help Link: https://docs.microsoft.com/powershell/module/az.accounts
Help Version: 4.6.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Az.Accounts.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Az.Accounts.md
ms.openlocfilehash: 40de141b041837ab06ebef434f24c43c29f95695
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136526033"
---
# Az.Accounts Module
## Deskripsi
Mengelola kredensial dan konfigurasi umum untuk semua modul Azure.

## Cmdlet Az.Accounts
### [Add-AzEnvironment](Add-AzEnvironment.md)
Menambahkan titik akhir dan metadata untuk contoh Manajer Sumber Daya Azure.

### [Clear-AzContext](Clear-AzContext.md)
Hapus semua kredensial, akun, dan informasi langganan Azure.

### [Clear-AzDefault](Clear-AzDefault.md)
Menghapus pengaturan default yang ditetapkan oleh pengguna dalam konteks saat ini.

### [Koneksi-AzAccount](Connect-AzAccount.md)
Koneksi ke Azure dengan akun terautentikasi untuk digunakan dengan cmdlet dari modul Az PowerShell.

### [Disable-AzContextAutosave](Disable-AzContextAutosave.md)
Nonaktifkan penyimpanan otomatis kredensial Azure.  Informasi masuk Anda akan lupa saat berikutnya Anda membuka jendela PowerShell

### [Disable-AzDataCollection](Disable-AzDataCollection.md)
Memilih untuk tidak mengumpulkan data untuk meningkatkan Azure PowerShell cmdlet. Data akan dikumpulkan secara default kecuali Anda secara eksplisit memilih untuk tidak mengikuti.

### [Disable-AzureRmAlias](Disable-AzureRmAlias.md)
Menonaktifkan alias prefiks AzureRm untuk modul Az.

### [Disconnect-AzAccount](Disconnect-AzAccount.md)
Memutuskan koneksi akun Azure yang tersambung dan menghapus semua kredensial dan konteks yang terkait dengan akun tersebut.

### [Enable-AzContextAutosave](Enable-AzContextAutosave.md)
Konteks Azure adalah objek PowerShell yang mewakili langganan aktif untuk dijalankan, dan informasi autentikasi yang diperlukan untuk tersambung ke cloud Azure. Dengan konteks Azure, Azure PowerShell tidak perlu mengautentikasi ulang akun Anda setiap kali beralih langganan. Untuk informasi selengkapnya, lihat [Azure PowerShell objek konteks](https://docs.microsoft.com/powershell/azure/context-persistence).

Cmdlet ini memungkinkan informasi konteks Azure disimpan dan dimuat secara otomatis saat Anda memulai proses PowerShell. Misalnya, ketika membuka jendela baru.

### [Enable-AzDataCollection](Enable-AzDataCollection.md)
Memungkinkan Azure PowerShell mengumpulkan data untuk meningkatkan pengalaman pengguna dengan cmdlet Azure PowerShell cmdlet. Menjalankan cmdlet ini memungkinkan pengumpulan data untuk pengguna saat ini di komputer saat ini. Data akan dikumpulkan secara default kecuali Anda secara eksplisit memilih untuk tidak mengikuti.

### [Enable-AzureRmAlias](Enable-AzureRmAlias.md)
Mengaktifkan alias prefiks AzureRm untuk modul Az.

### [Get-AzAccessToken](Get-AzAccessToken.md)
Dapatkan token akses mentah. Ketika menggunakan -ResourceUrl, pastikan nilai cocok dengan lingkungan Azure saat ini. Anda mungkin merujuk ke nilai `(Get-AzContext).Environment` .

### [Get-AzContext](Get-AzContext.md)
Dapatkan metadata yang digunakan untuk mengautentikasi permintaan Azure Resource Manager.

### [Get-AzContextAutosaveSetting](Get-AzContextAutosaveSetting.md)
Menampilkan metadata tentang fitur simpan otomatis konteks, termasuk apakah konteks disimpan secara otomatis, dan di mana informasi kredensial dan konteks yang disimpan dapat ditemukan.

### [Get-AzDefault](Get-AzDefault.md)
Atur pengaturan default oleh pengguna dalam konteks saat ini.

### [Get-AzEnvironment](Get-AzEnvironment.md)
Dapatkan titik akhir dan metadata untuk contoh layanan Azure.

### [Get-AzSubscription](Get-AzSubscription.md)
Dapatkan langganan yang bisa diakses oleh akun saat ini.

### [Get-AzTenant](Get-AzTenant.md)
Mendapatkan penyewa yang diotorisasi untuk pengguna saat ini.

### [Import-AzContext](Import-AzContext.md)
Memuat informasi autentikasi Azure dari file.

### [Invoke-AzMethod](Invoke-AzRestMethod.md)
Membangun dan menjalankan permintaan HTTP hanya ke titik akhir manajemen sumber daya Azure

### [Open-AzSurveyLink](Open-AzSurveyLink.md)
Buka link survei di browser default.

### [Register-AzModule](Register-AzModule.md)
UNTUK INTERNAL USE ONLY - Sediakan Dukungan Runtime untuk cmdlet Auto Runtime Generated

### [Remove-AzContext](Remove-AzContext.md)
Menghapus konteks dari kumpulan konteks yang tersedia

### [Remove-AzEnvironment](Remove-AzEnvironment.md)
Menghapus titik akhir dan metadata untuk terhubung ke instans Azure tertentu.

### [Rename-AzContext](Rename-AzContext.md)
Ganti nama konteks Azure.  Secara default konteks diberi nama berdasarkan akun pengguna dan langganan.

### [Resolve-AzError](Resolve-AzError.md)
Tampilkan informasi mendetail tentang kesalahan PowerShell, dengan detail yang diperluas untuk Azure PowerShell kesalahan.

### [Save-AzContext](Save-AzContext.md)
Menyimpan informasi autentikasi saat ini untuk digunakan di sesi PowerShell lainnya.

### [Select-AzContext](Select-AzContext.md)
Pilih langganan dan akun untuk ditargetkan dalam Azure PowerShell cmdlet

### [Kirim-Umpan Balik](Send-Feedback.md)
Mengirimkan umpan balik Azure PowerShell tim kami melalui kumpulan perintah yang dipandu.

### [Set-AzContext](Set-AzContext.md)
Mengatur penyewa, langganan, dan lingkungan untuk cmdlet yang akan digunakan dalam sesi saat ini.

### [Set-AzDefault](Set-AzDefault.md)
Mengatur default dalam konteks saat ini

### [Set-AzEnvironment](Set-AzEnvironment.md)
Mengatur properti untuk lingkungan Azure.

### [Uninstall-AzureRm](Uninstall-AzureRm.md)
Menghapus semua modul AzureRm dari komputer.

