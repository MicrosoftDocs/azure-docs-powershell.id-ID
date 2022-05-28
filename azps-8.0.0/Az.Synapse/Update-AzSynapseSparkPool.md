---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/update-azsynapsesparkpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Update-AzSynapseSparkPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Update-AzSynapseSparkPool.md
ms.openlocfilehash: 15640ef367dbb87aace2b0952795de371bfa11ec
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145523470"
---
# Update-AzSynapseSparkPool

## SYNOPSIS
Memperbarui kumpulan Apache Spark di Azure Synapse Analytics.

## SYNTAX

### SetByNameParameterSet (Default)
```
Update-AzSynapseSparkPool [-ResourceGroupName <String>] -WorkspaceName <String> -Name <String>
 [-Tag <Hashtable>] [-EnableAutoScale <Boolean>] [-AutoScaleMinNodeCount <Int32>]
 [-AutoScaleMaxNodeCount <Int32>] [-EnableAutoPause <Boolean>] [-AutoPauseDelayInMinute <Int32>]
 [-NodeCount <Int32>] [-NodeSize <String>] [-SparkVersion <String>] [-LibraryRequirementsFilePath <String>]
 [-SparkConfigFilePath <String>] [-PackageAction <PackageActionType>]
 [-Package <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Synapse.Models.WorkspacePackages.PSSynapseWorkspacePackage]>]
 [-ForceApplySetting] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByParentObjectParameterSet
```
Update-AzSynapseSparkPool -Name <String> -WorkspaceObject <PSSynapseWorkspace> [-Tag <Hashtable>]
 [-EnableAutoScale <Boolean>] [-AutoScaleMinNodeCount <Int32>] [-AutoScaleMaxNodeCount <Int32>]
 [-EnableAutoPause <Boolean>] [-AutoPauseDelayInMinute <Int32>] [-NodeCount <Int32>] [-NodeSize <String>]
 [-SparkVersion <String>] [-LibraryRequirementsFilePath <String>] [-SparkConfigFilePath <String>]
 [-PackageAction <PackageActionType>]
 [-Package <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Synapse.Models.WorkspacePackages.PSSynapseWorkspacePackage]>]
 [-ForceApplySetting] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByInputObjectParameterSet
```
Update-AzSynapseSparkPool -InputObject <PSSynapseSparkPool> [-Tag <Hashtable>] [-EnableAutoScale <Boolean>]
 [-AutoScaleMinNodeCount <Int32>] [-AutoScaleMaxNodeCount <Int32>] [-EnableAutoPause <Boolean>]
 [-AutoPauseDelayInMinute <Int32>] [-NodeCount <Int32>] [-NodeSize <String>] [-SparkVersion <String>]
 [-LibraryRequirementsFilePath <String>] [-SparkConfigFilePath <String>] [-PackageAction <PackageActionType>]
 [-Package <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Synapse.Models.WorkspacePackages.PSSynapseWorkspacePackage]>]
 [-ForceApplySetting] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByResourceIdParameterSet
```
Update-AzSynapseSparkPool -ResourceId <String> [-Tag <Hashtable>] [-EnableAutoScale <Boolean>]
 [-AutoScaleMinNodeCount <Int32>] [-AutoScaleMaxNodeCount <Int32>] [-EnableAutoPause <Boolean>]
 [-AutoPauseDelayInMinute <Int32>] [-NodeCount <Int32>] [-NodeSize <String>] [-SparkVersion <String>]
 [-LibraryRequirementsFilePath <String>] [-SparkConfigFilePath <String>] [-PackageAction <PackageActionType>]
 [-Package <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Synapse.Models.WorkspacePackages.PSSynapseWorkspacePackage]>]
 [-ForceApplySetting] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzSynapseSparkPool** memperbarui kumpulan Apache Spark di Azure Synapse Analytics.

## EXAMPLES

### Contoh 1
```powershell
Update-AzSynapseSparkPool -WorkspaceName ContosoWorkspace -Name ContosoSparkPool -Tag @{"key" = "value"} -NodeCount 5 -NodeSize Medium
```

