---
external help file: Azs.Network.Admin-help.xml
Module Name: Azs.Network.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 3f5fbef7c67676f16793b63a8448517ca24aa7e5
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136580972"
---
# Get-AzsNetworkAdminOverview

## SYNOPSIS
Dapatkan gambaran umum status penyedia sumber daya jaringan.

## SYNTAX

```
Get-AzsNetworkAdminOverview [<CommonParameters>]
```

## DESCRIPTION
Dapatkan gambaran umum status penyedia sumber daya jaringan. Properti individu menyediakan jumlah mendetail penggunaan dan kesehatan sumber daya menurut komponen.

## EXAMPLES

### CONTOH 1
```
Get-AzsNetworkAdminOverview
```

Dapatkan gambaran umum admin jaringan.

### CONTOH 2
```
(Get-AzsNetworkAdminOverview).PublicIpAddressUsage
```

Dapatkan penggunaan alamat ip publik.

## PARAMETERS

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Network.Admin.Models.AdminOverview

## CATATAN

## RELATED LINKS
