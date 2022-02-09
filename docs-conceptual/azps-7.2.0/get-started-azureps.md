---
title: Mulai menggunakan Azure PowerShell
description: Mulai menggunakan Azure PowerShell
ms.devlang: powershell
ms.topic: get-started-article
ms.date: 01/04/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: f6ada12faa1e82492824710103361792f8651fb8
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138335065"
---
# <a name="get-started-with-azure-powershell"></a>Mulai menggunakan Azure PowerShell

Azure PowerShell dirancang untuk mengelola dan mengelola sumber daya Azure dari baris perintah.
Gunakan Azure PowerShell saat Anda ingin membuat alat otomatis yang menggunakan model Azure Resource Manager. Cobalah di browser Anda dengan [Azure Cloud Shell](/azure/cloud-shell/overview), atau instal di mesin lokal Anda.

Artikel ini membantu Anda memulai dengan Azure PowerShell dan mengajarkan konsep inti di baliknya.

## <a name="install-or-run-in-azure-cloud-shell"></a>Menginstal atau menjalankan di Azure Cloud Shell

Cara termudah untuk memulai Azure PowerShell adalah dengan mencobanya di lingkungan Azure Cloud Shell. Untuk bangun dan berjalan dengan Cloud Shell, lihat [Mulai Cepat untuk PowerShell di Azure Cloud Shell](/azure/cloud-shell/quickstart-powershell). Cloud Shell menjalankan PowerShell pada kontainer Linux, sehingga fungsionalitas khusus Windows tidak tersedia.

Saat Anda siap menginstal Azure PowerShell di mesin lokal Anda, ikuti petunjuk di [Instal modul Azure PowerShell](install-az-ps.md).

## <a name="sign-in-to-azure"></a>Masuk ke Azure

Masuk secara interaktif dengan cmdlet [Koneksi-AzAccount](/powershell/module/az.accounts/connect-azaccount). Lewati langkah ini jika Anda menggunakan Cloud Shell. Sesi Azure Cloud Shell Anda sudah diautentikasi untuk lingkungan, langganan, dan penyewa yang meluncurkan sesi Cloud Shell.

```azurepowershell-interactive
Connect-AzAccount
```

Layanan cloud Azure menawarkan lingkungan yang sesuai dengan undang-undang penanganan data regional. Untuk akun di cloud regional, gunakan `Environment` parameter untuk masuk. Dapatkan nama lingkungan untuk wilayah Anda menggunakan cmdlet [Get-AzEnvironment](/powershell/module/Az.Accounts/Get-AzEnvironment) .
Misalnya, untuk masuk ke Azure China 21Vianet:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

Dimulai dengan modul Az PowerShell versi 5.0.0, `Connect-AzAccount` menyajikan prompt login berbasis browser interaktif secara default. Anda dapat menentukan `UseDeviceAuthentication` parameter untuk menerima string token yang sebelumnya default untuk PowerShell versi 6 dan yang lebih tinggi.

Setelah masuk, Anda akan melihat informasi yang menunjukkan langganan Azure mana yang aktif. Jika Anda memiliki beberapa langganan Azure di akun Anda dan ingin memilih langganan yang berbeda, dapatkan langganan yang tersedia dengan [Get-AzSubscription](/powershell/module/az.accounts/get-azsubscription) dan gunakan cmdlet [Set-AzContext](/powershell/module/az.accounts/set-azcontext) dengan ID langganan Anda. Untuk informasi selengkapnya tentang mengelola langganan Azure Anda di Azure PowerShell, lihat [Menggunakan beberapa langganan Azure](manage-subscriptions-azureps.md).

Setelah masuk, gunakan cmdlet Azure PowerShell untuk mengakses dan mengelola sumber daya dalam langganan Anda. Untuk mempelajari selengkapnya tentang proses masuk dan metode autentikasi, lihat [Masuk dengan Azure PowerShell](authenticate-azureps.md).

## <a name="find-commands"></a>Menemukan perintah

Azure PowerShell cmdlet mengikuti konvensi penamaan standar untuk PowerShell, `Verb-Noun`. Kata kerja menjelaskan tindakan (contoh termasuk `New`, , `Get``Set`, `Remove`) dan kata benda menggambarkan jenis sumber daya (contoh termasuk `AzVM`, `AzKeyVaultCertificate`, `AzFirewall`, `AzVirtualNetworkGateway`). Kata benda dalam Azure PowerShell selalu dimulai dengan awalan `Az`. Untuk daftar lengkap kata kerja standar, lihat [Kata kerja yang disetujui untuk Perintah PowerShell](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands).

