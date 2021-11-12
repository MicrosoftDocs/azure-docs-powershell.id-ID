---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: 37bbd8c92377158bbd124cd20d9eb09d75848c9e2a828aeead4b5294e7ba9427
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417641"
---
# Get-AzureRmContext

## SYNOPSIS
Dapatkan metadata yang digunakan untuk mengautentikasi permintaan Azure Resource Manager.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRmContext [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzureRmContext mendapatkan metadata saat ini yang digunakan untuk mengautentikasi permintaan Azure Resource Manager.

Cmdlet ini mendapatkan akun Direktori Aktif, penyewa Direktori Aktif, langganan Azure, dan lingkungan Azure yang ditargetkan.
Cmdlet Azure Resource Manager menggunakan pengaturan ini secara default saat membuat permintaan Azure Resource Manager.

## EXAMPLES

### Contoh 1: Mendapatkan konteks saat ini
```
PS C:\> Add-AzureRmAccount
PS C:\> Get-AzureRmContext

Environment           : AzureCloud
Account               : test@outlook.com
TenantId              : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SubscriptionId        : yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy
SubscriptionName      : Test Subscription
CurrentStorageAccount :
```

Dalam contoh ini, kami masuk ke akun dengan langganan Azure menggunakan Add-AzureRmAccount, lalu mendapatkan konteks sesi saat ini dengan menghubungi Get-AzureRmContext.

## PARAMETERS

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### PSAzureContext
Cmdlet ini mengembalikan akun, penyewa, dan langganan yang digunakan oleh cmdlet Azure Resource Manager.

## CATATAN

## RELATED LINKS

[Set-AzureRMContext]()

