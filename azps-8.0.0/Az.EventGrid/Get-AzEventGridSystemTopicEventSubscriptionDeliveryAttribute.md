---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridSystemTopicEventSubscriptionDeliveryAttribute.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridSystemTopicEventSubscriptionDeliveryAttribute.md
ms.openlocfilehash: 1b706b948db2f255d551cf51e66f9ac27c7b63cf
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145516291"
---
# Get-AzEventGridSystemTopicEventSubscriptionDeliveryAttribute

## SYNOPSIS
Mendapatkan atribut pengiriman untuk langganan peristiwa topik sistem

## SYNTAX

### TopicNameParameterSet (Default)
```
Get-AzEventGridSystemTopicEventSubscriptionDeliveryAttribute [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SystemTopicEventSuscriptionParameterSet
```
Get-AzEventGridSystemTopicEventSubscriptionDeliveryAttribute -EventSubscriptionName <String>
 -ResourceGroupName <String> -SystemTopicName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar atribut pengiriman untuk langganan peristiwa topik sistem

## EXAMPLES

### Contoh 1
```powershell
Get-AzEventGridSystemTopicEventSubscriptionDeliveryAttribute -ResourceGroupName MyResourceGroupName -SystemTopicName Topic1 -EventSubscriptionName EventSubscription1
```

Mendapatkan daftar atribut pengiriman untuk langganan \`peristiwa EventSubscription1\` yang dibuat untuk topik \`sistem Topic1\` di grup \`sumber daya MyResourceGroupName\`.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventSubscriptionName
Nama langganan peristiwa EventGrid.

```yaml
Type: System.String
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SystemTopicName
Nama topik EventGrid.

```yaml
Type: System.String
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PsDeliveryAttribute

## NOTES

## RELATED LINKS
