---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/set-azservicefabricmanagedclusterservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterService.md
ms.openlocfilehash: df5e302ddc2098234a565df4d522274b793cfd9e
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139968441"
---
# Set-AzServiceFabricManagedClusterService

## SYNOPSIS
Memperbarui layanan yang dikelola dari kluster. Hanya mendukung layanan ARM yang disebarkan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.servicefabric/set-azservicefabricmanagedclusterservice) untuk informasi terkini.

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
Cmdlet ini memperbarui formulir layanan terkelola kluster.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> $serviceName = "testService1"
PS C:\> Set-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName -Name $serviceName -Stateful -TargetReplicaSetSize 3 MinReplicaSetSize 5 -Verbose
```

Contoh ini akan memperbarui layanan terkelola "testService1".

### Contoh 2
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> $serviceName = "testService1"
PS C:\> $minInstancePercentage = 20
PS C:\> $minInstanceCount = 2
PS C:\> $statelessServiceMetric = New-Object -TypeName "Microsoft.Azure.Commands.ServiceFabric.Models.PSServiceMetric" -ArgumentList @("metric1", "Low", 4)
PS C:\> $service = Get-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName
PS C:\> $service | Set-AzServiceFabricManagedClusterService -Stateless -Metric @($statelessServiceMetric) -MinInstanceCount $minInstanceCount -MinInstancePercentage $minInstancePercentage -Verbose
```

Contoh ini akan menghapus layanan terkelola testService1".

### Contoh 3
```powershell
PS C:\> $standByReplicaKeepDuration = "00:11:00"
PS C:\> $servicePlacementTimeLimit = "00:11:00"
PS C:\> $resourceId = "/subscriptions/13ad2c84-84fa-4798-ad71-e70c07af873f/resourcegroups/testRG/providers/Microsoft.ServiceFabric/managedClusters/testCluster/applications/testApp/services/testService"
PS C:\> Set-AzServiceFabricManagedClusterService -ResourceId $resourceId -StandByReplicaKeepDuration $standByReplicaKeepDuration -ServicePlacementTimeLimit $servicePlacementTimeLimit -Verbose
```

Contoh ini akan menghapus detail layanan terkelola dengan ID Sumber Daya ARM yang ditentukan.

## PARAMETERS

### -ApplicationName
Tentukan nama dari aplikasi yang dikelola.

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
Jalankan cmdlet di latar belakang dan kembalikan Pekerjaan untuk melacak kemajuan.

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

### -Korelasi
Menentukan batasan penempatan layanan terkelola sebagai string.

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
Tentukan biaya default untuk pemindahan.
Biaya yang lebih tinggi semakin kecil kemungkinan Pengelola Sumber Daya Kluster akan memindahkan replika saat mencoba menyeimbangkan kluster tersebut

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

### -Force
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
Menentukan ukuran rangkaian replika target untuk layanan terkelola

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
Sumber daya layanan yang dikelola.

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
Menentukan jumlah instans untuk layanan yang dikelola

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

### -Metric
Menentukan batasan penempatan layanan terkelola sebagai string.

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
Menentukan jumlah instans minimum untuk layanan terkelola

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
Menentukan persentase contoh minimum untuk layanan terkelola

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
Menentukan ukuran rangkaian replika menit untuk layanan terkelola

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
Menentukan batasan penempatan layanan terkelola sebagai string.

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

### -EkslosLossWaitDuration
Tentukan durasi tunggu kerugian jangka waktu untuk layanan yang dikelola.
Durasi yang dinyatakan dalam format ISO 8601 'hh:mm:ss'

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
Durasi yang dinyatakan dalam format ISO 8601 'hh:mm:ss'

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
Tentukan biaya default untuk pemindahan.
Biaya yang lebih tinggi semakin kecil kemungkinan Pengelola Sumber Daya Kluster akan memindahkan replika saat mencoba menyeimbangkan kluster tersebut

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
Tentukan batas waktu penempatan layanan untuk layanan terkelola.
Durasi yang dinyatakan dalam format ISO 8601 'hh:mm:ss'

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
Tentukan durasi replika untuk layanan terkelola.
Durasi yang dinyatakan dalam format ISO 8601 'hh:mm:ss'

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
Gunakan untuk layanan yang jelas

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
Menentukan ukuran rangkaian replika target untuk layanan terkelola

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

### System.String

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedService

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedService

## CATATAN

## RELATED LINKS
