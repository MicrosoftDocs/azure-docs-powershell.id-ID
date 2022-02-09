---
title: Apa yang Azure PowerShell
description: Artikel ini adalah pengantar Azure PowerShell dan fitur-fiturnya.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/04/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 534978ef6d1cbe330f8164b6ead72523a1a5f0d1
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138184343"
---
# <a name="what-is-azure-powershell"></a>Apa Azure PowerShell itu?

Azure PowerShell adalah satu set cmdlet untuk mengelola sumber daya Azure langsung dari PowerShell. Azure PowerShell dirancang untuk membuatnya mudah dipelajari dan memulai, tetapi menyediakan fitur canggih untuk otomatisasi.

## <a name="the-az-powershell-module"></a>Modul Az PowerShell

> [!IMPORTANT]
> Modul Az PowerShell adalah modul PowerShell yang direkomendasikan untuk mengelola sumber daya Azure di semua platform.

Modul Az PowerShell didasarkan pada .NET Standard, dan bekerja dengan PowerShell 7.0.6 LTS dan PowerShell 7.1.3 atau lebih tinggi pada semua platform termasuk Windows, macOS, dan Linux. Ini juga kompatibel dengan Windows PowerShell 5.1.

> [!NOTE]
> PowerShell 7.0.6 LTS dan PowerShell 7.1.3 atau lebih tinggi adalah versi PowerShell yang direkomendasikan untuk digunakan dengan modul Az PowerShell di semua platform.

Anda dapat menginstal modul Az PowerShell secara lokal di Windows, macOS, dan Linux. Ini juga dapat digunakan dari browser melalui [Azure Cloud Shell](/azure/cloud-shell/overview) atau [di dalam kontainer Docker](/powershell/azure/azureps-in-docker). Untuk informasi selengkapnya, lihat [dokumentasi Azure PowerShell](/powershell/azure/).

### <a name="authentication"></a>Autentikasi

Azure PowerShell mendukung beberapa metode otentikasi. Untuk informasi mendetail tentangautentikasi ke Azure dari modul Az PowerShell, lihat [Masuk dengan Azure PowerShell](/powershell/azure/authenticate-azureps).

### <a name="module-design"></a>Desain Modul

Modul Az PowerShell adalah modul pembungkus untuk modul PowerShell terkait layanan Azure, biasanya satu modul per layanan Azure seperti `Az.Network` untuk layanan jaringan Azure dan `Az.AKS` untuk Azure Kubernetes Service.

Cmdlet di modul Az PowerShell melakukan panggilan REST ke Azure API. Melanggar perubahan pada modul Az PowerShell dibatasi hingga dua kali setahun. Banyak perubahan yang melanggar di tingkat API ditangani dalam cmdlet untuk mencegah persepsi perubahan yang melanggar.

Modul Az PowerShell berisi cmdlet untuk melakukan operasi bidang kontrol dan bidang data di Azure. Anda menggunakan sarana kontrol untuk mengelola sumber daya di langganan Anda. Anda menggunakan sarana data untuk menggunakan kemampuan yang diekspos oleh instans And dari tipe sumber daya. Untuk informasi selengkapnya, lihat [sarana kontrol dan sarana data Azure](/azure/azure-resource-manager/management/control-plane-and-data-plane).

### <a name="output-objects"></a>Objek Output

Cmdlet dalam modul Az PowerShell menghasilkan objek .NET. Seperti halnya perintah PowerShell yang menghasilkan output, cmdlet dalam modul Az PowerShell dapat disalurkan ke cmdlet [Get-Member](/powershell/module/microsoft.powershell.utility/get-member) untuk menentukan jenis objek apa yang dihasilkan bersama dengan daftar properti dan metode yang tersedia. Untuk informasi [selengkapnya, lihat Output kueri Azure PowerShell](/powershell/azure/queries-azureps) dan [Format Azure PowerShell output cmdlet](/powershell/azure/formatting-output).

## <a name="other-modules"></a>Modul lain

Modul AzureAD dan MSOnline PowerShell bukan bagian dari modul Az PowerShell. Untuk informasi selengkapnya tentang modul tersebut, lihat dokumentasi untuk [Azure Active Directory PowerShell untuk Graph](/powershell/azure/active-directory/overview).

## <a name="legacy-azure-powershell-modules"></a>Modul Azure PowerShell lama

### <a name="the-azurerm-powershell-module"></a>Modul AzureRM PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Modul AzureRM PowerShell tidak lagi direkomendasikan karena penghentian telah diumumkan, fitur baru tidak lagi ditambahkan, dan itu bukan lintas platform. Untuk informasi [selengkapnya, lihat Gambaran umum modul AzureRM PowerShell](/powershell/azure/azurerm/overview).

### <a name="the-azure-powershell-module"></a>Modul Azure PowerShell

> [!IMPORTANT]
> Cmdlet dalam modul Azure PowerShell adalah untuk mengelola sumber daya Azure lama yang menggunakan API Manajemen Layanan.

Beberapa cmdlet dalam modul Azure PowerShell telah usang dan yang lainnya telah usang untuk pelanggan baru dengan pensiun diumumkan untuk pelanggan yang sudah ada seperti yang tercantum pada halaman dokumentasi referensi yang sesuai. Untuk informasi [selengkapnya, lihat Gambaran umum modul Manajemen Layanan Azure PowerShell](/powershell/azure/servicemanagement/overview)
