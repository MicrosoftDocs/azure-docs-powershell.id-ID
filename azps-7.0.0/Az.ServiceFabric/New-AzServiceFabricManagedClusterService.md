---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/new-azservicefabricmanagedclusterservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricManagedClusterService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricManagedClusterService.md
ms.openlocfilehash: 9f47c54e521944f4366feb6915832ea9888bd8a3
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136533605"
---
# New-AzServiceFabricManagedClusterService

## SYNOPSIS
Create new service fabric managed service under the specified application and cluster.

## SYNTAX

### Stateless-Singleton (Default)
```
New-AzServiceFabricManagedClusterService [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationName] <String> [-Name] <String> -Type <String> [-Stateless] -InstanceCount <Int32>
 [-MinInstanceCount <Int32>] [-MinInstancePercentage <Int32>] [-DefaultMoveCost <MoveCostEnum>]
 [-PlacementConstraint <String>] [-Metric <PSServiceMetric[]>] [-Correlation <PSServiceCorrelation[]>]
 [-ServicePackageActivationMode <ServicePackageActivationModeEnum>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-PartitionSchemeSingleton] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Stateless-UniformInt64Range
```
New-AzServiceFabricManagedClusterService [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationName] <String> [-Name] <String> -Type <String> [-Stateless] -InstanceCount <Int32>
 [-MinInstanceCount <Int32>] [-MinInstancePercentage <Int32>] [-DefaultMoveCost <MoveCostEnum>]
 [-PlacementConstraint <String>] [-Metric <PSServiceMetric[]>] [-Correlation <PSServiceCorrelation[]>]
 [-ServicePackageActivationMode <ServicePackageActivationModeEnum>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-PartitionSchemeUniformInt64] -PartitionCount <Int32> -LowKey <Int64> -HighKey <Int64>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateless-Named
```
New-AzServiceFabricManagedClusterService [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationName] <String> [-Name] <String> -Type <String> [-Stateless] -InstanceCount <Int32>
 [-MinInstanceCount <Int32>] [-MinInstancePercentage <Int32>] [-DefaultMoveCost <MoveCostEnum>]
 [-PlacementConstraint <String>] [-Metric <PSServiceMetric[]>] [-Correlation <PSServiceCorrelation[]>]
 [-ServicePackageActivationMode <ServicePackageActivationModeEnum>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-PartitionSchemeNamed] -PartitionName <String[]> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Stateful-Singleton
```
New-AzServiceFabricManagedClusterService [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationName] <String> [-Name] <String> -Type <String> [-Stateful] -TargetReplicaSetSize <Int32>
 -MinReplicaSetSize <Int32> [-HasPersistedState] [-ReplicaRestartWaitDuration <TimeSpan>]
 [-QuorumLossWaitDuration <TimeSpan>] [-StandByReplicaKeepDuration <TimeSpan>]
 [-ServicePlacementTimeLimit <TimeSpan>] [-DefaultMoveCost <MoveCostEnum>] [-PlacementConstraint <String>]
 [-Metric <PSServiceMetric[]>] [-Correlation <PSServiceCorrelation[]>]
 [-ServicePackageActivationMode <ServicePackageActivationModeEnum>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-PartitionSchemeSingleton] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Stateful-UniformInt64Range
```
New-AzServiceFabricManagedClusterService [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationName] <String> [-Name] <String> -Type <String> [-Stateful] -TargetReplicaSetSize <Int32>
 -MinReplicaSetSize <Int32> [-HasPersistedState] [-ReplicaRestartWaitDuration <TimeSpan>]
 [-QuorumLossWaitDuration <TimeSpan>] [-StandByReplicaKeepDuration <TimeSpan>]
 [-ServicePlacementTimeLimit <TimeSpan>] [-DefaultMoveCost <MoveCostEnum>] [-PlacementConstraint <String>]
 [-Metric <PSServiceMetric[]>] [-Correlation <PSServiceCorrelation[]>]
 [-ServicePackageActivationMode <ServicePackageActivationModeEnum>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-PartitionSchemeUniformInt64] -PartitionCount <Int32> -LowKey <Int64> -HighKey <Int64>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateful-Named
```
New-AzServiceFabricManagedClusterService [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationName] <String> [-Name] <String> -Type <String> [-Stateful] -TargetReplicaSetSize <Int32>
 -MinReplicaSetSize <Int32> [-HasPersistedState] [-ReplicaRestartWaitDuration <TimeSpan>]
 [-QuorumLossWaitDuration <TimeSpan>] [-StandByReplicaKeepDuration <TimeSpan>]
 [-ServicePlacementTimeLimit <TimeSpan>] [-DefaultMoveCost <MoveCostEnum>] [-PlacementConstraint <String>]
 [-Metric <PSServiceMetric[]>] [-Correlation <PSServiceCorrelation[]>]
 [-ServicePackageActivationMode <ServicePackageActivationModeEnum>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-PartitionSchemeNamed] -PartitionName <String[]> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini memungkinkan pembuatan layanan yang dikelola secara stateless atau stateful di bawah aplikasi yang ditentukan. Layanan harus keluar di manifes aplikasi dan tipenya harus sama dengan yang ada di manifes. Nama aplikasi harus merupakan prefiks nama layanan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> $serviceName = "testService1"
