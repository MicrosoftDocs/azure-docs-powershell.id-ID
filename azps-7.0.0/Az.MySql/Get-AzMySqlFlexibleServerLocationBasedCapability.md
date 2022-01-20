---
external help file: ''
Module Name: Az.MySql
online version: https://docs.microsoft.com/powershell/module/az.mysql/get-azmysqlflexibleserverlocationbasedcapability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Get-AzMySqlFlexibleServerLocationBasedCapability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Get-AzMySqlFlexibleServerLocationBasedCapability.md
ms.openlocfilehash: abd12b46eefa62bd4ce8edb0598eb4f9ee969a19
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136397202"
---
# Get-AzMySqlFlexibleServerLocationBasedCapability

## SYNOPSIS
Mendapatkan informasi SKU yang tersedia untuk lokasi

## SYNTAX

```
Get-AzMySqlFlexibleServerLocationBasedCapability -Location <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi SKU yang tersedia untuk lokasi

## EXAMPLES

### Contoh 1: Mendapatkan kapabilitas lokasi menurut nama lokasi
```powershell
PS C:\> Get-AzMySqlFlexibleServerLocationBasedCapability -Location westus2
"Please refer to https://aka.ms/mysql-pricing for pricing details"

SKU               Memory Tier            vCore
---               ------ ----            -----
Standard_B1s        1024 Burstable           1
Standard_B1ms       2048 Burstable           1
Standard_B2s        2048 Burstable           2
Standard_D2ds_v4    4096 GeneralPurpose      2
Standard_D4ds_v4    4096 GeneralPurpose      4
Standard_D8ds_v4    4096 GeneralPurpose      8
Standard_D16ds_v4   4096 GeneralPurpose     16
Standard_D32ds_v4   4096 GeneralPurpose     32
Standard_D48ds_v4   4096 GeneralPurpose     48
Standard_D64ds_v4   4096 GeneralPurpose     64
Standard_E2ds_v4    8192 MemoryOptimized     2
Standard_E4ds_v4    8192 MemoryOptimized     4
Standard_E8ds_v4    8192 MemoryOptimized     8
Standard_E16ds_v4   8192 MemoryOptimized    16
Standard_E32ds_v4   8192 MemoryOptimized    32
Standard_E48ds_v4   8192 MemoryOptimized    48
Standard_E64ds_v4   8192 MemoryOptimized    64

```

Cmdlet ini memperlihatkan informasi sku dasar dari lokasi yang disediakan.

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
Nama lokasi.

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
ID langganan target.

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

### Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20210501.ICapabilityProperties

## CATATAN

ALIAS

## RELATED LINKS

