---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: 47523664195913a7a3d24a21a9804b035b88acf5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142354058"
---
# Get-AzureRmContext

## SYNOPSIS
Mendapatkan metadata yang digunakan untuk mengautentikasi permintaan Resource Manager Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRmContext [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzureRmContext mendapatkan metadata saat ini yang digunakan untuk mengautentikasi permintaan Resource Manager Azure.

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

Dalam contoh ini, kami masuk ke akun kami dengan langganan Azure menggunakan Add-AzureRmAccount, lalu kami mendapatkan konteks sesi saat ini dengan menghubungi Get-AzureRmContext.

## PARAMETERS

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSAzureContext
Cmdlet ini mengembalikan cmdlet akun, penyewa, dan langganan yang digunakan oleh Cmdlet Azure Resource Manager.

## CATATAN

## RELATED LINKS

[Set-AzureRMContext]()

