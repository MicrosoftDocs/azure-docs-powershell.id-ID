---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/restore-azsynapsesqlpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Restore-AzSynapseSqlPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Restore-AzSynapseSqlPool.md
ms.openlocfilehash: e2cea0190665c1911a35621175ad2e818bcaf920
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142754182"
---
# Restore-AzSynapseSqlPool

## SYNOPSIS
Memulihkan kumpulan SQL Synapse Analytics.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/restore-azsynapsesqlpool) untuk informasi terbaru.

## SYNTAX

### RestoreFromBackupIdByNameParameterSet (Default)
```
Restore-AzSynapseSqlPool [-FromBackup] [-ResourceGroupName <String>] -WorkspaceName <String> -Name <String>
 -ResourceId <String> [-Tag <Hashtable>] [-StorageAccountType <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PemulihanFromBackupIdByByParentObjectParameterSet
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
PS C:\> # Transform Synapse SQL pool resource ID to SQL database ID because 
PS C:\> # currently the command only accepts the SQL databse ID. For example: /subscriptions/<SubscriptionId>/resourceGroups/<ResourceGroupName>/providers/Microsoft.Sql/servers/<WorkspaceName>/databases/<DatabaseName>
PS C:\> $pool = Get-AzSynapseSqlPool -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name ContosoSqlPool
PS C:\> $databaseId = $pool.Id -replace "Microsoft.Synapse", "Microsoft.Sql" `
PS C:\>     -replace "workspaces", "servers" `
PS C:\>     -replace "sqlPools", "databases"
PS C:\> 
PS C:\> # Get the latest restore point
PS C:\> $restorePoint = $pool | Get-AzSynapseSqlPoolRestorePoint | Select -Last 1
PS C:\> 
PS C:\> # Restore to same workspace with source SQL pool
PS C:\> $restoredPool = Restore-AzSynapseSqlPool -FromRestorePoint -RestorePoint $restorePoint.RestorePointCreationDate -TargetSqlPoolName ContosoRestoredSqlPool -ResourceGroupName $pool.ResourceGroupName -WorkspaceName $pool.WorkspaceName -ResourceId $databaseId -PerformanceLevel DW200c
```

Perintah ini membuat kumpulan SQL Analitik Azure Synapse dengan memanfaatkan titik pemulihan dari kumpulan SQL yang sudah ada untuk memulihkan atau menyalin dari status sebelumnya.

### Contoh 2
```powershell
PS C:\> # Transform Synapse SQL pool resource ID to SQL database ID because
PS C:\> # currently the command only accepts the SQL databse ID. For example: /subscriptions/<SubscriptionId>/resourceGroups/<ResourceGroupName>/providers/Microsoft.Sql/servers/<WorkspaceName>/recoverabledatabases/<DatabaseName>
PS C:\> $pool = Get-AzSynapseSqlPoolGeoBackup -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name ContosoSqlPool
PS C:\> $databaseId = $pool.Id -replace "Microsoft.Synapse", "Microsoft.Sql" `
PS C:\>     -replace "workspaces", "servers"
PS C:\> 
PS C:\> # Restore to same workspace with source SQL pool
PS C:\> $restoredPool = Restore-AzSynapseSqlPool -FromBackup -TargetSqlPoolName ContosoRestoredSqlPool -ResourceGroupName $pool.ResourceGroupName -WorkspaceName $pool.WorkspaceName -ResourceId $databaseId
```

Perintah ini membuat kumpulan SQL Analitik Azure Synapse yang dipulihkan dari cadangan kumpulan SQL.

### Contoh 3
```powershell
PS C:\> # Transform Synapse dropped SQL pool resource ID to SQL pool resource ID
PS C:\> $pool = Get-AzSynapseDroppedSqlPool -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name ContosoSqlPool
PS C:\> $poolId = $pool.Id.Split(",")[0]
PS C:\> $poolId = $poolId -replace "restorableDroppedSqlPools", "sqlPools"
PS C:\> 
PS C:\> # Restore to same workspace with source SQL pool
PS C:\> $restoredPool = Restore-AzSynapseSqlPool -FromDroppedSqlPool -DeletionDate $pool.DeletionDate -TargetSqlPoolName ContosoRestoredSqlPool -ResourceGroupName $pool.ResourceGroupName -WorkspaceName $pool.WorkspaceName -ResourceId $poolId
```

Perintah ini membuat kumpulan SQL Analitik Azure Synapse yang dipulihkan dari cadangan kumpulan SQL yang dihapus.

### Contoh 4
```powershell
PS C:\> # Transform Synapse SQL pool resource ID to SQL database ID because 
PS C:\> # currently the command only accepts the SQL databse ID. For example: /subscriptions/<SubscriptionId>/resourceGroups/<ResourceGroupName>/providers/Microsoft.Sql/servers/<WorkspaceName>/databases/<DatabaseName>
PS C:\> $pool = Get-AzSynapseSqlPool -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name ContosoSqlPool
PS C:\> $databaseId = $pool.Id -replace "Microsoft.Synapse", "Microsoft.Sql" `
PS C:\>     -replace "workspaces", "servers" `
PS C:\>     -replace "sqlPools", "databases"
PS C:\> 
PS C:\> # Get the latest restore point
PS C:\> $restorePoint = $pool | Get-AzSynapseSqlPoolRestorePoint | Select -Last 1
PS C:\> 
PS C:\> # Restore to same workspace with source SQL pool
PS C:\> $restoredPool = Restore-AzSynapseSqlPool -FromRestorePoint -RestorePoint $restorePoint.RestorePointCreationDate -TargetSqlPoolName ContosoRestoredSqlPool -ResourceGroupName $pool.ResourceGroupName -WorkspaceName $pool.WorkspaceName -ResourceId $databaseId -PerformanceLevel DW200c -Tag @{"tagName" = "tagValue"} -StorageAccountType LRS
```

Perintah ini membuat kumpulan SQL Analitik Azure Synapse dengan tipe akun penyimpanan dan tag tertentu dengan memanfaatkan titik pemulihan dari kumpulan SQL yang sudah ada untuk memulihkan atau menyalin dari status sebelumnya.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -PenghapusanDate
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
Menunjukkan untuk memulihkan dari cadangan terbaru kumpulan SQL apa pun dalam langganan ini.

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

### -Nama
Nama Synapse SQL pool.

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
Tingkat layanan SQL dan tingkat kinerja untuk ditetapkan ke kumpulan SQL.
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
ID sumber daya database untuk dipulihkan.

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
Jepretan layar waktu untuk memulihkan.

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
Tipe akun penyimpanan yang digunakan untuk menyimpan cadangan untuk kumpulan sql. Nilai yang memungkinkan meliputi: 'GRS', 'LRS'.

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

### -Nama Ruang Kerja
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
objek input ruang kerja, biasanya melewati saluran.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseSqlPool

## NOTES

## RELATED LINKS