Perintah ini memperbarui kumpulan Apache Spark di Azure Synapse Analytics.

### Contoh 2
```powershell
$pool = Get-AzSynapseSparkPool -WorkspaceName ContosoWorkspace -Name ContosoSparkPool
$pool | Update-AzSynapseSparkPool -Tag @{"key" = "value1"}
```

Perintah ini memperbarui kumpulan Apache Spark di Azure Synapse Analytics melalui alur.

### Contoh: 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Update-AzSynapseSparkPool -Name ContosoSparkPool -Tag @{"key" = "value2"}
```

Perintah ini memperbarui kumpulan Apache Spark di Azure Synapse Analytics melalui alur.

### Contoh 4
```powershell
Update-AzSynapseSparkPool -ResourceId /subscriptions/21686af7-58ec-4f4d-9c68-f431f4db4edd/resourceGroups/ContosoResourceGroup/providers/Microsoft.Synapse/workspaces/ContosoWorkspace/bigDataPools/ContosoSparkPool -Tag @{"key" = "value3"}
```

Perintah ini memperbarui kumpulan Apache Spark di Azure Synapse Analytics dengan ID sumber daya.

### Contoh 5
```powershell
Update-AzSynapseSparkPool -WorkspaceName ContosoWorkspace -Name ContosoSparkPool -EnableAutoScale $true -AutoScaleMinNodeCount 3 -AutoScaleMaxNodeCount 7
```

Perintah ini memungkinkan penskalaan otomatis untuk kumpulan Apache Spark di Azure Synapse Analytics.

### Contoh 6
```powershell
Update-AzSynapseSparkPool -WorkspaceName ContosoWorkspace -Name ContosoSparkPool -EnableAutoScale $false
```

Perintah ini menonaktifkan skala otomatis untuk kumpulan Apache Spark di Azure Synapse Analytics.

### Contoh 7
```powershell
Update-AzSynapseSparkPool -WorkspaceName ContosoWorkspace -Name ContosoSparkPool -EnableAutoPause $true -AutoPauseDelayInMinute 15
```

Perintah ini memungkinkan jeda otomatis untuk kumpulan Apache Spark di Azure Synapse Analytics.

### Contoh 8
```powershell
Update-AzSynapseSparkPool -WorkspaceName ContosoWorkspace -Name ContosoSparkPool -EnableAutoPause $false
```

Perintah ini menonaktifkan jeda otomatis untuk kumpulan Apache Spark di Azure Synapse Analytics.

### Contoh 9
```powershell
$packages = Get-AzSynapseWorkspacePackage -WorkspaceName ContosoWorkspace
Update-AzSynapseSparkPool -WorkspaceName ContosoWorkspace -Name ContosoSparkPool -PackageAction Add -Package $packages
```

Perintah pertama mengambil paket ruang kerja. Perintah kedua menautkan paket ruang kerja ini ke kumpulan Apache Spark di Azure Synapse Analytics.

### Contoh 10
```powershell
$package = Get-AzSynapseWorkspacePackage -WorkspaceName ContosoWorkspace -Name ContosoPackage
Update-AzSynapseSparkPool -WorkspaceName ContosoWorkspace -Name ContosoSparkPool -PackageAction Remove -Package $package
```

Perintah pertama mengambil paket ruang kerja bernama ContosoPackage. Perintah kedua menghapus paket ruang kerja dari kumpulan Apache Spark di Azure Synapse Analytics.

### Contoh 11
```powershell
$pool = Get-AzSynapseSparkPool -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name ContosoSparkPool
$pool | Update-AzSynapseSparkPool -PackageAction Remove -Package $pool.WorkspacePackages
```

Perintah pertama mengambil kumpulan Apache Spark di Azure Synapse Analytics. Perintah kedua menghapus semua paket ruang kerja yang ditautkan ke kumpulan Apache Spark tersebut.

### Contoh 12
```powershell
Update-AzSynapseSparkPool -WorkspaceName ContosoWorkspace -Name ContosoSparkPool -Tag @{"key" = "value"} -NodeCount 5 -NodeSize Medium -SparkConfigFilePath "c:\sparkconfig.txt"
```

Perintah ini memperbarui kumpulan Apache Spark di Azure Synapse Analytics dan mengunggah file konfigurasi spark untuk kumpulan spark.

### Contoh 13
```powershell
Update-AzSynapseSparkPool -WorkspaceName ContosoWorkspace -Name ContosoSparkPool -NodeSize small -ForceApplySetting
```

Perintah ini memperbarui kumpulan Apache Spark di Azure Synapse Analytics, mengatur NodeSize ke kecil untuk kumpulan spark dan paksa menghentikan pekerjaan yang sedang berjalan di kumpulan Spark untuk menerapkan pengaturan baru ini.

### Contoh 14
```powershell
$pool = Get-AzSynapseSparkPool -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name ContosoSparkPool
$pool | Update-AzSynapseSparkPool -PackageAction Remove -Package $pool.WorkspacePackages -ForceApplySetting
```

Perintah pertama mengambil kumpulan Apache Spark di Azure Synapse Analytics. Perintah kedua menghapus semua paket ruang kerja yang ditautkan ke kumpulan Apache Spark tersebut dan memaksa menghentikan pekerjaan yang sedang berjalan di kumpulan Spark untuk menerapkan pengaturan baru ini.

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

### -AutoPauseDelayInMinute
Jumlah menit diam. Parameter ini dapat ditentukan saat Jeda otomatis diaktifkan. Nilai defaultnya adalah [15] jika tidak ditentukan secara manual.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoScaleMaxNodeCount
Jumlah maksimum simpul yang akan dialokasikan dalam kumpulan Spark yang ditentukan.
Parameter ini harus ditentukan saat Skala otomatis diaktifkan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoScaleMinNodeCount
Jumlah minimum simpul yang akan dialokasikan dalam kumpulan Spark yang ditentukan.
Parameter ini harus ditentukan saat Skala otomatis diaktifkan.

```yaml
Type: System.Int32
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

