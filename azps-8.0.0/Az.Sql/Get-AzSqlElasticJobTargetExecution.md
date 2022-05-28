---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/Az.sql/get-Azsqlelasticjobtargetexecution
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlElasticJobTargetExecution.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlElasticJobTargetExecution.md
ms.openlocfilehash: b7ffffa39881da248b23abcebe24738b93855476
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145506991"
---
# Get-AzSqlElasticJobTargetExecution

## SYNOPSIS
Mendapatkan satu atau beberapa eksekusi target pekerjaan

## SYNTAX

### DefaultSet (Default)
```
Get-AzSqlElasticJobTargetExecution [-ResourceGroupName] <String> [-ServerName] <String> [-AgentName] <String>
 [-JobName] <String> -JobExecutionId <String> -Count <Int32> [-StepName <String>] [-CreateTimeMin <DateTime>]
 [-CreateTimeMax <DateTime>] [-EndTimeMin <DateTime>] [-EndTimeMax <DateTime>] [-Active]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ObjectSet
```
Get-AzSqlElasticJobTargetExecution [-ParentObject] <AzureSqlElasticJobExecutionModel> -Count <Int32>
 [-StepName <String>] [-CreateTimeMin <DateTime>] [-CreateTimeMax <DateTime>] [-EndTimeMin <DateTime>]
 [-EndTimeMax <DateTime>] [-Active] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdSet
```
Get-AzSqlElasticJobTargetExecution [-ParentResourceId] <String> -Count <Int32> [-StepName <String>]
 [-CreateTimeMin <DateTime>] [-CreateTimeMax <DateTime>] [-EndTimeMin <DateTime>] [-EndTimeMax <DateTime>]
 [-Active] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzSqlElasticJobTargetExecution mendapatkan satu atau beberapa eksekusi target pekerjaan dari eksekusi pekerjaan

## EXAMPLES

### Contoh 1: Mendapatkan satu atau beberapa eksekusi target pekerjaan dari eksekusi pekerjaan
```powershell
$je = Get-AzSqlElasticJobExecution -ResourceGroupName rg -ServerName elasticjobserver -AgentName agent -JobName job1 -JobExecutionId 3bcfc912-20b2-411d-a2b7-6265d13fe272
$je | Get-AzSqlElasticJobTargetExecution -Count 2
```

```output
JobName JobVersion StepName StepId JobExecutionId                       Lifecycle       TargetServerName TargetDatabaseName StartTime            EndTime
------- ---------- -------- ------ --------------                       ---------       ---------------- ------------------ ---------            -------
job1    1          step2    1      ea0a870b-dfe3-427e-9f95-d229d7815b65 Succeeded       s1               db2                6/1/2018 10:11:47 PM 6/1/2018 10:11:50 PM
job1    1          step1    1      ea0a870b-dfe3-427e-9f95-d229d7815b65 Succeeded       s1               db1                6/1/2018 10:11:44 PM 6/1/2018 10:11:47 PM
```

### Contoh 2: Mendapatkan satu atau beberapa eksekusi target pekerjaan dari eksekusi pekerjaan - pemfilteran menurut nama langkah
```powershell
$je = Get-AzSqlElasticJobExecution -ResourceGroupName rg -ServerName elasticjobserver -AgentName agent -JobName job1 -JobExecutionId 3bcfc912-20b2-411d-a2b7-6265d13fe272
$je | Get-AzSqlElasticJobTargetExecution -Count 2 -StepName step2
```

```output
JobName JobVersion StepName StepId JobExecutionId                       Lifecycle       TargetServerName TargetDatabaseName StartTime            EndTime
------- ---------- -------- ------ --------------                       ---------       ---------------- ------------------ ---------            -------
job1    1          step2    1      ea0a870b-dfe3-427e-9f95-d229d7815b65 Succeeded       s1               db2                6/1/2018 10:11:47 PM 6/1/2018 10:11:50 PM
```

Mendapatkan satu atau beberapa eksekusi target pekerjaan

## PARAMETERS

### -Aktif
Bendera untuk memfilter menurut eksekusi aktif.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AgentName
Nama agen.

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Count
Count mengembalikan jumlah eksekusi teratas.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateTimeMax
Memfilter menurut maks waktu pembuatan

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateTimeMin
Filter menurut waktu pembuatan min

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
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

### -EndTimeMax
Filter menurut waktu akhir maks.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTimeMin
Filter menurut waktu akhir min.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobExecutionId
Id eksekusi pekerjaan.

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName
Nama pekerjaan.

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentObject
Objek eksekusi pekerjaan.

```yaml
Type: Microsoft.Azure.Commands.Sql.ElasticJobs.Model.AzureSqlElasticJobExecutionModel
Parameter Sets: ObjectSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ParentResourceId
Id sumber daya eksekusi pekerjaan.

```yaml
Type: System.String
Parameter Sets: ResourceIdSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Nama server.

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StepName
Nama langkah pekerjaan.

```yaml
Type: System.String
Parameter Sets: (All)
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

### Microsoft.Azure.Commands.Sql.ElasticJobs.Model.AzureSqlElasticJobExecutionModel

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ElasticJobs.Model.AzureSqlElasticJobExecutionModel

## NOTES

## RELATED LINKS
