---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/get-azwebpubsubsku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubSku.md
ms.openlocfilehash: 87138838b983bc2f5b48377b5a5d2fc27c75ed96
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145629782"
---
# Get-AzWebPubSubSku

## SYNOPSIS
Cantumkan semua sku sumber daya yang tersedia.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.signalr/get-azwebpubsubsku) untuk informasi terbaru.

## SYNTAX

```
Get-AzWebPubSubSku -ResourceGroupName <String> -ResourceName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Cantumkan semua sku sumber daya yang tersedia.

## EXAMPLES

### Contoh 1: Mencantumkan semua SKU yang tersedia dari sumber daya Web PubSub
```powershell
Get-AzWebPubSubSku -ResourceGroupName psdemo -ResourceName psdemo-wps | Format-List
```

```output
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

Contohnya mencantumkan SKU sumber daya Web PubSub lalu menyalurkan hasilnya untuk `Format-List` melihat semua nilai properti hasilnya.
Kita dapat melihat dari hasil bahwa ada dua SKU, Tingkat seseorang adalah "Gratis", dan yang lainnya adalah "Standar".

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
Nama grup sumber daya yang berisi sumber daya.
Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.

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
Mendapatkan ID langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.ISkuList

## NOTES

ALIAS

## RELATED LINKS