PS C:\> $serviceTypeName = "testStateless"
PS C:\> $statelessServiceMetric = New-Object -TypeName "Microsoft.Azure.Commands.ServiceFabric.Models.PSServiceMetric" -ArgumentList @("metric1", "Low", 4)
PS C:\> New-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName -Name $serviceName -Type $serviceTypeName -Stateless -InstanceCount -1 -PartitionSchemaSingleton -Metric @($statelessServiceMetric) -Verbose
```

Contoh ini akan membuat layanan terkelola tanpa status baru "testService1" dengan jumlah instans -1 (di semua node).

### Contoh 2
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> $serviceName = "testService2"
PS C:\> $serviceTypeName = "testStatefulType"
PS C:\> $partitionCount = 5
PS C:\> $partitionLowKey = 0
PS C:\> $partitionHighKey = 25
PS C:\> $statefulServiceMetric = New-Object -TypeName "Microsoft.Azure.Commands.ServiceFabric.Models.PSServiceMetric" -ArgumentList @("metric2", "Medium", 4, 2)
PS C:\> New-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName -Name $serviceName -Type $serviceTypeName -Stateful -TargetReplicaSetSize 5 -MinReplicaSetSize 3 -Metric @($statefulServiceMetric) -PartitionSchemeUniformInt64 -PartitionCount $partitionCount -LowKey $partitionLowKey -HighKey $partitionHighKey -Verbose
```

Contoh ini akan membuat layanan terkelola baru "testService2" dengan target 5 node.

### Contoh 3
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> $serviceName = "testService3"
PS C:\> $serviceName2 = "testService2"
PS C:\> $serviceTypeName = "testStateless"
PS C:\> $statefulService = Get-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName -Name $serviceName2
PS C:\> $statefulServiceCorrelation = New-Object -TypeName "Microsoft.Azure.Commands.ServiceFabric.Models.PSServiceCorrelation" -ArgumentList @("AlignedAffinity, $statefulService.Id)
PS C:\> New-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName -Name $serviceName -Type $serviceTypeName -Stateless -InstanceCount 3 -PartitionSchemaSingleton -Correlation @($statefulServiceCorrelation) -Verbose
```

Contoh ini akan membuat layanan terkelola tanpa status baru "testService3".

## PARAMETERS

### -ApplicationName
Tentukan nama dari aplikasi yang dikelola.

```yaml
Type: System.String
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: Stateful-Singleton, Stateful-UniformInt64Range, Stateful-Named
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HighKey
Tentukan batas atas rentang kunci partisi.

```yaml
Type: System.Int64
Parameter Sets: Stateless-UniformInt64Range, Stateful-UniformInt64Range
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceCount
Menentukan jumlah instans untuk layanan yang dikelola

```yaml
Type: System.Int32
Parameter Sets: Stateless-Singleton, Stateless-UniformInt64Range, Stateless-Named
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LowKey
Tentukan batas bawah rentang kunci partisi.

```yaml
Type: System.Int64
Parameter Sets: Stateless-UniformInt64Range, Stateful-UniformInt64Range
Aliases:

Required: True
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
Parameter Sets: Stateless-Singleton, Stateless-UniformInt64Range, Stateless-Named
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
Parameter Sets: Stateless-Singleton, Stateless-UniformInt64Range, Stateless-Named
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
Parameter Sets: Stateful-Singleton, Stateful-UniformInt64Range, Stateful-Named
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Tentukan nama layanan terkelola.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionCount
Menentukan jumlah partisi.

```yaml
Type: System.Int32
Parameter Sets: Stateless-UniformInt64Range, Stateful-UniformInt64Range
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionName
Menunjukkan bahwa layanan menggunakan skema partisi bernama. Layanan yang menggunakan model ini biasanya berisi data yang dapat di bucketed, di dalam sebuah kumpulan terikat. Beberapa contoh umum bidang data yang digunakan sebagai kunci partisi bernama akan menjadi kawasan, kode pos, grup pelanggan, atau batas bisnis lainnya.

```yaml
Type: System.String[]
Parameter Sets: Stateless-Named, Stateful-Named
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionSchemeNamed
Menunjukkan bahwa layanan menggunakan skema partisi bernama.
Layanan yang menggunakan model ini biasanya berisi data yang dapat di bucketed, di dalam sebuah kumpulan terikat.
Beberapa contoh umum bidang data yang digunakan sebagai kunci partisi bernama akan menjadi kawasan, kode pos, grup pelanggan, atau batas bisnis lainnya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stateless-Named, Stateful-Named
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionSchemeSingleton
Menunjukkan bahwa layanan menggunakan skema partisi tunggal.
Partisi tunggal biasanya digunakan saat layanan tidak memerlukan perutean tambahan apa pun.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stateless-Singleton, Stateful-Singleton
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartitionSchemeUniformInt64
Menunjukkan bahwa layanan menggunakan skema partisi UniformInt64.
Ini berarti bahwa setiap partisi memiliki rentang tombol int64.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stateless-UniformInt64Range, Stateful-UniformInt64Range
Aliases:

Required: True
Position: Named
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
Parameter Sets: Stateful-Singleton, Stateful-UniformInt64Range, Stateful-Named
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
Parameter Sets: Stateful-Singleton, Stateful-UniformInt64Range, Stateful-Named
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
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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
Parameter Sets: Stateful-Singleton, Stateful-UniformInt64Range, Stateful-Named
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
Parameter Sets: Stateful-Singleton, Stateful-UniformInt64Range, Stateful-Named
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
Parameter Sets: Stateful-Singleton, Stateful-UniformInt64Range, Stateful-Named
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
Parameter Sets: Stateless-Singleton, Stateless-UniformInt64Range, Stateless-Named
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
Parameter Sets: Stateful-Singleton, Stateful-UniformInt64Range, Stateful-Named
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Tentukan nama jenis layanan dari aplikasi yang dikelola, harus ada di manifes aplikasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServiceType

Required: True
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedService

## CATATAN

## RELATED LINKS
