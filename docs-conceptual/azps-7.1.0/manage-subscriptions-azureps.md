---
title: Kelola langganan Azure dengan Azure PowerShell
description: Kelola langganan Azure dengan Azure PowerShell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/04/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 8add22176ec12ac9d3672f8bd34358232e7c7bf3
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "135958462"
---
# <a name="use-multiple-azure-subscriptions"></a>Menggunakan beberapa langganan Azure

Sebagian besar pengguna Azure hanya akan memiliki satu langganan. Namun, jika Anda merupakan bagian dari lebih dari satu organisasi atau organisasi telah membagi akses ke sumber daya tertentu di seluruh grup, Anda mungkin memiliki beberapa langganan dalam Azure. CLI mendukung pemilihan langganan secara global dan per perintah.

Untuk informasi lebih lanjut tentang manajemen langganan, tagihan, dan biaya, lihat [dokumentasi manajemen tagihan dan biaya.](/azure/billing/)

## <a name="tenants-users-and-subscriptions"></a>Penyewa, pengguna, dan langganan

Anda mungkin bingung atas perbedaan antara penyewa, pengguna, dan langganan dalam Azure. Penyewa  adalah Azure Active Directory entitas yang mencakup seluruh organisasi. Penyewa ini memiliki setidaknya _satu langganan_ dan _pengguna._ Pengguna adalah individu dan dikaitkan hanya dengan satu penyewa, organisasi di mana mereka menjadi anggotanya. Pengguna adalah akun yang masuk ke Azure untuk membuat, mengelola, dan menggunakan sumber daya. Pengguna mungkin memiliki akses ke _beberapa langganan,_ yang merupakan perjanjian dengan Microsoft untuk menggunakan layanan cloud, termasuk Azure. Setiap sumber daya dikaitkan dengan langganan.

Untuk mempelajari selengkapnya tentang perbedaan antara penyewa, pengguna, dan langganan, lihat kamus [terminologi awan Azure.](/azure/azure-glossary-cloud-terminology) Untuk mempelajari cara menambahkan langganan baru ke penyewa Azure Active Directory, lihat Mengaitkan atau menambahkan langganan Azure ke [Azure Active Directory penyewa Anda.](/azure/active-directory/active-directory-how-subscriptions-associated-directory)
Untuk mempelajari cara masuk ke penyewa tertentu, lihat [Masuk dengan Azure PowerShell](/powershell/azure/authenticate-azureps).

## <a name="change-the-active-subscription"></a>Mengubah langganan aktif

Dalam Azure PowerShell, mengakses sumber daya untuk langganan memerlukan pengubahan langganan yang terkait dengan sesi Azure Anda saat ini. Ini dilakukan dengan memodifikasi konteks sesi aktif, informasi tentang penyewa, langganan, dan cmdlet pengguna mana yang harus dijalankan. Untuk mengubah langganan, objek Konteks Azure PowerShell harus diambil dengan [Get-AzSubscription](/powershell/module/az.accounts/get-azsubscription) terlebih dahulu, lalu konteks saat ini berubah dengan [Set-AzContext](/powershell/module/az.accounts/set-azcontext).

Contoh berikutnya memperlihatkan cara mendapatkan langganan di penyewa yang saat ini aktif, dan mengaturnya sebagai sesi aktif:

```powershell-interactive
$context = Get-AzSubscription -SubscriptionId ...
Set-AzContext $context
```

Untuk mempelajari selengkapnya Azure PowerShell konteks, termasuk cara menyimpannya dan beralih antar konteks dengan cepat untuk bekerja dengan beberapa langganan dengan mudah, lihat Menyimpan kredensial [dengan Azure PowerShell konteks](context-persistence.md).
