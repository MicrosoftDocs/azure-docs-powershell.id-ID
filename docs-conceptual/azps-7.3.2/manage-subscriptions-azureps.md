---
description: Mengelola langganan Azure dengan Azure PowerShell
ms.custom: devx-track-azurepowershell
ms.date: 03/12/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Mengelola langganan Azure dengan Azure PowerShell
ms.openlocfilehash: 5bf3b32da23772986947361cf4347becd5600215
ms.sourcegitcommit: b346b2fbd8b25f54759984e75ddbee3304921c43
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/16/2022
ms.locfileid: "140664453"
---
# <a name="use-multiple-azure-subscriptions"></a>Menggunakan beberapa langganan Azure

Sebagian besar pengguna Azure hanya akan memiliki satu langganan. Namun, jika Anda adalah bagian dari lebih dari satu organisasi atau organisasi Anda telah membagi akses ke sumber daya tertentu di seluruh pengelompokan, Anda dapat memiliki beberapa langganan dalam Azure. CLI mendukung pemilihan langganan baik secara global maupun per perintah.

Untuk informasi mendetail tentang langganan, penagihan, dan manajemen biaya, lihat [dokumentasi manajemen biaya dan penagihan](/azure/billing/).

## <a name="tenants-users-and-subscriptions"></a>Penyewa, pengguna, dan langganan

Anda mungkin memiliki beberapa pertanyaan tentang perbedaan antara penyewa, pengguna, dan langganan dalam Azure. _Penyewa_ adalah entitas Azure Active Directory yang mencakup seluruh organisasi. Penyewa ini memiliki setidaknya satu _langganan_ dan _pengguna_. Pengguna adalah individu dan dikaitkan dengan hanya satu penyewa, organisasi tempat mereka berada. Pengguna adalah akun yang masuk ke Azure untuk membuat, mengelola, dan menggunakan sumber daya. Pengguna mungkin memiliki akses ke beberapa _langganan_, yang merupakan perjanjian dengan Microsoft untuk menggunakan layanan awan, termasuk Azure. Setiap sumber daya dikaitkan dengan langganan.

Untuk mempelajari selengkapnya tentang perbedaan antara penyewa, pengguna, dan langganan, lihat [Kamus terminologi cloud Azure](/azure/azure-glossary-cloud-terminology). Untuk mempelajari cara menambahkan langganan baru ke penyewa Azure Active Directory Anda, lihat [Mengaitkan atau menambahkan langganan Azure ke penyewa Azure Active Directory Anda](/azure/active-directory/active-directory-how-subscriptions-associated-directory).
Untuk mempelajari cara masuk ke penyewa tertentu, lihat [Masuk dengan Azure PowerShell](/powershell/azure/authenticate-azureps).

## <a name="change-the-active-subscription"></a>Mengubah langganan aktif

Di Azure PowerShell, mengakses sumber daya untuk langganan memerlukan perubahan langganan yang berkaitan dengan sesi Azure Anda saat ini. Hal ini dilakukan dengan memodifikasi konteks sesi aktif, informasi tentang cmdlet penyewa, langganan, dan pengguna mana yang harus dijalankan. Untuk mengubah langganan, objek Konteks Azure PowerShell harus diambil dengan [Get-AzSubscription](/powershell/module/az.accounts/get-azsubscription) dan kemudian konteks saat ini diubah dengan [Set-AzContext](/powershell/module/az.accounts/set-azcontext).

Contoh berikutnya menunjukkan cara mendapatkan langganan di penyewa aktif saat ini, dan mengaturnya sebagai sesi aktif:

```powershell-interactive
$context = Get-AzSubscription -SubscriptionId ...
Set-AzContext $context
```

Untuk mempelajari tentang konteks Azure PowerShell, termasuk cara menyimpannya dan beralih dengan cepat di antaranya untuk bekerja dengan beberapa langganan dengan mudah, lihat [Mempertahankan informasi masuk dengan konteks Azure PowerShell](context-persistence.md).
