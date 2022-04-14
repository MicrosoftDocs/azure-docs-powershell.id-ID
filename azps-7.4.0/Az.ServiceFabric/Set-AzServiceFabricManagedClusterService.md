---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/set-azservicefabricmanagedclusterservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterService.md
ms.openlocfilehash: 911d7115490e2ca307bc8019b3d5cb87d29334c2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141990131"
---
# Set-AzServiceFabricManagedClusterService

## SYNOPSIS
Memperbarui layanan terkelola dari kluster. Hanya mendukung layanan arm yang disebarkan.

## SYNTAX

### Stateless-ByResourceGroup (Default)
```
Set-AzServiceFabricManagedClusterService [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationName] <String> [-Name] <String> [-Stateless] [-InstanceCount <Int32>] [-MinInstanceCount <Int32>]
 [-MinInstancePercentage <Int32>] [-DefaultMoveCost <MoveCostEnum>] [-PlacementConstraint <String>]
 [-Metric <PSServiceMetric[]>] [-Correlation <PSServiceCorrelation[]>]
 [-ServicePackageActivationMode <ServicePackageActivationModeEnum>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateful-ByResourceGroup
```
Set-AzServiceFabricManagedClusterService [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationName] <String> [-Name] <String> [-Stateful] [-TargetReplicaSetSize <Int32>]
 [-MinReplicaSetSize <Int32>] [-HasPersistedState] [-ReplicaRestartWaitDuration <TimeSpan>]
 [-QuorumLossWaitDuration <TimeSpan>] [-StandByReplicaKeepDuration <TimeSpan>]
 [-ServicePlacementTimeLimit <TimeSpan>] [-DefaultMoveCost <MoveCostEnum>] [-PlacementConstraint <String>]
 [-Metric <PSServiceMetric[]>] [-Correlation <PSServiceCorrelation[]>]
 [-ServicePackageActivationMode <ServicePackageActivationModeEnum>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateless-ByResourceId
```
Set-AzServiceFabricManagedClusterService -ResourceId <String> [-Stateless] [-InstanceCount <Int32>]
 [-MinInstanceCount <Int32>] [-MinInstancePercentage <Int32>] [-DefaultMoveCost <MoveCostEnum>]
 [-PlacementConstraint <String>] [-Metric <PSServiceMetric[]>] [-Correlation <PSServiceCorrelation[]>]
 [-ServicePackageActivationMode <ServicePackageActivationModeEnum>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateful-ByResourceId
```
Set-AzServiceFabricManagedClusterService -ResourceId <String> [-Stateful] [-TargetReplicaSetSize <Int32>]
 [-MinReplicaSetSize <Int32>] [-HasPersistedState] [-ReplicaRestartWaitDuration <TimeSpan>]
 [-QuorumLossWaitDuration <TimeSpan>] [-StandByReplicaKeepDuration <TimeSpan>]
 [-ServicePlacementTimeLimit <TimeSpan>] [-DefaultMoveCost <MoveCostEnum>] [-PlacementConstraint <String>]
 [-Metric <PSServiceMetric[]>] [-Correlation <PSServiceCorrelation[]>]
 [-ServicePackageActivationMode <ServicePackageActivationModeEnum>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateless-ByInputObject
```
Set-AzServiceFabricManagedClusterService -InputObject <PSManagedService> [-Stateless] [-InstanceCount <Int32>]
 [-MinInstanceCount <Int32>] [-MinInstancePercentage <Int32>] [-DefaultMoveCost <MoveCostEnum>]
 [-PlacementConstraint <String>] [-Metric <PSServiceMetric[]>] [-Correlation <PSServiceCorrelation[]>]
 [-ServicePackageActivationMode <ServicePackageActivationModeEnum>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateful-ByInputObject
```
Set-AzServiceFabricManagedClusterService -InputObject <PSManagedService> [-Stateful]
 [-TargetReplicaSetSize <Int32>] [-MinReplicaSetSize <Int32>] [-HasPersistedState]
 [-ReplicaRestartWaitDuration <TimeSpan>] [-QuorumLossWaitDuration <TimeSpan>]
 [-StandByReplicaKeepDuration <TimeSpan>] [-ServicePlacementTimeLimit <TimeSpan>]
 [-DefaultMoveCost <MoveCostEnum>] [-PlacementConstraint <String>] [-Metric <PSServiceMetric[]>]
 [-Correlation <PSServiceCorrelation[]>] [-ServicePackageActivationMode <ServicePackageActivationModeEnum>]
 [-Tag <Hashtable>] [-Force] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini memperbarui layanan terkelola membentuk kluster.

## EXAMPLES

### Contoh 1
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appName = "testApp"
$serviceName = "testService1"
Set-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName -Name $serviceName -Stateful -TargetReplicaSetSize 3 MinReplicaSetSize 5 -Verbose
```

Contoh ini akan memperbarui layanan terkelola "testService1".

### Contoh 2
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appName = "testApp"
$serviceName = "testService1"
$minInstancePercentage = 20
$minInstanceCount = 2
$statelessServiceMetric = New-Object -TypeName "Microsoft.Azure.Commands.ServiceFabric.Models.PSServiceMetric" -ArgumentList @("metric1", "Low", 4)
$service = Get-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName
$service | Set-AzServiceFabricManagedClusterService -Stateless -Metric @($statelessServiceMetric) -MinInstanceCount $minInstanceCount -MinInstancePercentage $minInstancePercentage -Verbose
```

Contoh ini akan menghapus uji layanan terkelolaService1".

### Contoh 3
```powershell
$standByReplicaKeepDuration = "00:11:00"
$servicePlacementTimeLimit = "00:11:00"
$resourceId = "/subscriptions/13ad2c84-84fa-4798-ad71-e70c07af873f/resourcegroups/testRG/providers/Microsoft.ServiceFabric/managedClusters/testCluster/applications/testApp/services/testService"
Set-AzServiceFabricManagedClusterService -ResourceId $resourceId -StandByReplicaKeepDuration $standByReplicaKeepDuration -ServicePlacementTimeLimit $servicePlacementTimeLimit -Verbose
```

Contoh ini akan menghapus detail layanan terkelola dengan ID Sumber Daya ARM yang ditentukan.

## PARAMETERS

### -ApplicationName
Tentukan nama aplikasi yang dikelola.

```yaml
Type: System.String
Parameter Sets: Stateless-ByResourceGroup, Stateful-ByResourceGroup
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Jalankan cmdlet di latar belakang dan kembalikan Job untuk melacak kemajuan.

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

### -ClusterName
Tentukan nama kluster.

```yaml
Type: System.String
Parameter Sets: Stateless-ByResourceGroup, Stateful-ByResourceGroup
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Korlasi
Tentukan batasan penempatan layanan terkelola, sebagai string.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.PSServiceCorrelation[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultMoveCost
Tentukan biaya default untuk perpindahan.
Biaya yang lebih tinggi memperkecil kemungkinan cluster Resource Manager akan memindahkan replika ketika mencoba menyeimbangkan kluster

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.MoveCostEnum
Parameter Sets: (All)
Aliases:
Accepted values: Zero, Low, Medium, High

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

### -Paksa
Lanjutkan tanpa perintah

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

### -HasPersistedState
Menentukan ukuran kumpulan replika target untuk layanan terkelola

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stateful-ByResourceGroup, Stateful-ByResourceId, Stateful-ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Sumber daya layanan terkelola.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedService
Parameter Sets: Stateless-ByInputObject, Stateful-ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InstanceCount
Menentukan hitungan instans untuk layanan terkelola

```yaml
Type: System.Int32
Parameter Sets: Stateless-ByResourceGroup, Stateless-ByResourceId, Stateless-ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metrik
Tentukan batasan penempatan layanan terkelola, sebagai string.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.PSServiceMetric[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinInstanceCount
Menentukan hitungan instans minimum untuk layanan yang dikelola

```yaml
Type: System.Int32
Parameter Sets: Stateless-ByResourceGroup, Stateless-ByResourceId, Stateless-ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinInstancePercentage
Menentukan persentase instans minimum untuk layanan yang dikelola

```yaml
Type: System.Int32
Parameter Sets: Stateless-ByResourceGroup, Stateless-ByResourceId, Stateless-ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinReplicaSetSize
Menentukan ukuran kumpulan replika min untuk layanan yang dikelola

```yaml
Type: System.Int32
Parameter Sets: Stateful-ByResourceGroup, Stateful-ByResourceId, Stateful-ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Tentukan nama layanan terkelola.

```yaml
Type: System.String
Parameter Sets: Stateless-ByResourceGroup, Stateful-ByResourceGroup
Aliases: ServiceName

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlacementConstraint
Tentukan batasan penempatan layanan terkelola, sebagai string.

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

### -QuorumLossWaitDuration
Tentukan durasi tunggu kehilangan kuorum untuk layanan yang dikelola.
Durasi dinyatakan dalam format ISO 8601 'hh:mm:ss'

```yaml
Type: System.TimeSpan
Parameter Sets: Stateful-ByResourceGroup, Stateful-ByResourceId, Stateful-ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaRestartWaitDuration
Tentukan durasi tunggu mulai ulang replika untuk layanan yang dikelola.
Durasi dinyatakan dalam format ISO 8601 'hh:mm:ss'

```yaml
Type: System.TimeSpan
Parameter Sets: Stateful-ByResourceGroup, Stateful-ByResourceId, Stateful-ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Tentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Stateless-ByResourceGroup, Stateful-ByResourceGroup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Arm ResourceId dari layanan yang dikelola.

```yaml
Type: System.String
Parameter Sets: Stateless-ByResourceId, Stateful-ByResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServicePackageActivationMode
Tentukan biaya default untuk perpindahan.
Biaya yang lebih tinggi memperkecil kemungkinan cluster Resource Manager akan memindahkan replika ketika mencoba menyeimbangkan kluster

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.ServicePackageActivationModeEnum
Parameter Sets: (All)
Aliases:
Accepted values: SharedProcess, ExclusiveProcess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicePlacementTimeLimit
Tentukan batas waktu penempatan layanan untuk layanan yang dikelola.
Durasi dinyatakan dalam format ISO 8601 'hh:mm:ss'

```yaml
Type: System.TimeSpan
Parameter Sets: Stateful-ByResourceGroup, Stateful-ByResourceId, Stateful-ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StandByReplicaKeepDuration
Tentukan durasi tribun demi replika untuk layanan yang dikelola.
Durasi dinyatakan dalam format ISO 8601 'hh:mm:ss'

```yaml
Type: System.TimeSpan
Parameter Sets: Stateful-ByResourceGroup, Stateful-ByResourceId, Stateful-ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stateful
Gunakan untuk layanan bernegara

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stateful-ByResourceGroup, Stateful-ByResourceId, Stateful-ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stateless
Gunakan untuk layanan tanpa status

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stateless-ByResourceGroup, Stateless-ByResourceId, Stateless-ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tentukan tag sebagai pasangan kunci/nilai.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetReplicaSetSize
Menentukan ukuran kumpulan replika target untuk layanan terkelola

```yaml
Type: System.Int32
Parameter Sets: Stateful-ByResourceGroup, Stateful-ByResourceId, Stateful-ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### System.String

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedService

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedService

## CATATAN

## RELATED LINKS
