---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/restore-azsynapsesqlpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Restore-AzSynapseSqlPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Restore-AzSynapseSqlPool.md
ms.openlocfilehash: 0a4cc5c052722a740ed8bcbb1faa58d016311fe3
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140094815"
---
# Restore-AzSynapseSqlPool

## SYNOPSIS
Memulihkan Analitik Synapse dalam SQL sama.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.synapse/restore-azsynapsesqlpool) untuk informasi terkini.

## SYNTAX

### RestoreFromBackupIdByNameParameterSet (Default)
```
Restore-AzSynapseSqlPool [-FromBackup] [-ResourceGroupName <String>] -WorkspaceName <String> -Name <String>
 -ResourceId <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RestoreFromBackupIdByParentObjectParameterSet
```
Restore-AzSynapseSqlPool [-FromBackup] -WorkspaceObject <PSSynapseWorkspace> -Name <String>
 -ResourceId <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RestoreFromRestorePointIdByNameParameterSet
```
Restore-AzSynapseSqlPool [-FromRestorePoint] [-ResourceGroupName <String>] -WorkspaceName <String>
 -Name <String> -PerformanceLevel <String> -ResourceId <String> -RestorePoint <DateTime> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PulihkanFromRestorePointIdByParentObjectParameterSet
```
Restore-AzSynapseSqlPool [-FromRestorePoint] -WorkspaceObject <PSSynapseWorkspace> -Name <String>
 -PerformanceLevel <String> -ResourceId <String> -RestorePoint <DateTime> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RestoreFromPoolppedSqlPoolByNameParameterSet
```
Restore-AzSynapseSqlPool [-FromDroppedSqlPool] [-ResourceGroupName <String>] -WorkspaceName <String>
 -Name <String> -ResourceId <String> -DeletionDate <DateTime> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RestoreFromPoolPpedSqlPoolByParentObjectParameterSet
```
Restore-AzSynapseSqlPool [-FromDroppedSqlPool] -WorkspaceObject <PSSynapseWorkspace> -Name <String>
 -ResourceId <String> -DeletionDate <DateTime> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Restore-AzSynapseSqlPool** memulihkan grup SQL Analitik Azure Synapse dari cadangan geo berlebihan, cadangan pool SQL yang dihapus atau titik pemulihan dari setiap SQL lokal.
Pool SQL yang dipulihkan dibuat sebagai sebuah SQL baru.

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

Perintah ini membuat azure Synapse Analytics SQL pool dengan memaksimalkan titik pemulihan dari semua SQL lokal yang sudah ada untuk memulihkan atau menyalin dari status sebelumnya.

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

Perintah ini membuat analitik Azure Synapse SQL lokal yang dipulihkan dari SQL cadangan pool.

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

Perintah ini membuat analitik Azure Synapse SQL baru yang dipulihkan dari pencadangan SQL otomatis yang dihapus.

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
Tanggal penghapusan program Azure Synaspe SQL Database mengambil cadangan, dengan presisi milidetik (misalnya 2016-02-23T00:21:22.847Z)

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
Menunjukkan untuk memulihkan dari cadangan terbaru semua pengguna SQL anda dalam langganan ini.

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

### -FromIdrppedSqlPool
Menunjukkan untuk memanfaatkan titik pemulihan dari setiap SQL lokal dalam langganan ini untuk memulihkan atau menyalin dari status sebelumnya.

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
Menunjukkan untuk memanfaatkan titik pemulihan dari setiap SQL lokal dalam langganan ini untuk memulihkan atau menyalin dari status sebelumnya.

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
Nama SQL Tim.

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
Tingkat SQL Layanan tingkat dan tingkat kinerja untuk ditetapkan ke SQL baru.
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
Waktu snapshot untuk dipulihkan.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseSqlPool

## CATATAN

## RELATED LINKS
