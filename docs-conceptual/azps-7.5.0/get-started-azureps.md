---
description: Mulai menggunakan Azure PowerShell
ms.custom: devx-track-azurepowershell
ms.date: 04/05/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: get-started-article
title: Mulai menggunakan Azure PowerShell
ms.openlocfilehash: 8b93200ef32b9e70a4fd52ce1dc0f00b8be1fd29
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144294283"
---
# <a name="get-started-with-azure-powershell"></a>Mulai menggunakan Azure PowerShell

Azure PowerShell dirancang untuk mengelola dan menata sumber daya Azure dari baris perintah.
Gunakan Azure PowerShell saat Anda ingin membuat alat otomatis yang menggunakan model Azure Resource Manager. Cobalah di browser Anda dengan [Azure Cloud Shell](/azure/cloud-shell/overview), atau instal di komputer lokal Anda.

Artikel ini membantu Anda memulai Azure PowerShell dan mengajarkan konsep inti di baliknya.

## <a name="install-or-run-in-azure-cloud-shell"></a>Menginstal atau menjalankan di Azure Cloud Shell

Cara termudah untuk memulai Azure PowerShell adalah dengan mencobanya di lingkungan Azure Cloud Shell. Untuk mulai menggunakan Cloud Shell, lihat [Mulai Cepat untuk PowerShell di Azure Cloud Shell](/azure/cloud-shell/quickstart-powershell). Cloud Shell menjalankan PowerShell pada kontainer Linux sehingga fungsi khusus Windows tidak tersedia.

Begitu Anda siap menginstal Azure PowerShell di komputer lokal, ikuti petunjuk dalam [Menginstal modul Azure PowerShell](install-az-ps.md).

## <a name="sign-in-to-azure"></a>Masuk ke Azure

Masuk secara interaktif dengan cmdlet [Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount). Lewati langkah ini jika Anda menggunakan Cloud Shell. Sesi Azure Cloud Shell Anda sudah diautentikasi untuk lingkungan, langganan, dan penyewa yang meluncurkan sesi Cloud Shell.

```azurepowershell-interactive
Connect-AzAccount
```

Layanan cloud Azure menawarkan lingkungan yang sesuai dengan undang-undang penanganan data regional. Untuk akun di cloud wilayah, gunakan parameter `Environment` untuk masuk. Cari tahu nama lingkungan untuk wilayan Anda menggunakan cmdlet [Get-AzEnvironment](/powershell/module/Az.Accounts/Get-AzEnvironment).
Misalnya, untuk masuk ke Azure Tiongkok:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

Sejak modul Az PowerShell versi 5.0.0, `Connect-AzAccount` menyajikan perintah masuk berbasis browser interaktif secara default. Anda dapat menentukan parameter `UseDeviceAuthentication` untuk menerima string token yang sebelumnya merupakan default untuk PowerShell versi 6 dan yang lebih tinggi.

Setelah masuk, Anda akan melihat informasi yang menunjukkan langganan Azure mana yang aktif. Jika Anda memiliki beberapa langganan Azure di akun Anda dan ingin memilih yang lain, dapatkan langganan yang tersedia dengan [Get-AzSubscription](/powershell/module/az.accounts/get-azsubscription) dan gunakan cmdlet [Set-AzContext](/powershell/module/az.accounts/set-azcontext) dengan ID langganan Anda. Untuk informasi selengkapnya tentang mengelola langganan Azure Anda di Azure PowerShell, lihat [Menggunakan beberapa langganan Azure](manage-subscriptions-azureps.md).

Setelah masuk, gunakan cmdlet Azure PowerShell untuk mengakses dan mengelola sumber daya dalam langganan Anda. Untuk mempelajari proses masuk dan metode autentikasi lebih lanjut, lihat [Masuk dengan Azure PowerShell](authenticate-azureps.md).

## <a name="find-commands"></a>Menemukan perintah

Cmdlet Azure PowerShell mengikuti konvensi penamaan standar untuk PowerShell, `Verb-Noun`. Kata kerja menggambarkan tindakan (contohnya meliputi `New`, `Get`, `Set`, `Remove`) dan kata benda menggambarkan jenis sumber daya (contohnya meliputi `AzVM`, `AzKeyVaultCertificate`, `AzFirewall`, `AzVirtualNetworkGateway`). Kata benda dalam Azure PowerShell selalu dimulai dengan awalan `Az`. Untuk daftar lengkap kata kerja standar, lihat [Kata kerja yang disetujui untuk Perintah PowerShell](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands).

Mengetahui kata benda, kata kerja, dan modul Azure PowerShell yang tersedia akan membantu Anda menemukan perintah dengan cmdlet [Get-Command](/powershell/module/microsoft.powershell.core/get-command). Misalnya, untuk menemukan semua perintah terkait VM yang menggunakan kata kerja `Get`:

```powershell-interactive
Get-Command -Verb Get -Noun AzVM* -Module Az.Compute
```

Untuk membantu Anda menemukan perintah umum, tabel ini mencantumkan jenis sumber daya, modul Azure PowerShell yang sesuai, dan awalan kata benda untuk digunakan dengan `Get-Command`:

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

Azure PowerShell secara otomatis mengumpulkan data telemetri secara default. Microsoft mengagregasi kumpulan data untuk mengidentifikasi pola penggunaan, mengidentifikasi masalah umum, dan meningkatkan pengalaman Azure PowerShell. Microsoft Azure PowerShell tidak mengumpulkan data pribadi atau personal apa pun. Untuk menonaktifkan pengumpulan data, Anda harus menolak secara eksplisit dengan menjalankan [Disable-AzDataCollection](/powershell/module/az.accounts/disable-azdatacollection).

## <a name="learn-azure-powershell-basics-with-quickstarts-and-tutorials"></a>Pelajari dasar-dasar Azure PowerShell dengan panduan mulai cepat dan tutorial

Untuk memulai Azure PowerShell, cobalah tutorial mendalam untuk menyiapkan komputer virtual dan mempelajari cara membuat kueri.

> [!div class="nextstepaction"]
> [Membuat komputer virtual dengan Azure PowerShell](azureps-vm-tutorial.yml)

Ada juga panduan mulai cepat Azure PowerShell untuk layanan Azure lain yang populer:

* [Buat akun penyimpanan](/azure/storage/common/storage-quickstart-create-account?tabs=azure-powershell)
* [Mentransfer objek ke/dari penyimpanan Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-powershell)
* [Membuat dan mengambil rahasia dari Azure Key Vault](/azure/key-vault/quick-create-powershell)
* [Membuat database dan firewall Azure SQL](/azure/sql-database/scripts/sql-database-create-and-configure-database-powershell)
* [Menjalankan kontainer dalam Azure Container Instances](/azure/container-instances/container-instances-quickstart-powershell)
* [Membuat Set Skala Komputer Virtual](/azure/virtual-machine-scale-sets/quick-create-powershell)
* [Membuat penyeimbang muatan standar](/azure/load-balancer/quickstart-create-standard-load-balancer-powershell)

## <a name="next-steps"></a>Langkah berikutnya

* [Masuk dengan Azure PowerShell](authenticate-azureps.md)
* [Mengelola langganan Azure dengan Azure PowerShell](manage-subscriptions-azureps.md)
* [Membuat prinsipal layanan dengan Azure PowerShell](create-azure-service-principal-azureps.md)
* Mendapatkan bantuan dari komunitas:
  * [Forum Azure di MSDN](https://go.microsoft.com/fwlink/p/?LinkId=320212)
  * [Stack Overflow](https://go.microsoft.com/fwlink/?LinkId=320213)
