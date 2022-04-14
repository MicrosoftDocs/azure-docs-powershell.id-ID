---
Module Name: Az.Accounts
Module Guid: 342714fc-4009-4863-8afb-a9067e3db04b
Download Help Link: https://docs.microsoft.com/powershell/module/az.accounts
Help Version: 4.6.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Az.Accounts.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Az.Accounts.md
ms.openlocfilehash: 40de141b041837ab06ebef434f24c43c29f95695
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142004890"
---
# Modul Akun Az.
## Deskripsi
Mengelola kredensial dan konfigurasi umum untuk semua modul Azure.

## Cmdlet Az.Accounts
### [Add-AzEnvironment](Add-AzEnvironment.md)
Menambahkan titik akhir dan metadata untuk instans Azure Resource Manager.

### [Clear-AzContext](Clear-AzContext.md)
Hapus semua kredensial, akun, dan informasi langganan Azure.

### [Clear-AzDefault](Clear-AzDefault.md)
Menghapus default yang diatur oleh pengguna dalam konteks saat ini.

### [Koneksi-AzAccount](Connect-AzAccount.md)
Koneksi ke Azure dengan akun yang diautentikasi untuk digunakan dengan cmdlet dari modul Az PowerShell.

### [Disable-AzContextAutosave](Disable-AzContextAutosave.md)
Nonaktifkan penyimpanan otomatis kredensial Azure.  Informasi masuk Anda akan terlupakan pada kali berikutnya Anda membuka jendela PowerShell

### [Disable-AzDataCollection](Disable-AzDataCollection.md)
Menolak mengumpulkan data untuk meningkatkan cmdlet Azure PowerShell. Data dikumpulkan secara default kecuali Anda menolak secara eksplisit.

### [Nonaktifkan-AzureRmAlias](Disable-AzureRmAlias.md)
Menonaktifkan alias prefiks AzureRm untuk modul Az.

### [Putuskan sambungan-AzAccount](Disconnect-AzAccount.md)
Memutuskan koneksi akun Azure yang tersambung dan menghapus semua kredensial dan konteks yang terkait dengan akun tersebut.

### [Enable-AzContextAutosave](Enable-AzContextAutosave.md)
Konteks Azure adalah objek PowerShell yang mewakili langganan aktif Anda untuk menjalankan perintah, dan informasi autentikasi yang diperlukan untuk menyambungkan ke awan Azure. Dengan konteks Azure, Azure PowerShell tidak perlu menulis ulang akun setiap kali Anda beralih langganan. Untuk informasi selengkapnya, lihat [Azure PowerShell objek konteks](https://docs.microsoft.com/powershell/azure/context-persistence).

Cmdlet ini memungkinkan informasi konteks Azure disimpan dan dimuat secara otomatis saat Anda memulai proses PowerShell. Misalnya, saat membuka jendela baru.

### [Enable-AzDataCollection](Enable-AzDataCollection.md)
Memungkinkan Azure PowerShell mengumpulkan data untuk meningkatkan pengalaman pengguna dengan cmdlet Azure PowerShell. Menjalankan cmdlet ini memilih pengumpulan data untuk pengguna saat ini di komputer saat ini. Data dikumpulkan secara default kecuali Anda menolak secara eksplisit.

### [Enable-AzureRmAlias](Enable-AzureRmAlias.md)
Mengaktifkan alias prefiks AzureRm untuk modul Az.

### [Get-AzAccessToken](Get-AzAccessToken.md)
Dapatkan token akses mentah. Saat menggunakan -ResourceUrl, pastikan nilai cocok dengan lingkungan Azure saat ini. Anda dapat merujuk ke nilai `(Get-AzContext).Environment`.

### [Get-AzContext](Get-AzContext.md)
Mendapatkan metadata yang digunakan untuk mengautentikasi permintaan Resource Manager Azure.

### [Get-AzContextAutosaveSetting](Get-AzContextAutosaveSetting.md)
Menampilkan metadata tentang fitur penyimpanan otomatis konteks, termasuk apakah konteks disimpan secara otomatis, dan tempat informasi konteks dan kredensial yang disimpan dapat ditemukan.

### [Get-AzDefault](Get-AzDefault.md)
Dapatkan default yang diatur oleh pengguna dalam konteks saat ini.

### [Get-AzEnvironment](Get-AzEnvironment.md)
Dapatkan titik akhir dan metadata untuk contoh layanan Azure.

### [Get-AzSubscription](Get-AzSubscription.md)
Dapatkan langganan yang dapat diakses akun saat ini.

### [Get-AzTenant](Get-AzTenant.md)
Mendapatkan penyewa yang diotorisasi untuk pengguna saat ini.

### [Impor-AzContext](Import-AzContext.md)
Memuat informasi autentikasi Azure dari file.

### [Invoke-AzRestMethod](Invoke-AzRestMethod.md)
Membuat dan melakukan permintaan HTTP hanya ke titik akhir manajemen sumber daya Azure

### [Open-AzSurveyLink](Open-AzSurveyLink.md)
Buka tautan survei di browser default.

### [Register-AzModule](Register-AzModule.md)
HANYA UNTUK PENGGUNAAN INTERNAL - Menyediakan Dukungan Runtime untuk cmdlet Yang Dihasilkan AutoRest

### [Hapus-AzContext](Remove-AzContext.md)
Menghapus konteks dari kumpulan konteks yang tersedia

### [Hapus-AzEnvironment](Remove-AzEnvironment.md)
Menghapus titik akhir dan metadata untuk menyambungkan ke instans Azure tertentu.

### [Ganti nama-AzContext](Rename-AzContext.md)
Mengganti nama konteks Azure.  Secara default konteks dinamai menurut akun pengguna dan langganan.

### [Resolve-AzError](Resolve-AzError.md)
Menampilkan informasi mendetail tentang kesalahan PowerShell, dengan detail yang diperluas untuk kesalahan Azure PowerShell.

### [Save-AzContext](Save-AzContext.md)
Menyimpan informasi autentikasi saat ini untuk digunakan dalam sesi PowerShell lainnya.

### [Pilih-AzContext](Select-AzContext.md)
Pilih langganan dan akun untuk ditargetkan dalam cmdlet Azure PowerShell

### [Kirim Umpan Balik](Send-Feedback.md)
Mengirim umpan balik ke tim Azure PowerShell melalui sekumpulan perintah yang dipandu.

### [Set-AzContext](Set-AzContext.md)
Mengatur penyewa, langganan, dan lingkungan untuk cmdlet yang digunakan dalam sesi saat ini.

### [Set-AzDefault](Set-AzDefault.md)
Mengatur default dalam konteks saat ini

### [Set-AzEnvironment](Set-AzEnvironment.md)
Mengatur properti untuk lingkungan Azure.

### [Menghapus instalan AzureRm](Uninstall-AzureRm.md)
Menghapus semua modul AzureRm dari komputer.

