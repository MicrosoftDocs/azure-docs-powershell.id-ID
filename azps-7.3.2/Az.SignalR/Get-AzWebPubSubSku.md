---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/get-azwebpubsubsku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubSku.md
ms.openlocfilehash: b86da37bfcf31ffae262d510fc3c1714e18a9de7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142758178"
---
# Get-AzWebPubSubSku

## SYNOPSIS
Cantumkan semua sku yang tersedia dari sumber daya.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.signalr/get-azwebpubsubsku) untuk informasi terbaru.

## SYNTAX

```
Get-AzWebPubSubSku -ResourceGroupName <String> -ResourceName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Cantumkan semua sku yang tersedia dari sumber daya.

## EXAMPLES

### Contoh 1: Mencantumkan semua SKU yang tersedia dari sumber daya PubSub Web
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

Contoh ini mencantumkan SKU sumber daya PubSub Web lalu menyalurkan hasil untuk `Format-List` melihat semua nilai properti hasil.
Kita dapat melihat dari hasil bahwa ada dua SKU, Satu Tingkat adalah "Gratis", dan yang lainnya adalah "Standar".

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
Anda dapat memperoleh nilai ini dari API azure Resource Manager atau portal.

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
Mendapatkan Id langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.ISkuList

## NOTES

ALIAS

## RELATED LINKS

