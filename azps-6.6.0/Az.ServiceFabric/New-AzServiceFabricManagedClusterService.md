---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/new-azservicefabricmanagedclusterservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricManagedClusterService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricManagedClusterService.md
ms.openlocfilehash: 25edbeedf27d79c9e6c47b274dc01c70c45312b6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142299481"
---
# New-AzServiceFabricManagedClusterService

## SYNOPSIS
Buat servis servis baru yang dikelola kain di bawah aplikasi dan kluster yang ditentukan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.servicefabric/new-azservicefabricmanagedclusterservice) untuk informasi terbaru.

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
Cmdlet ini memungkinkan untuk membuat layanan yang terkelola tanpa status atau stateful di bawah aplikasi yang ditentukan. Layanan harus keluar dalam manifes aplikasi dan tipenya harus sama dengan yang ada di manifes. Nama aplikasi harus berupa prefiks nama layanan.

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

Contoh ini akan membuat layanan terkelola tanpa status baru "testService1" dengan hitungan instans -1 (di semua node).

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

Contoh ini akan membuat "testService2" layanan terkelola status baru dengan target 5 node.

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
Tentukan nama aplikasi yang dikelola.

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
Parameter Sets: (All)
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
Menentukan hitungan instans untuk layanan terkelola

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
Parameter Sets: Stateless-Singleton, Stateless-UniformInt64Range, Stateless-Named
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
Parameter Sets: Stateless-Singleton, Stateless-UniformInt64Range, Stateless-Named
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
Tentukan jumlah partisi.

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
Menunjukkan bahwa layanan menggunakan skema partisi bernama. Layanan yang menggunakan model ini biasanya memiliki data yang dapat di-bucket, dalam rangkaian terikat. Beberapa contoh umum bidang data yang digunakan sebagai kunci partisi bernama adalah kawasan, kode pos, grup pelanggan, atau batas bisnis lainnya.

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
Layanan yang menggunakan model ini biasanya memiliki data yang dapat di-bucket, dalam rangkaian terikat.
Beberapa contoh umum bidang data yang digunakan sebagai kunci partisi bernama adalah kawasan, kode pos, grup pelanggan, atau batas bisnis lainnya.

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
Menunjukkan bahwa layanan menggunakan skema partisi singleton.
Partisi singleton biasanya digunakan ketika layanan tidak memerlukan perutean tambahan.

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
Ini berarti bahwa setiap partisi memiliki rentang kunci int64.

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
Durasi dinyatakan dalam format ISO 8601 'hh:mm:ss'

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
Parameter Sets: Stateful-Singleton, Stateful-UniformInt64Range, Stateful-Named
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
Parameter Sets: Stateful-Singleton, Stateful-UniformInt64Range, Stateful-Named
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
Menentukan ukuran kumpulan replika target untuk layanan terkelola

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
Tentukan nama tipe layanan aplikasi yang dikelola, harus ada dalam manifes aplikasi.

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

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedService

## CATATAN

## RELATED LINKS
