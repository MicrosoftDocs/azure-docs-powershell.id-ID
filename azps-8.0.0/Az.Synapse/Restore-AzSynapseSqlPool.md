---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/restore-azsynapsesqlpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Restore-AzSynapseSqlPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Restore-AzSynapseSqlPool.md
ms.openlocfilehash: 4d08fb2049c766150aebd5f78520068dcf806e20
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145517578"
---
# Restore-AzSynapseSqlPool

## SYNOPSIS
Memulihkan kumpulan SQL Synapse Analytics.

## SYNTAX

### RestoreFromBackupIdByNameParameterSet (Default)
```
Restore-AzSynapseSqlPool [-FromBackup] [-ResourceGroupName <String>] -WorkspaceName <String> -Name <String>
 -ResourceId <String> [-Tag <Hashtable>] [-StorageAccountType <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RestoreFromBackupIdByParentObjectParameterSet
```
Restore-AzSynapseSqlPool [-FromBackup] -WorkspaceObject <PSSynapseWorkspace> -Name <String>
 -ResourceId <String> [-Tag <Hashtable>] [-StorageAccountType <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RestoreFromRestorePointIdByNameParameterSet
```
Restore-AzSynapseSqlPool [-FromRestorePoint] [-ResourceGroupName <String>] -WorkspaceName <String>
 -Name <String> -PerformanceLevel <String> -ResourceId <String> -RestorePoint <DateTime> [-Tag <Hashtable>]
 [-StorageAccountType <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RestoreFromRestorePointIdByParentObjectParameterSet
```
Restore-AzSynapseSqlPool [-FromRestorePoint] -WorkspaceObject <PSSynapseWorkspace> -Name <String>
 -PerformanceLevel <String> -ResourceId <String> -RestorePoint <DateTime> [-Tag <Hashtable>]
 [-StorageAccountType <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RestoreFromDroppedSqlPoolByNameParameterSet
```
Restore-AzSynapseSqlPool [-FromDroppedSqlPool] [-ResourceGroupName <String>] -WorkspaceName <String>
 -Name <String> -ResourceId <String> -DeletionDate <DateTime> [-Tag <Hashtable>] [-StorageAccountType <String>]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RestoreFromDroppedSqlPoolByParentObjectParameterSet
```
Restore-AzSynapseSqlPool [-FromDroppedSqlPool] -WorkspaceObject <PSSynapseWorkspace> -Name <String>
 -ResourceId <String> -DeletionDate <DateTime> [-Tag <Hashtable>] [-StorageAccountType <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Restore-AzSynapseSqlPool** memulihkan kumpulan Azure Synapse Analytics SQL dari cadangan geo-redundan, cadangan kumpulan SQL yang dihapus atau titik pemulihan kumpulan SQL apa pun.
Kumpulan SQL yang dipulihkan dibuat sebagai kumpulan SQL baru.

## EXAMPLES

### Contoh 1
```powershell
# Transform Synapse SQL pool resource ID to SQL database ID because 
# currently the command only accepts the SQL databse ID. For example: /subscriptions/<SubscriptionId>/resourceGroups/<ResourceGroupName>/providers/Microsoft.Sql/servers/<WorkspaceName>/databases/<DatabaseName>
$pool = Get-AzSynapseSqlPool -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name ContosoSqlPool
$databaseId = $pool.Id -replace "Microsoft.Synapse", "Microsoft.Sql" `
    -replace "workspaces", "servers" `
    -replace "sqlPools", "databases"
 
# Get the latest restore point
$restorePoint = $pool | Get-AzSynapseSqlPoolRestorePoint | Select-Object -Last 1

# Restore to same workspace with source SQL pool
$restoredPool = Restore-AzSynapseSqlPool -FromRestorePoint -RestorePoint $restorePoint.RestorePointCreationDate -TargetSqlPoolName ContosoRestoredSqlPool -ResourceGroupName $pool.ResourceGroupName -WorkspaceName $pool.WorkspaceName -ResourceId $databaseId -PerformanceLevel DW200c
```

Perintah ini membuat kumpulan SQL Azure Synapse Analytics dengan memanfaatkan titik pemulihan dari kumpulan SQL yang ada untuk memulihkan atau menyalin dari status sebelumnya.

### Contoh 2
```powershell
# Transform Synapse SQL pool resource ID to SQL database ID because
# currently the command only accepts the SQL databse ID. For example: /subscriptions/<SubscriptionId>/resourceGroups/<ResourceGroupName>/providers/Microsoft.Sql/servers/<WorkspaceName>/recoverabledatabases/<DatabaseName>
$pool = Get-AzSynapseSqlPoolGeoBackup -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name ContosoSqlPool
$databaseId = $pool.Id -replace "Microsoft.Synapse", "Microsoft.Sql" `
    -replace "workspaces", "servers"

# Restore to same workspace with source SQL pool
$restoredPool = Restore-AzSynapseSqlPool -FromBackup -TargetSqlPoolName ContosoRestoredSqlPool -ResourceGroupName $pool.ResourceGroupName -WorkspaceName $pool.WorkspaceName -ResourceId $databaseId
```

Perintah ini membuat kumpulan SQL Azure Synapse Analytics yang dipulihkan dari cadangan kumpulan SQL.

### Contoh: 3
```powershell
# Transform Synapse dropped SQL pool resource ID to SQL pool resource ID
$pool = Get-AzSynapseDroppedSqlPool -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name ContosoSqlPool
$poolId = $pool.Id.Split(",")[0]
$poolId = $poolId -replace "restorableDroppedSqlPools", "sqlPools"

# Restore to same workspace with source SQL pool
$restoredPool = Restore-AzSynapseSqlPool -FromDroppedSqlPool -DeletionDate $pool.DeletionDate -TargetSqlPoolName ContosoRestoredSqlPool -ResourceGroupName $pool.ResourceGroupName -WorkspaceName $pool.WorkspaceName -ResourceId $poolId
```

Perintah ini membuat kumpulan SQL Azure Synapse Analytics yang dipulihkan dari cadangan kumpulan SQL yang dihapus.

### Contoh 4
```powershell
# Transform Synapse SQL pool resource ID to SQL database ID because 
# currently the command only accepts the SQL databse ID. For example: /subscriptions/<SubscriptionId>/resourceGroups/<ResourceGroupName>/providers/Microsoft.Sql/servers/<WorkspaceName>/databases/<DatabaseName>
$pool = Get-AzSynapseSqlPool -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name ContosoSqlPool
$databaseId = $pool.Id -replace "Microsoft.Synapse", "Microsoft.Sql" `
    -replace "workspaces", "servers" `
    -replace "sqlPools", "databases"

# Get the latest restore point
$restorePoint = $pool | Get-AzSynapseSqlPoolRestorePoint | Select-Object -Last 1

# Restore to same workspace with source SQL pool
$restoredPool = Restore-AzSynapseSqlPool -FromRestorePoint -RestorePoint $restorePoint.RestorePointCreationDate -TargetSqlPoolName ContosoRestoredSqlPool -ResourceGroupName $pool.ResourceGroupName -WorkspaceName $pool.WorkspaceName -ResourceId $databaseId -PerformanceLevel DW200c -Tag @{"tagName" = "tagValue"} -StorageAccountType LRS
```

Perintah ini membuat kumpulan SQL Azure Synapse Analytics dengan tag dan jenis akun penyimpanan tertentu dengan memanfaatkan titik pemulihan dari kumpulan SQL yang ada untuk memulihkan atau menyalin dari status sebelumnya.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
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

### -DeletionDate
Tanggal penghapusan Azure Synaspe SQL Database untuk mengambil cadangan, dengan presisi milidetik (misalnya 2016-02-23T00:21:22.847Z)

```yaml
Type: System.DateTime
Parameter Sets: RestoreFromDroppedSqlPoolByNameParameterSet, RestoreFromDroppedSqlPoolByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FromBackup
Menunjukkan untuk memulihkan dari cadangan terbaru dari kumpulan SQL apa pun dalam langganan ini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RestoreFromBackupIdByNameParameterSet, RestoreFromBackupIdByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FromDroppedSqlPool
Menunjukkan untuk memanfaatkan titik pemulihan dari kumpulan SQL apa pun dalam langganan ini untuk memulihkan atau menyalin dari status sebelumnya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RestoreFromDroppedSqlPoolByNameParameterSet, RestoreFromDroppedSqlPoolByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FromRestorePoint
Menunjukkan untuk memanfaatkan titik pemulihan dari kumpulan SQL apa pun dalam langganan ini untuk memulihkan atau menyalin dari status sebelumnya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RestoreFromRestorePointIdByNameParameterSet, RestoreFromRestorePointIdByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama kumpulan SQL Synapse.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetSqlPoolName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PerformanceLevel
Tingkat layanan SQL dan tingkat performa untuk ditetapkan ke kumpulan SQL.
Misalnya, DW2000c.

```yaml
Type: System.String
Parameter Sets: RestoreFromRestorePointIdByNameParameterSet, RestoreFromRestorePointIdByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: RestoreFromBackupIdByNameParameterSet, RestoreFromRestorePointIdByNameParameterSet, RestoreFromDroppedSqlPoolByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya database yang akan dipulihkan.

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

### -RestorePoint
Waktu rekam jepret untuk dipulihkan.

```yaml
Type: System.DateTime
Parameter Sets: RestoreFromRestorePointIdByNameParameterSet, RestoreFromRestorePointIdByParentObjectParameterSet
Aliases: PointInTime

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountType
Jenis akun penyimpanan yang digunakan untuk menyimpan cadangan untuk kumpulan sql. Nilai yang mungkin termasuk: 'GRS', 'LRS'.

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

### -Tag
String, kamus string tag yang terkait dengan sumber daya.

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

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: RestoreFromBackupIdByNameParameterSet, RestoreFromRestorePointIdByNameParameterSet, RestoreFromDroppedSqlPoolByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
objek input ruang kerja, biasanya melewati alur.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: RestoreFromBackupIdByParentObjectParameterSet, RestoreFromRestorePointIdByParentObjectParameterSet, RestoreFromDroppedSqlPoolByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseSqlPool

## NOTES

## RELATED LINKS
