---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridFullUrlForSystemTopicEventSubscription.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridFullUrlForSystemTopicEventSubscription.md
ms.openlocfilehash: 76bc47056e71bea5f81526909498d6c9ce2d2696
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145559393"
---
# Get-AzEventGridFullUrlForSystemTopicEventSubscription

## SYNOPSIS
Mendapatkan URL lengkap untuk langganan peristiwa topik sistem

## SYNTAX

### TopicNameParameterSet (Default)
```
Get-AzEventGridFullUrlForSystemTopicEventSubscription [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SystemTopicEventSuscriptionParameterSet
```
Get-AzEventGridFullUrlForSystemTopicEventSubscription -EventSubscriptionName <String>
 -ResourceGroupName <String> -SystemTopicName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan URL titik akhir lengkap jika merupakan langganan peristiwa berbasis webhook.

## EXAMPLES

### Contoh 1
```powershell
Get-AzEventGridFullUrlForSystemTopicEventSubscription -ResourceGroupName MyResourceGroupName -SystemTopicName Topic1 -EventSubscriptionName EventSubscription1
```

Mendapatkan URL titik akhir lengkap untuk langganan \`peristiwa EventSubscription1\` yang dibuat untuk topik \`sistem Topic1\` di grup \`sumber daya MyResourceGroupName\`.

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

### System.String

## NOTES

## RELATED LINKS