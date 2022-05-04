---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/get-azpurviewtrigger
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewTrigger.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewTrigger.md
ms.openlocfilehash: 7402e650fab9844e62e595bbe308ad44acdd3568
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144597578"
---
# Get-AzPurviewTrigger

## SYNOPSIS
Mendapatkan informasi pemicu

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/get-azpurviewtrigger) untuk informasi terbaru.

## SYNTAX

```
Get-AzPurviewTrigger -Endpoint <String> -DataSourceName <String> -ScanName <String>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi pemicu

## EXAMPLES

### Contoh 1: Dapatkan jadwal pemicu untuk eksekusi pemindaian
```powershell
PS C:\> Get-AzPurviewTrigger -Endpoint https://parv-brs-2.purview.azure.com/ -DataSourceName 'DataScanTestData-Parv' -ScanName 'Scan-6HK'

CreatedAt                  : 2/17/2022 1:35:12 PM
Id                         : datasources/DataScanTestData-Parv/scans/Scan-6HK/triggers/default
IncrementalScanStartTime   :
Interval                   : 1
LastModifiedAt             : 2/17/2022 1:35:12 PM
LastScheduled              :
Name                       : default
RecurrenceEndTime          : 7/20/2022 12:00:00 AM
RecurrenceFrequency        : Month
RecurrenceInterval         :
RecurrenceStartTime        : 2/17/2022 1:32:00 PM
RecurrenceTimeZone         :
ResourceGroupName          :
ScanLevel                  : Incremental
ScheduleAdditionalProperty : {
                             }
ScheduleHour               : {9}
ScheduleMinute             : {0}
ScheduleMonthDay           : {10}
ScheduleMonthlyOccurrence  :
ScheduleWeekDay            :
```

Mendapatkan jadwal pemicu untuk eksekusi pemindaian

## PARAMETERS

### -DataSourceName
.

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

### -Titik akhir
Titik akhir pemindaian akun purview Anda.
Contoh: https://{accountName}.purview.azure.com

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

### -ScanName
.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.ITrigger

## NOTES

ALIAS

## RELATED LINKS
