---
external help file: Microsoft.Azure.PowerShell.Cmdlets.AlertsManagement.dll-Help.xml
Module Name: Az.AlertsManagement
online version: https://docs.microsoft.com/powershell/module/az.alertsmanagement/get-azalert
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/Get-AzAlert.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/Get-AzAlert.md
ms.openlocfilehash: 78397996082eea9b4756aa6d5d3b2bcfa55ab18b
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145782550"
---
# Get-AzAlert

## SYNOPSIS
Dapatkan Informasi Pemberitahuan

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.alertsmanagement/get-azalert) untuk informasi terbaru.

## SYNTAX

### AlertsListByFilter (Default)
```
Get-AzAlert [-TargetResourceType <String>] [-TargetResourceGroup <String>] [-MonitorService <String>]
 [-MonitorCondition <String>] [-Severity <String>] [-State <String>] [-AlertRuleId <String>]
 [-SmartGroupId <String>] [-IncludeContext <Boolean>] [-IncludeEgressConfig <Boolean>] [-PageCount <Int32>]
 [-SortBy <String>] [-SortOrder <String>] [-TimeRange <String>] [-CustomTimeRange <String>] [-Select <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AlertById
```
Get-AzAlert -AlertId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AlertsListByTargetResourceIdFilter
```
Get-AzAlert [-TargetResourceId <String>] [-MonitorService <String>] [-MonitorCondition <String>]
 [-Severity <String>] [-State <String>] [-AlertRuleId <String>] [-SmartGroupId <String>]
 [-IncludeContext <Boolean>] [-IncludeEgressConfig <Boolean>] [-PageCount <Int32>] [-SortBy <String>]
 [-SortOrder <String>] [-TimeRange <String>] [-CustomTimeRange <String>] [-Select <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Get-AzAlert** mendapatkan instans pemberitahuan yang diaktifkan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzAlert -Severity "Sev2" -MonitorCondition "Fired" -IncludeContext $true
```

Cantumkan semua pemberitahuan dengan tingkat keparahan Sev2 dan kondisi Monitor yang diaktifkan. Mengatur IncludeContext ke true, sertakan payload kustom pemberitahuan.
Gunakan Format-List untuk mendapatkan detail lengkap setiap pemberitahuan dalam daftar.

### Contoh 2
```powershell
Get-AzAlert -AlertId "afbf1b3a-0a6c-4f19-9c9b-644ccd7b1529" | Format-List
```

Dapatkan detail Pemberitahuan berdasarkan Id (GUID) atau Id Sumber Daya (Id ARM Lengkap)

### Contoh: 3

Mendapatkan Informasi Pemberitahuan. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Get-AzAlert -IncludeContext $true -TimeRange '1h'
```

## PARAMETERS

### -AlertId
Pengidentifikasi Unik Pemberitahuan / ResourceId pemberitahuan.

```yaml
Type: System.String
Parameter Sets: AlertById
Aliases: ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AlertRuleId
Filter pada Id Aturan Pemberitahuan

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomTimeRange
Format yang didukung - \<start-time\>/\<end-time\> di mana waktu dalam format ISO-8601

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeContext
Sertakan konteks (payload kustom) pemberitahuan

```yaml
Type: System.Boolean
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeEgressConfig
Sertakan EgressConfig

```yaml
Type: System.Boolean
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitorCondition
Filter pada Kondisi Monitor

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitorService
Filter pada Layanan Moniter

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PageCount
Jumlah pemberitahuan yang akan diambil dalam halaman.

```yaml
Type: System.Int32
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pilih
Project bidang yang diperlukan dari hal-hal penting.
Input yang diharapkan dipisahkan koma.

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tingkat keparahan
Filter pada Tingkat Keparahan pemberitahuan

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmartGroupId
Memfilter semua pemberitahuan yang memiliki Id Grup Cerdas

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SortBy
Properti pemberitahuan yang akan digunakan saat mengurutkan

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SortOrder
Urutan Sortir

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Filter pada Status pemberitahuan

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetResourceGroup
Filter pada nama grup Sumber Daya dari sumber daya target pemberitahuan.

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetResourceId
Filter pada Id Sumber Daya dari sumber daya target pemberitahuan.

```yaml
Type: System.String
Parameter Sets: AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetResourceType
Filter pada Jenis sumber daya dari sumber daya target pemberitahuan.

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeRange
Nilai rentang waktu yang didukung - 1 jam, 1d, 7d, 30d (Defaultnya adalah 1d)

```yaml
Type: System.String
Parameter Sets: AlertsListByFilter, AlertsListByTargetResourceIdFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.AlertsManagement.OutputModels.PSAlert

## NOTES

## RELATED LINKS
