---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/get-AzOperationalInsightsAvailableServiceTier
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsAvailableServiceTier.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsAvailableServiceTier.md
ms.openlocfilehash: 89ae04ebbacc11a16ba5e00647f9f66c2bb1300c
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144654896"
---
# Get-AzOperationalInsightsAvailableServiceTier

## SYNOPSIS
Perintah ini mendapatkan semua tingkat layanan yang tersedia untuk worksapce tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.operationalinsights/get-azoperationalinsightsavailableservicetier) untuk informasi terbaru.

## SYNTAX

```
Get-AzOperationalInsightsAvailableServiceTier [-ResourceGroupName] <String> [-WorkspaceName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Perintah ini mendapatkan semua tingkat layanan yang tersedia untuk worksapce tertentu.

## EXAMPLES

### Contoh 1
```powershell
Get-AzOperationalInsightsAvailableServiceTier -ResourceGroupName ContosoResourceGroup -WorkspaceName MyWorkspace
```

```output
ServiceTier              : PerGB2018
Enabled                  : True
MinimumRetention         : 30
MaximumRetention         : 730
DefaultRetention         : 30
CapacityReservationLevel :
LastSkuUpdate            :

ServiceTier              : CapacityReservation
Enabled                  : True
MinimumRetention         : 30
MaximumRetention         : 730
DefaultRetention         : 31
CapacityReservationLevel :
LastSkuUpdate            : Tue, 16 Nov 2021 13:20:32 GMT
```

Perintah ini mendapatkan semua tingkat layanan yang tersedia untuk worksapce tertentu.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja yang berisi tabel.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSAvailableServiceTier

## NOTES

## RELATED LINKS
