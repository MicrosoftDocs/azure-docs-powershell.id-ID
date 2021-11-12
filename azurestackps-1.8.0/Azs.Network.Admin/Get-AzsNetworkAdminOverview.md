---
external help file: Azs.Network.Admin-help.xml
Module Name: Azs.Network.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6c22881ad3509dca07d6272376168218b0dfdec735a936c6760fc0d9956e3c5e
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132416305"
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
