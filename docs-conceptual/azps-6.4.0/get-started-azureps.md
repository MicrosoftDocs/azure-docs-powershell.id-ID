---
title: Mulai menggunakan Azure PowerShell
description: Mulai menggunakan Azure PowerShell
ms.devlang: powershell
ms.topic: get-started-article
ms.date: 09/27/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: bf2b0b6455b3b401011ff92eca2bf3db5c5c4673
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429499"
---
# <a name="get-started-with-azure-powershell"></a>Mulai menggunakan Azure PowerShell

Azure PowerShell dirancang untuk mengelola dan mengelola sumber daya Azure dari baris perintah.
Gunakan Azure PowerShell saat Anda ingin menyusun alat otomatis yang menggunakan model Azure Resource Manager. Coba di browser dengan [Azure Cloud Shell](/azure/cloud-shell/overview), atau instal di komputer lokal Anda.

Artikel ini membantu Anda memulai dengan Azure PowerShell dan mengajarkan konsep inti di baliknya.

## <a name="install-or-run-in-azure-cloud-shell"></a>Menginstal atau menjalankan Azure Cloud Shell

Cara termudah untuk mulai menggunakan Azure PowerShell adalah dengan mencobanya di lingkungan Azure Cloud Shell. Untuk memulai dan menjalankan Cloud Shell, lihat [Mulai cepat PowerShell di Azure Cloud Shell](/azure/cloud-shell/quickstart-powershell). Cloud Shell menjalankan PowerShell di wadah Linux, Windows tersebut tidak tersedia.

Jika sudah siap menginstal di Azure PowerShell lokal Anda, ikuti instruksi di [Menginstal modul Azure PowerShell .](install-az-ps.md)

## <a name="sign-in-to-azure"></a>Masuk ke Azure

Masuk secara interaktif dengan cmdlet [Koneksi-AzAccount.](/powershell/module/az.accounts/connect-azaccount) Lewati langkah ini jika Anda menggunakan Cloud Shell. Sesi Azure Cloud Shell Anda sudah diautentikasi untuk lingkungan, langganan, dan penyewa yang meluncurkan sesi Cloud Shell.

```azurepowershell-interactive
Connect-AzAccount
```

Lingkungan penawaran layanan awan Azure mematuhi hukum penanganan data kawasan. Untuk akun di awan regional, gunakan `Environment` parameter untuk masuk. Dapatkan nama lingkungan untuk kawasan Anda menggunakan cmdlet [Get-AzEnvironment.](/powershell/module/Az.Accounts/Get-AzEnvironment)
Misalnya, untuk masuk ke Azure China 21Vianet:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

Dimulai dengan modul Az PowerShell versi 5.0.0, `Connect-AzAccount` menyajikan perintah masuk berbasis browser interaktif secara default. Anda dapat menentukan `UseDeviceAuthentication` parameter untuk menerima string token yang sebelumnya merupakan default untuk PowerShell versi 6 dan lebih tinggi.

Setelah masuk, Anda akan melihat informasi yang mengindikasikan langganan Azure mana yang aktif. Jika memiliki beberapa langganan Azure dalam akun Anda dan ingin memilih langganan lainnya, dapatkan langganan yang tersedia dengan [Get-AzSubscription](/powershell/module/az.accounts/get-azsubscription) dan gunakan cmdlet [Set-AzContext](/powershell/module/az.accounts/set-azcontext) dengan ID langganan. Untuk informasi selengkapnya tentang cara mengelola langganan Azure di Azure PowerShell, [lihat Menggunakan beberapa langganan Azure.](manage-subscriptions-azureps.md)

Setelah masuk, gunakan cmdlet Azure PowerShell untuk mengakses dan mengelola sumber daya dalam langganan Anda. Untuk mempelajari selengkapnya tentang proses masuk dan metode autentikasi, lihat [Masuk dengan Azure PowerShell](authenticate-azureps.md).

## <a name="find-commands"></a>Menemukan perintah

Azure PowerShell cmdlet mengikuti konvensi penamaan standar untuk PowerShell, `Verb-Noun` . Kata kerja menjelaskan tindakan (contohnya antara lain , , , ) dan kata benda yang menguraikan tipe sumber daya `New` `Get` `Set` `Remove` (contohnya antara `AzVM` lain , , , `AzKeyVaultCertificate` `AzFirewall` `AzVirtualNetworkGateway` ). Kata benda di Azure PowerShell selalu diawali dengan prefiks `Az` . Untuk daftar lengkap kata kerja standar, lihat [Kata kerja yang disetujui untuk Perintah PowerShell](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands).

