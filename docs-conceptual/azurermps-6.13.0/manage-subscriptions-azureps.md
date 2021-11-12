---
title: Kelola langganan Azure dengan Azure PowerShell
description: Kelola langganan Azure dengan Azure PowerShell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 75f114ed4b58df4061db3b9478a4f7736a333eb3
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429357"
---
# <a name="manage-multiple-azure-subscriptions"></a>Mengelola beberapa langganan Azure

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Jika baru menggunakan Azure, Anda mungkin hanya memiliki satu langganan. Namun, jika telah menggunakan Azure untuk beberapa lama, Anda mungkin telah membuat beberapa langganan Azure. Anda dapat Azure PowerShell untuk menjalankan perintah terhadap langganan tertentu.

1. Dapatkan daftar semua langganan dalam akun Anda.

   ```azurepowershell
   Get-AzureRmSubscription
   ```

   ```Output
   Environment           : AzureCloud
   Account               : username@contoso.com
   TenantId              : 00000000-0000-0000-0000-000000000000
   SubscriptionId        : 00000000-0000-0000-0000-000000000000
   SubscriptionName      : My Production Subscription
   CurrentStorageAccount :

   Environment           : AzureCloud
   Account               : username@contoso.com
   TenantId              : 00000000-0000-0000-0000-000000000000
   SubscriptionId        : 00000000-0000-0000-0000-000000000000
   SubscriptionName      : My DevTest Subscription
   CurrentStorageAccount :

   Environment           : AzureCloud
   Account               : username@contoso.com
   TenantId              : 00000000-0000-0000-0000-000000000000
   SubscriptionId        : 00000000-0000-0000-0000-000000000000
   SubscriptionName      : My Demos
   CurrentStorageAccount :
   ```

2. Atur default.

   ```azurepowershell
   Select-AzureRmSubscription -Subscription 'My Demos'
   ```

3. Verifikasi perubahan dengan menjalankan `Get-AzureRmContext` cmdlet.

   ```azurepowershell
   Get-AzureRmContext
   ```

   ```Output
   Environment           : AzureCloud
   Account               : username@contoso.com
   TenantId              : 00000000-0000-0000-0000-000000000000
   SubscriptionId        : 00000000-0000-0000-0000-000000000000
   SubscriptionName      : My Demos
   CurrentStorageAccount :
   ```

Setelah Anda menetapkan langganan default, semua Azure PowerShell perintah dijalankan terhadap langganan ini.
