---
external help file: Azs.Subscriptions.Admin-help.xml
Module Name: Azs.Subscriptions.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 66337bc49bdb31133b501b32b9bd4c59463c1e0eb963009fc9feae82c4a2f079
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417250"
---
# Get-AzsSubscriptionsQuota

## SYNOPSIS
Dapatkan daftar kuota penyedia sumber daya langganan di suatu lokasi.

## SYNTAX

### Daftar (Default)
```
Get-AzsSubscriptionsQuota [-Location <String>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzsSubscriptionsQuota -Name <String> [-Location <String>] [<CommonParameters>]
```

### ResourceId
```
Get-AzsSubscriptionsQuota -ResourceId <String> [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar kuota di lokasi.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Get-AzsSubscriptionsQuota
```

Dapatkan daftar kuota penyedia sumber daya langganan di suatu lokasi.

## PARAMETERS

### -Lokasi
Lokasi AzureStack.

```yaml
Type: String
Parameter Sets: List, Get
Aliases: ArmLocation

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kuota.

```yaml
Type: String
Parameter Sets: Get
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya.

```yaml
Type: String
Parameter Sets: ResourceId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Subscriptions.Admin.Models.Quota

## CATATAN

## RELATED LINKS