Mengetahui kata benda, kata kerja, dan modul Azure PowerShell tersedia akan membantu Anda menemukan perintah dengan cmdlet [Get-Command.](/powershell/module/microsoft.powershell.core/get-command) Misalnya, untuk menemukan semua perintah vm terkait yang menggunakan kata `Get` kerja:

```powershell-interactive
Get-Command -Verb Get -Noun AzVM* -Module Az.Compute
```

Untuk membantu Anda menemukan perintah umum, tabel ini mencantumkan tipe sumber daya, modul Azure PowerShell terkait, dan prefiks kata benda untuk digunakan `Get-Command` dengan:

|                              Tipe sumber daya                              |                   Azure PowerShell ini                    |    Prefiks kata benda     |
| ----------------------------------------------------------------------- | ------------------------------------------------------------ | ------------------ |
| [Grup Sumber Daya](/azure/azure-resource-manager/resource-group-overview) | [Az.Resources](/powershell/module/az.resources#resources)    | `AzResourceGroup`  |
| [Mesin virtual](/azure/virtual-machines)                             | [Az.Compute](/powershell/module/az.compute#virtual_machines) | `AzVM`             |
| [Storage akun](/azure/storage/common/storage-introduction)          | [Az.Storage](/powershell/module/az.storage/)                 | `AzStorageAccount` |
| [Kunci Vault](/azure/key-vault/key-vault-whatis)                          | [Az.KeyVault](/powershell/module/az.keyvault)                | `AzKeyVault`       |
| [Aplikasi web](/azure/app-service)                                  | [Situs Web Az.](/powershell/module/az.websites)                | `AzWebApp`         |
| [SQL database](/azure/sql-database)                                    | [az.sql](/powershell/module/az.sql)                          | `AzSqlDatabase`    |

Untuk daftar lengkap modul di Azure PowerShell, lihat daftar modul [Azure PowerShell dihosting di](https://github.com/Azure/azure-powershell/blob/master/documentation/azure-powershell-modules.md) GitHub.

## <a name="telemetry"></a>Telemetri

Azure PowerShell mengumpulkan data telemetri secara default. Microsoft menggabungkan data yang dikumpulkan untuk mengidentifikasi pola penggunaan, untuk mengidentifikasi masalah umum, dan untuk meningkatkan pengalaman Azure PowerShell. Microsoft Azure PowerShell tidak mengumpulkan data pribadi atau pribadi apa pun. Untuk menonaktifkan pengumpulan data, Anda harus secara eksplisit memilih untuk tidak menggunakan [Disable-AzDataCollection](/powershell/module/az.accounts/disable-azdatacollection).

## <a name="learn-azure-powershell-basics-with-quickstarts-and-tutorials"></a>Pelajari Azure PowerShell dasar-dasar dengan mulai cepat dan tutorial

Untuk mulai menggunakan Azure PowerShell, cobalah tutorial mendalam untuk menyetel mesin virtual dan mempelajari cara membuat kuerinya.

> [!div class="nextstepaction"]
> [Membuat mesin virtual dengan Azure PowerShell](azureps-vm-tutorial.yml)

Tersedia juga cara Azure PowerShell cepat untuk layanan Azure populer lainnya:

* [Membuat akun penyimpanan](/azure/storage/common/storage-quickstart-create-account?tabs=azure-powershell)
* [Mentransfer objek ke/dari penyimpanan Blob Azure](/azure/storage/blobs/storage-quickstart-blobs-powershell)
* [Membuat dan mengambil rahasia dari Key Vault Azure](/azure/key-vault/quick-create-powershell)
* [Membuat database dan firewall Azure SQL](/azure/sql-database/scripts/sql-database-create-and-configure-database-powershell)
* [Menjalankan wadah dalam Azure Container Instances](/azure/container-instances/container-instances-quickstart-powershell)
* [Membuat Kumpulan Skala Mesin Virtual](/azure/virtual-machine-scale-sets/quick-create-powershell)
* [Membuat penyeimbang muat standar](/azure/load-balancer/quickstart-create-standard-load-balancer-powershell)

## <a name="next-steps"></a>Langkah berikutnya

* [Masuk dengan Azure PowerShell](authenticate-azureps.md)
* [Kelola langganan Azure dengan Azure PowerShell](manage-subscriptions-azureps.md)
* [Membuat prinsipal layanan dengan Azure PowerShell](create-azure-service-principal-azureps.md)
* Dapatkan bantuan dari komunitas:
  * [Forum Azure di MSDN](https://go.microsoft.com/fwlink/p/?LinkId=320212)
  * [Stack Overflow](https://go.microsoft.com/fwlink/?LinkId=320213)
