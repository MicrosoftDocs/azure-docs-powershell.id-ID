---
external help file: Azs.Network.Admin-help.xml
Module Name: Azs.Network.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 3f5fbef7c67676f16793b63a8448517ca24aa7e5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143101493"
---
# Get-AzsNetworkAdminOverview

## SYNOPSIS
Dapatkan gambaran umum status penyedia sumber daya jaringan.

## SYNTAX

```
Get-AzsNetworkAdminOverview [<CommonParameters>]
```

## DESCRIPTION
Dapatkan gambaran umum status penyedia sumber daya jaringan. Properti individual menyediakan jumlah mendetail penggunaan sumber daya dan kesehatan menurut komponen.

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

Dapatkan penggunaan alamat IP publik.

## PARAMETERS

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Network.Admin.Models.AdminOverview

## NOTES

## RELATED LINKS
