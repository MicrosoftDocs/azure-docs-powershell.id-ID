---
title: Kelola langganan Azure dengan Azure PowerShell
description: Kelola langganan Azure dengan Azure PowerShell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/02/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 54d42785bcedd1a29453996b5ec042a93ceb1263
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "134026042"
---
# <a name="use-multiple-azure-subscriptions"></a>Menggunakan beberapa langganan Azure

Sebagian besar pengguna Azure hanya akan memiliki satu langganan. Namun, jika Anda merupakan bagian dari lebih dari satu organisasi atau organisasi telah membagi akses ke sumber daya tertentu di seluruh grup, Anda mungkin memiliki beberapa langganan dalam Azure. CLI mendukung pemilihan langganan secara global dan per perintah.

Untuk informasi lebih lanjut tentang manajemen langganan, tagihan, dan biaya, lihat [dokumentasi manajemen tagihan dan biaya.](/azure/billing/)

## <a name="tenants-users-and-subscriptions"></a>Penyewa, pengguna, dan langganan

Anda mungkin bingung atas perbedaan antara penyewa, pengguna, dan langganan dalam Azure. _Penyewa_ adalah Azure Active Directory entitas yang mencakup seluruh organisasi. Penyewa ini memiliki setidaknya _satu langganan_ dan _pengguna._ Pengguna adalah individu dan dikaitkan hanya dengan satu penyewa, organisasi di mana mereka menjadi anggotanya. Pengguna adalah akun yang masuk ke Azure untuk membuat, mengelola, dan menggunakan sumber daya. Pengguna mungkin memiliki akses ke _beberapa langganan,_ yang merupakan perjanjian dengan Microsoft untuk menggunakan layanan cloud, termasuk Azure. Setiap sumber daya dikaitkan dengan langganan.

Untuk mempelajari selengkapnya tentang perbedaan antara penyewa, pengguna, dan langganan, lihat kamus [terminologi awan Azure.](/azure/azure-glossary-cloud-terminology) Untuk mempelajari cara menambahkan langganan baru ke penyewa Azure Active Directory, lihat Mengaitkan atau menambahkan langganan Azure ke [penyewa Azure Active Directory Anda.](/azure/active-directory/active-directory-how-subscriptions-associated-directory)
Untuk mempelajari cara masuk ke penyewa tertentu, lihat [Masuk dengan akun Azure PowerShell](/powershell/azure/authenticate-azureps).

## <a name="change-the-active-subscription"></a>Mengubah langganan aktif

Dalam Azure PowerShell, mengakses sumber daya untuk langganan memerlukan pengubahan langganan yang terkait dengan sesi Azure Anda saat ini. Ini dilakukan dengan memodifikasi konteks sesi aktif, informasi tentang penyewa, langganan, dan cmdlet pengguna mana yang harus dijalankan. Untuk mengubah langganan, objek Konteks Azure PowerShell harus diambil dengan [Get-AzSubscription](/powershell/module/az.accounts/get-azsubscription) terlebih dahulu, lalu konteks saat ini berubah dengan [Set-AzContext](/powershell/module/az.accounts/set-azcontext).

Contoh berikutnya memperlihatkan cara mendapatkan langganan di penyewa yang saat ini aktif, dan mengaturnya sebagai sesi aktif:

```powershell-interactive
$context = Get-AzSubscription -SubscriptionId ...
Set-AzContext $context
```

Untuk mempelajari selengkapnya tentang Azure PowerShell konteks, termasuk cara menyimpannya dan beralih antar konteks dengan cepat untuk bekerja dengan beberapa langganan dengan mudah, lihat Menyimpan kredensial [dengan Azure PowerShell konteks](context-persistence.md).
