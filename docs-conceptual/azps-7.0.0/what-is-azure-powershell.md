---
title: Apa yang Azure PowerShell
description: Artikel ini merupakan pengenalan tentang Azure PowerShell dan fiturnya.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/02/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: e7a4b7a3a889903f3c9e93e28fc74c356fc16c08
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "134026033"
---
# <a name="what-is-azure-powershell"></a>Apa itu Azure PowerShell?

Azure PowerShell adalah kumpulan cmdlet untuk mengelola sumber daya Azure langsung dari PowerShell. Azure PowerShell dirancang untuk memudahkan dalam mempelajari dan memulai, namun menyediakan fitur canggih untuk otomatisasi.

## <a name="the-az-powershell-module"></a>Modul Az PowerShell

> [!IMPORTANT]
> Modul Az PowerShell adalah modul PowerShell yang disarankan untuk mengelola sumber daya Azure di semua platform.

Modul Az PowerShell didasarkan pada .NET Standard, dan berfungsi dengan PowerShell 7.0.6 LTS dan PowerShell 7.1.3 atau yang lebih tinggi di semua platform termasuk Windows, macOS, dan Linux. Ini juga kompatibel dengan Windows PowerShell 5.1.

> [!NOTE]
> PowerShell 7.0.6 LTS dan PowerShell 7.1.3 atau yang lebih tinggi adalah versi PowerShell yang disarankan untuk digunakan dengan modul Az PowerShell di semua platform.

Anda dapat menginstal modul Az PowerShell secara lokal di Windows, macOS, dan Linux. Informasi ini juga dapat digunakan dari browser melalui [Azure Cloud Shell](/azure/cloud-shell/overview) atau di dalam wadah [Docker](/powershell/azure/azureps-in-docker). Untuk informasi selengkapnya, lihat [Azure PowerShell dokumen](/powershell/azure/).

### <a name="authentication"></a>Autentikasi

Azure PowerShell mendukung beberapa metode autentikasi. Untuk informasi lebih lanjut tentang mengotentikan ke Azure dari modul Az PowerShell, [lihat Masuk dengan Azure PowerShell](/powershell/azure/authenticate-azureps).

### <a name="module-design"></a>Desain Modul

Modul Az PowerShell adalah modul pembungkus untuk modul PowerShell terkait layanan Azure, biasanya satu modul per layanan Azure seperti untuk layanan jaringan Azure dan untuk `Az.Network` `Az.AKS` Layanan Azure K azure.

Cmdlet dalam modul Az PowerShell membuat panggilan REST ke API Azure. Memutus perubahan dalam modul Az PowerShell terbatas pada dua kali dalam setahun. Banyak perubahan yang tidak dapat diubah pada tingkat API ditangani dalam cmdlet untuk mencegah kerusakan perubahan.

Modul Az PowerShell berisi cmdlet untuk melakukan operasi pesawat kontrol dan pesawat data di Azure. Anda menggunakan bidang kontrol untuk mengelola sumber daya dalam langganan. Anda menggunakan bidang data untuk menggunakan kemampuan yang diekspos oleh instans tipe sumber daya Anda. Untuk informasi selengkapnya, lihat [Pesawat kontrol Azure dan pesawat data.](/azure/azure-resource-manager/management/control-plane-and-data-plane)

### <a name="output-objects"></a>Objek Output

Cmdlet di modul Az PowerShell menghasilkan objek .NET. Seperti perintah PowerShell apa pun yang menghasilkan output, cmdlet dalam modul Az PowerShell dapat dijimkan ke cmdlet [Get-Member](/powershell/module/microsoft.powershell.utility/get-member) untuk menentukan tipe objek yang dihasilkan bersama dengan daftar properti dan metode yang tersedia. Untuk informasi selengkapnya, lihat [Output kueri dari Azure PowerShell](/powershell/azure/queries-azureps) dan Format Azure PowerShell output [cmdlet](/powershell/azure/formatting-output).

## <a name="other-modules"></a>Modul lainnya

Modul PowerShell AzureAD dan MSOnline bukanlah bagian dari modul Az PowerShell. Untuk informasi selengkapnya tentang modul tersebut, lihat dokumentasi tentang [Azure Active Directory PowerShell untuk Graph](/powershell/azure/active-directory/overview).

## <a name="legacy-azure-powershell-modules"></a>Modul Azure PowerShell warisan

### <a name="the-azurerm-powershell-module"></a>Modul PowerShell AzureRM

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Modul PowerShell AzureRM tidak lagi disarankan karena penghentian telah diumumkan, fitur baru tidak lagi ditambahkan, dan bukan platform silang. Untuk informasi selengkapnya, [lihat Gambaran umum modul PowerShell AzureRM](/powershell/azure/azurerm/overview).

### <a name="the-azure-powershell-module"></a>Modul Azure PowerShell

> [!IMPORTANT]
> Cmdlet dalam modul Azure PowerShell digunakan untuk mengelola sumber daya Azure warisan yang menggunakan API Manajemen Layanan.

Beberapa cmdlet dalam modul Azure PowerShell sudah tidak berlaku dan lainnya sudah tidak berlaku bagi pelanggan baru dengan penghentian yang diumumkan untuk pelanggan yang sudah ada seperti yang disebutkan di halaman dokumentasi referensi terkait. Untuk informasi selengkapnya, [lihat Gambaran umum Azure PowerShell modul Manajemen Layanan](/powershell/azure/servicemanagement/overview)
