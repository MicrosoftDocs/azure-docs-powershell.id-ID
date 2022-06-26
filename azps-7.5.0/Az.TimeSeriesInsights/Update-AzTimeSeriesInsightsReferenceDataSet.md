---
external help file: ''
Module Name: Az.TimeSeriesInsights
online version: https://docs.microsoft.com/powershell/module/az.timeseriesinsights/update-aztimeseriesinsightsreferencedataset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TimeSeriesInsights/help/Update-AzTimeSeriesInsightsReferenceDataSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TimeSeriesInsights/help/Update-AzTimeSeriesInsightsReferenceDataSet.md
ms.openlocfilehash: 9043fddf013ce543bbc1144c48c10d495d3c26f4
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146611714"
---
# Update-AzTimeSeriesInsightsReferenceDataSet

## SYNOPSIS
Updates himpunan data referensi dengan nama yang ditentukan dalam langganan, grup sumber daya, dan lingkungan yang ditentukan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.timeseriesinsights/update-aztimeseriesinsightsreferencedataset) untuk informasi terbaru.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzTimeSeriesInsightsReferenceDataSet -EnvironmentName <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzTimeSeriesInsightsReferenceDataSet -InputObject <ITimeSeriesInsightsIdentity> [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Updates himpunan data referensi dengan nama yang ditentukan dalam langganan, grup sumber daya, dan lingkungan yang ditentukan.

## EXAMPLES

### Contoh 1: Memperbarui himpunan data referensi tertentu berdasarkan nama
```powershell
Update-AzTimeSeriesInsightsReferenceDataSet -EnvironmentName tsitest001 -Name dstest001 -ResourceGroupName testgroup -Tag @{"tstg"="lb001"}
```
```output
Location Name      Type
-------- ----      ----
eastus   dstest001 Microsoft.TimeSeriesInsights/Environments/ReferenceDataSets
```

Perintah ini memperbarui himpunan data referensi tertentu.

### Contoh 2: Memperbarui himpunan data referensi tertentu menurut objek
```powershell
$ds = Get-AzTimeSeriesInsightsReferenceDataSet -EnvironmentName tsitest001 -ResourceGroupName testgroup -ReferenceDataSetName dstest001
Update-AzTimeSeriesInsightsReferenceDataSet -InputObject $ds -Tag @{"tstg"="lb001"}
```
```output
Location Name      Type
-------- ----      ----
eastus   dstest001 Microsoft.TimeSeriesInsights/Environments/ReferenceDataSets
```

Perintah ini memperbarui himpunan data referensi tertentu.

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

### -EnvironmentName
Nama lingkungan Time Series Insights yang terkait dengan grup sumber daya yang ditentukan.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.TimeSeriesInsights.Models.ITimeSeriesInsightsIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama himpunan data referensi Insights Time Series yang terkait dengan lingkungan yang ditentukan.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: ReferenceDataSetName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup Sumber Daya Azure.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID Langganan Azure.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Pasangan kunci-nilai properti tambahan untuk himpunan data referensi.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.TimeSeriesInsights.Models.ITimeSeriesInsightsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.TimeSeriesInsights.Models.Api20200515.IReferenceDataSetResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<ITimeSeriesInsightsIdentity>`: Parameter Identitas
  - `[AccessPolicyName <String>]`: Nama kebijakan akses.
  - `[EnvironmentName <String>]`: Nama lingkungan
  - `[EventSourceName <String>]`: Nama sumber peristiwa Time Series Insights yang terkait dengan lingkungan yang ditentukan.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ReferenceDataSetName <String>]`: Nama himpunan data referensi.
  - `[ResourceGroupName <String>]`: Nama grup Sumber Daya Azure.
  - `[SubscriptionId <String>]`: ID Langganan Azure.

## RELATED LINKS

