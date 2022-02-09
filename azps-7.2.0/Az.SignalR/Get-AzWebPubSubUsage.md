---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/get-azwebpubsubusage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubUsage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubUsage.md
ms.openlocfilehash: cab7eb58f775a56f842b93930fbba440d176c036
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138264556"
---
# Get-AzWebPubSubUsage

## SYNOPSIS
Mencantumkan kuota penggunaan sumber daya menurut lokasi.

## SYNTAX

```
Get-AzWebPubSubUsage -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan kuota penggunaan sumber daya menurut lokasi.

## EXAMPLES

### Contoh 1: List Web PubSub usage in east US region.
```powershell
PS C:\> Get-AzWebPubSubUsage -Location eastus | Format-List

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

Contoh akan pipes hasil `Get-AzWebPubSubUsage -Location eastus` untuk `Format-list` menampilkan nilai semua properti dari hasil.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.ISignalrServiceUsage

## CATATAN

ALIAS

## RELATED LINKS

