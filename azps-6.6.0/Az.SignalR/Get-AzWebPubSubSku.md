---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/get-azwebpubsubsku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubSku.md
ms.openlocfilehash: 9cb734803be43ef26a635a07087ba52c74610c19
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136334567"
---
# Get-AzWebPubSubSku

## SYNOPSIS
Mencantumkan semua sku sumber daya yang tersedia.

## SYNTAX

```
Get-AzWebPubSubSku -ResourceGroupName <String> -ResourceName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua sku sumber daya yang tersedia.

## EXAMPLES

### Contoh 1: Mencantumkan semua SKU sumber daya PubSub Web yang tersedia
```powershell
PS C:\>  Get-AzWebPubSubSku -ResourceGroupName psdemo -ResourceName psdemo-wps | Format-List

CapacityAllowedValue : {0, 1}
CapacityDefault      : 1
CapacityMaximum      : 1
CapacityMinimum      : 0
CapacityScaleType    : Manual
Family               :
Name                 : Free_F1
ResourceType         : Microsoft.SignalRService/WebPubSub
Size                 :
SkuCapacity          :
Tier                 : Free

CapacityAllowedValue : {0, 1, 2, 5…}
CapacityDefault      : 1
CapacityMaximum      : 100
CapacityMinimum      : 0
CapacityScaleType    : Automatic
Family               :
Name                 : Standard_S1
ResourceType         : Microsoft.SignalRService/WebPubSub
Size                 :
SkuCapacity          :
Tier                 : Standard
```

Contoh tersebut mencantumkan SKU sumber daya PubSub Web, lalu mencantumkan hasil untuk `Format-List` melihat semua nilai properti dari hasil tersebut.
Kita dapat melihat dari hasil bahwa ada dua SKU, satu Tingkatan "Gratis", dan yang lainnya "Standar".

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya tersebut.
Anda dapat memperoleh nilai ini dari API Azure Resource Manager atau portal.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceName
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Mendapatkan Id langganan yang secara unik mengidentifikasi Microsoft Azure Anda.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.ISkuList

## CATATAN

ALIAS

## RELATED LINKS

