---
description: Artikel ini adalah pengantar untuk Azure PowerShell dan fitur-fiturnya.
ms.custom: devx-track-azurepowershell
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Apa itu Azure PowerShell
ms.openlocfilehash: b0236e2ab905fbaa4195a0eea9c68ff41b368ff6
ms.sourcegitcommit: cdca0d3199eb118c98aafb63ffcacc3dd080f0d4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "138855027"
---
# <a name="what-is-azure-powershell"></a>Apa itu Azure PowerShell?

Azure PowerShell adalah satu set cmdlet untuk mengelola sumber daya Azure langsung dari PowerShell. Azure PowerShell dirancang untuk memudahkan belajar dan memulai, tetapi menyediakan fitur canggih untuk otomatisasi.

## <a name="the-az-powershell-module"></a>Modul Az PowerShell

> [!IMPORTANT]
> Modul Az PowerShell adalah modul PowerShell yang direkomendasikan untuk mengelola sumber daya Azure di semua platform.

Modul Az PowerShell didasarkan pada pustaka .NET Standard dan berfungsi dengan PowerShell 7.0.6 LTS dan PowerShell 7.1.3 atau yang lebih baru di semua platform termasuk Windows, macOS, dan Linux. Kompatibel juga dengan Windows PowerShell 5.1.

> [!NOTE]
> PowerShell 7.0.6 LTS dan PowerShell 7.1.3 atau versi yang lebih tinggi adalah versi PowerShell yang direkomendasikan untuk digunakan dengan modul Az PowerShell di semua platform.

Anda dapat menginstal modul Az PowerShell secara lokal di Windows, macOS, dan Linux. Ini juga dapat digunakan dari browser melalui [Azure Cloud Shell](/azure/cloud-shell/overview) atau [dalam kontainer Docker](/powershell/azure/azureps-in-docker). Untuk informasi selengkapnya, lihat [Dokumentasi Azure PowerShell](/powershell/azure/).

### <a name="authentication"></a>Autentikasi

Azure PowerShell mendukung beberapa metode autentikasi. Untuk informasi terperinci tentang autentikasi ke Azure dari modul Az PowerShell, lihat [Masuk dengan Azure PowerShell](/powershell/azure/authenticate-azureps).

### <a name="module-design"></a>Desain Modul

Modul Az PowerShell adalah modul pembungkus untuk modul PowerShell terkait layanan Azure, biasanya satu modul per layanan Azure seperti `Az.Network` untuk layanan jaringan Azure dan `Az.AKS` untuk Azure Kubernetes Service.

Cmdlet dalam modul Az PowerShell melakukan panggilan REST ke API Azure. Perubahan yang melanggar dalam modul Az PowerShell dibatasi hingga dua kali setahun. Banyak perubahan yang melanggar pada tingkat API ditangani dalam cmdlet untuk mencegah persepsi perubahan yang melanggar.

Modul Az PowerShell berisi cmdlet untuk melakukan operasi sarana kontrol dan data plane di Azure. Anda menggunakan sarana kontrol untuk mengelola sumber daya di langganan Anda. Anda menggunakan sarana data untuk menggunakan kemampuan yang diekspos oleh instans And dari tipe sumber daya. Untuk informasi selengkapnya, lihat [sarana kontrol dan sarana data Azure](/azure/azure-resource-manager/management/control-plane-and-data-plane).

### <a name="output-objects"></a>Objek Output

Cmdlet dalam modul Az PowerShell menghasilkan objek .NET. Seperti perintah PowerShell yang menghasilkan output, cmdlet dalam modul Az PowerShell dapat disalurkan ke cmdlet [Get-Member](/powershell/module/microsoft.powershell.utility/get-member) untuk menentukan jenis objek apa yang dihasilkan bersama dengan daftar properti dan metode yang tersedia. Untuk informasi selengkapnya, lihat [Output kueri output Azure PowerShell](/powershell/azure/queries-azureps) dan [Format output cmdlet Azure PowerShell](/powershell/azure/formatting-output).

## <a name="other-modules"></a>Modul lain

Modul AzureAD dan MSOnline PowerShell bukan bagian dari modul Az PowerShell. Untuk informasi selengkapnya tentang modul tersebut, lihat dokumentasi untuk [PowerShell Azure Active Directory untuk Graph](/powershell/azure/active-directory/overview).

## <a name="legacy-azure-powershell-modules"></a>Modul Azure PowerShell lama

### <a name="the-azurerm-powershell-module"></a>Modul AzureRM PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Modul AzureRM PowerShell tidak lagi direkomendasikan karena penghentian telah diumumkan, fitur baru tidak lagi ditambahkan, dan tidak lintas platform. Untuk informasi selengkapnya, lihat [Ringkasan modul AzureRM PowerShell](/powershell/azure/azurerm/overview).

### <a name="the-azure-powershell-module"></a>Modul Azure PowerShell

> [!IMPORTANT]
> Cmdlet dalam modul Azure PowerShell adalah untuk mengelola sumber daya Azure lama yang menggunakan API Service Management.

Beberapa cmdlet dalam modul Azure PowerShell sudah tidak digunakan lagi dan yang lainnya tidak digunakan lagi untuk pelanggan baru dengan penghentian yang diumumkan untuk pelanggan yang sudah ada seperti yang tercantum pada halaman dokumentasi referensi yang sesuai. Untuk informasi selengkapnya, lihat [Ringkasan modul Azure PowerShell Service Management](/powershell/azure/servicemanagement/overview)