### -EnableAutoPause
Menunjukkan apakah Jeda otomatis harus diaktifkan.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAutoScale
Menunjukkan apakah Skala otomatis harus diaktifkan

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceApplySetting
Apakah akan menghentikan pekerjaan yang sedang berjalan di kumpulan Big Data.

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

### -InputObject
Objek input kumpulan Spark, biasanya melewati alur.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseSparkPool
Parameter Sets: SetByInputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LibraryRequirementsFilePath
File konfigurasi lingkungan (output "PEMBekuAN PIP").

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

### -Name
Nama kumpulan Synapse Spark.

```yaml
Type: System.String
Parameter Sets: SetByNameParameterSet, SetByParentObjectParameterSet
Aliases: SparkPoolName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeCount
Jumlah simpul yang akan dialokasikan di kumpulan Spark yang ditentukan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeSize
Jumlah inti dan memori yang akan digunakan untuk simpul yang dialokasikan dalam kumpulan Spark yang ditentukan.
Parameter ini harus ditentukan ketika Skala otomatis dinonaktifkan

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Small, Medium, Large

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paket
Paket ruang kerja.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Synapse.Models.WorkspacePackages.PSSynapseWorkspacePackage]
Parameter Sets: (All)
Aliases: WorkspacePackage

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageAction
Tindakan paket harus ditentukan saat Anda menambahkan atau menghapus paket ruang kerja dari kumpulan Apache Spark.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.SynapseConstants+PackageActionType
Parameter Sets: (All)
Aliases:
Accepted values: Add, Remove

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: SetByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya kumpulan Synapse Spark.

```yaml
Type: System.String
Parameter Sets: SetByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SparkConfigFilePath
File konfigurasi properti kumpulan Spark.

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

### -SparkVersion
Versi Apache Spark.
Nilai yang diizinkan: 2,4

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
Parameter Sets: SetByNameParameterSet
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
Parameter Sets: SetByParentObjectParameterSet
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

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseSparkPool

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseSparkPool

## NOTES

## RELATED LINKS
