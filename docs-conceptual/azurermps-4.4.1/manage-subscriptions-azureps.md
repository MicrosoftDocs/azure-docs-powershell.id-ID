---
title: Kelola langganan Azure dengan Azure PowerShell | Microsoft Docs
description: Kelola langganan Azure dengan Azure PowerShell
keywords: Azure PowerShell, langganan
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/30/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: d2674e37a211d1c1896a13e234cda95beea4479a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423164"
---
# <a name="manage-multiple-azure-subscriptions"></a>Mengelola beberapa langganan Azure

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Jika baru menggunakan Azure, Anda mungkin hanya memiliki satu langganan. Namun, jika telah menggunakan Azure untuk beberapa lama, Anda mungkin telah membuat beberapa langganan Azure. Anda dapat Azure PowerShell untuk menjalankan perintah terhadap langganan tertentu.

1. Dapatkan daftar semua langganan dalam akun Anda.

    ```powershell-interactive
    Get-AzureRmSubscription
    ```

    ```output
    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Production Subscription
    CurrentStorageAccount :

    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My DevTest Subscription
    CurrentStorageAccount :

    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Demos
    CurrentStorageAccount :
    ```

2. Atur default.

    ```powershell-interactive
    Select-AzureRmSubscription -SubscriptionName "My Demos"
    ```

3. Verifikasi perubahan dengan menjalankan `Get-AzureRmContext` cmdlet.

    ```powershell-interactive
    Get-AzureRmContext
    ```

    ```output
    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Demos
    CurrentStorageAccount :
    ```

Setelah Anda mengatur langganan default, semua perintah Azure PowerShell dijalankan terhadap langganan ini.
