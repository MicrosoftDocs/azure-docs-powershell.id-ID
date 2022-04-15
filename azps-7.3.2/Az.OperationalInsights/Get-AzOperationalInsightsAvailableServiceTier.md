---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/get-AzOperationalInsightsAvailableServiceTier
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsAvailableServiceTier.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsAvailableServiceTier.md
ms.openlocfilehash: 362e87db229d50a33418ba34a5b28130d748c0c4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142466747"
---
# Get-AzOperationalInsightsAvailableServiceTier

## SYNOPSIS
Perintah ini mendapatkan semua tingkat layanan yang tersedia untuk hasil kerja tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.operationalinsights/get-azoperationalinsightsavailableservicetier) untuk informasi terbaru.

## SYNTAX

```
Get-AzOperationalInsightsAvailableServiceTier [-ResourceGroupName] <String> [-WorkspaceName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Perintah ini mendapatkan semua tingkat layanan yang tersedia untuk hasil kerja tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzOperationalInsightsAvailableServiceTier -ResourceGroupName ContosoResourceGroup -WorkspaceName MyWorkspace

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

Perintah ini mendapatkan semua tingkat layanan yang tersedia untuk hasil kerja tertentu.

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

### -Nama Ruang Kerja
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSAvailableServiceTier

## CATATAN

## RELATED LINKS