Mengetahui kata benda, kata kerja, dan modul Azure PowerShell yang tersedia membantu Anda menemukan perintah dengan cmdlet [Get-Command](/powershell/module/microsoft.powershell.core/get-command). Misalnya, untuk menemukan semua perintah terkait VM yang menggunakan `Get` kata kerja:

```powershell-interactive
Get-Command -Verb Get -Noun AzVM* -Module Az.Compute
```

Untuk membantu Anda menemukan perintah umum, tabel ini mencantumkan jenis sumber daya, modul Azure PowerShell yang sesuai, dan awalan kata benda untuk digunakan dengan`Get-Command`:

|                              Jenis Sumber Daya                              |                   Modul Azure PowerShell                    |    Awalan kata benda     |
| ----------------------------------------------------------------------- | ------------------------------------------------------------ | ------------------ |
| [Grup sumber daya](/azure/azure-resource-manager/resource-group-overview) | [Az.Resources](/powershell/module/az.resources#resources)    | `AzResourceGroup`  |
| [Komputer virtual](/azure/virtual-machines)                             | [Az.Compute](/powershell/module/az.compute#virtual_machines) | `AzVM`             |
| [Akun penyimpanan](/azure/storage/common/storage-introduction)          | [Az.Storage](/powershell/module/az.storage/)                 | `AzStorageAccount` |
| [Key Vault](/azure/key-vault/key-vault-whatis)                          | [Az.KeyVault](/powershell/module/az.keyvault)                | `AzKeyVault`       |
| [Aplikasi web](/azure/app-service)                                  | [Az.Websites](/powershell/module/az.websites)                | `AzWebApp`         |
| [Database SQL](/azure/sql-database)                                    | [Az.Sql](/powershell/module/az.sql)                          | `AzSqlDatabase`    |

Untuk daftar lengkap modul di Azure PowerShell, lihat [daftar modul Azure PowerShell](https://github.com/Azure/azure-powershell/blob/master/documentation/azure-powershell-modules.md) yang dihosting di GitHub.

## <a name="telemetry"></a>Telemetri

Azure PowerShell secara otomatis mengumpulkan data telemetri secara default. Microsoft mengumpulkan data yang dikumpulkan untuk mengidentifikasi pola penggunaan, untuk mengidentifikasi masalah umum, dan untuk meningkatkan pengalaman Azure PowerShell. Microsoft Azure PowerShell tidak mengumpulkan data pribadi atau pribadi. Untuk menonaktifkan pengumpulan data, Anda harus secara eksplisit memilih keluar dengan menjalankan [Disable-AzDataCollection](/powershell/module/az.accounts/disable-azdatacollection).

## <a name="learn-azure-powershell-basics-with-quickstarts-and-tutorials"></a>Pelajari dasar-dasar Azure PowerShell dengan mulai cepat dan tutorial

Untuk memulai dengan Azure PowerShell, coba tutorial mendalam untuk menyiapkan mesin virtual dan pelajari cara memintanya.

> [!div class="nextstepaction"]
> [Buat mesin virtual dengan Azure PowerShell](azureps-vm-tutorial.yml)

Ada juga Azure PowerShell mulai cepat untuk layanan Azure populer lainnya:

* [Buat akun penyimpanan](/azure/storage/common/storage-quickstart-create-account?tabs=azure-powershell)
* [Mentransfer objek ke/dari penyimpanan Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-powershell)
* [Membuat dan mengambil rahasia dari Azure Key Vault](/azure/key-vault/quick-create-powershell)
* [Membuat database dan firewall Azure SQL](/azure/sql-database/scripts/sql-database-create-and-configure-database-powershell)
* [Menjalankan kontainer di Azure Container Instances](/azure/container-instances/container-instances-quickstart-powershell)
* [Membuat Set Timbangan Mesin Virtual](/azure/virtual-machine-scale-sets/quick-create-powershell)
* [Membuat penyeimbang muatan standar](/azure/load-balancer/quickstart-create-standard-load-balancer-powershell)

## <a name="next-steps"></a>Langkah berikutnya

* [Masuk dengan Azure PowerShell](authenticate-azureps.md)
* [Mengelola langganan Azure dengan Azure PowerShell](manage-subscriptions-azureps.md)
* [Buat prinsipal layanan dengan Azure PowerShell](create-azure-service-principal-azureps.md)
* Dapatkan bantuan dari komunitas:
  * [Azure forum on MSDN](https://go.microsoft.com/fwlink/p/?LinkId=320212)
  * [Stack Overflow](https://go.microsoft.com/fwlink/?LinkId=320213)
