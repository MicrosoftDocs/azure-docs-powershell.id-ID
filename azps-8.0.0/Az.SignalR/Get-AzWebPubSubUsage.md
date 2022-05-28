---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/get-azwebpubsubusage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubUsage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubUsage.md
ms.openlocfilehash: 34dc4fa0d293b3b913b038c29f28e121073f45b2
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145508818"
---
# Get-AzWebPubSubUsage

## SYNOPSIS
Cantumkan kuota penggunaan sumber daya berdasarkan lokasi.

## SYNTAX

```
Get-AzWebPubSubUsage -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Cantumkan kuota penggunaan sumber daya berdasarkan lokasi.

## EXAMPLES

### Contoh 1: Mencantumkan penggunaan Web PubSub di wilayah AS timur.
```powershell
Get-AzWebPubSubUsage -Location eastus | Format-List
```

```output
CurrentValue       : 4
Id                 : /subscriptions/9caf2a1e-9c49-49b6-89a2-56bdec7e3f97/providers/Microsoft.SignalRService/locations/eastus/usages/FreeTierInstances
Limit              : 5
NameLocalizedValue : Free Tier SignalR Instances per subscription
NameValue          : FreeTierInstances
Unit               : Count

CurrentValue       : 225
Id                 : /subscriptions/9caf2a1e-9c49-49b6-89a2-56bdec7e3f97/providers/Microsoft.SignalRService/locations/eastus/usages/SignalRTotalUnits
Limit              : 1500
NameLocalizedValue : SignalRTotalUnits
NameValue          : SignalRTotalUnits
Unit               : Count
```

Contoh menyalurkan hasil `Get-AzWebPubSubUsage -Location eastus` ke `Format-list` untuk melihat nilai semua properti hasil.

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

### -Lokasi
lokasi seperti "eastus"

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
Mendapatkan Id langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
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

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.ISignalRServiceUsage

## NOTES

ALIAS

## RELATED LINKS

