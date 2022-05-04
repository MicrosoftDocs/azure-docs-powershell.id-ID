---
external help file: ''
Module Name: Az.Functions
online version: https://docs.microsoft.com/powershell/module/az.functions/get-azfunctionappavailablelocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Get-AzFunctionAppAvailableLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Get-AzFunctionAppAvailableLocation.md
ms.openlocfilehash: f231772bfc6348ff3ae3083150f4473a075566c6
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144572996"
---
# Get-AzFunctionAppAvailableLocation

## SYNOPSIS
Mendapatkan lokasi tempat aplikasi fungsi untuk os dan jenis paket yang diberikan tersedia.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.functions/get-azfunctionappavailablelocation) untuk informasi terbaru.

## SYNTAX

```
Get-AzFunctionAppAvailableLocation [[-SubscriptionId] <String[]>] [[-PlanType] <String>] [[-OSType] <String>]
 [[-DefaultProfile] <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan lokasi tempat aplikasi fungsi untuk os dan jenis paket yang diberikan tersedia.

## EXAMPLES

### Contoh 1: Dapatkan lokasi tempat Premium tersedia untuk Windows. Jika tidak ada parameter yang ditentukan, PlanType diatur ke 'Premium' dan OSType diatur ke 'Windows'.
```powershell
Get-AzFunctionAppAvailableLocation
```

```output
Name
----
Central US
North Europe
West Europe
Southeast Asia
East Asia
West US
East US
Japan West
Japan East
East US 2
North Central US
South Central US
Brazil South
Australia East
Australia Southeast
East Asia (Stage)
West India
South India
Canada Central
West US 2
UK West
UK South
East US 2 EUAP
Central US EUAP
Korea Central
France Central
Australia Central 2
Australia Central
Germany West Central
Norway East
```

Perintah ini mendapatkan lokasi tempat Premium tersedia untuk Windows.

### Contoh 2: Dapatkan lokasi tempat Premium tersedia untuk Linux.
```powershell
Get-AzFunctionAppAvailableLocation -PlanType Premium -OSType Linux
```

```output
Name
----
Central US
North Europe
West Europe
Southeast Asia
East Asia
West US
East US
Japan West
Japan East
East US 2
North Central US
South Central US
Brazil South
Australia East
Australia Southeast
West India
Canada Central
West Central US
West US 2
UK West
UK South
Central US EUAP
Korea Central
France Central
Norway East
```

Perintah ini mendapatkan lokasi tempat Premium tersedia untuk Linux.

### Contoh 3: Dapatkan lokasi tempat Konsumsi tersedia untuk Windows.
```powershell
Get-AzFunctionAppAvailableLocation -PlanType Consumption -OSType Windows
```

```output
Name
----
Central US
North Europe
West Europe
Southeast Asia
East Asia
West US
East US
Japan West
Japan East
East US 2
North Central US
South Central US
Brazil South
Australia East
Australia Southeast
East Asia (Stage)
Central India
West India
South India
Canada Central
Canada East
West Central US
West US 2
UK West
UK South
East US 2 EUAP
Central US EUAP
Korea Central
France Central
Australia Central 2
Australia Central
South Africa North
Switzerland North
Germany West Central
```

Perintah ini mendapatkan lokasi di mana Konsumsi tersedia untuk Windows.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSType
Jenis OS untuk paket layanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlanType
Jenis paket.
Input yang valid: Konsumsi atau Premium

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Atur ID Langganan Azure.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Functions.Models.Api20190801.IGeoRegion

## NOTES

ALIAS

## RELATED LINKS

