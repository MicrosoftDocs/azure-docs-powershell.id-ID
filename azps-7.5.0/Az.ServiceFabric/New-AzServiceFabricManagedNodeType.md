---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/new-azservicefabricmanagednodetype
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricManagedNodeType.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricManagedNodeType.md
ms.openlocfilehash: 6a2077267c69ace61e8027c82a6aea9c2f73228b
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145630988"
---
# New-AzServiceFabricManagedNodeType

## SYNOPSIS
Buat sumber daya jenis node baru.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.servicefabric/new-azservicefabricmanagednodetype) untuk informasi terbaru.

## SYNTAX

```
New-AzServiceFabricManagedNodeType [-ResourceGroupName] <String> [-ClusterName] <String> [-Name] <String>
 -InstanceCount <Int32> [-Primary] [-DiskSize <Int32>] [-DiskType <PSDiskType>] [-ApplicationStartPort <Int32>]
 [-ApplicationEndPort <Int32>] [-EphemeralStartPort <Int32>] [-EphemeralEndPort <Int32>] [-VmSize <String>]
 [-VmImagePublisher <String>] [-VmImageOffer <String>] [-VmImageSku <String>] [-VmImageVersion <String>]
 [-Capacity <Hashtable>] [-PlacementProperty <Hashtable>] [-VmUserAssignedIdentity <String[]>] [-IsStateless]
 [-MultiplePlacementGroup] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Buat sumber daya jenis node baru untuk kluster tertentu.

## EXAMPLES

### Contoh 1
```powershell
$rgName = "testRG"
$clusterName = "testCluster"
$NodeTypeName = "nt1"
New-AzServiceFabricManagedNodeType -ResourceGroupName $rgName -ClusterName $clusterName -Name $NodeTypeName -Primary -InstanceCount 3
```

Buat jenis simpul utama dengan 3 simpul.

### Contoh 2
```powershell
$rgName = "testRG"
$clusterName = "testCluster"
$NodeTypeName = "nt1"
New-AzServiceFabricManagedNodeType -ResourceGroupName $rgName -ClusterName $clusterName -Name $NodeTypeName -InstanceCount 5 -Primary -PlacementProperty @{NodeColor="Green";SomeProperty="5";} -Capacity @{ClientConnections="65536";} -ApplicationStartPort 20575 -ApplicationEndPort 20605 -EphemeralStartPort 20606 -EphemeralEndPort 20861
```

Buat jenis node utama dengan 5 simpul dan tentukan properti penempatan, kapasitas, aplikasi, dan port sementara.

### Contoh: 3
```powershell
$rgName = "testRG"
$clusterName = "testCluster"
$NodeTypeName = "nt2"
New-AzServiceFabricManagedNodeType -ResourceGroupName $rgName -ClusterName $clusterName -Name $NodeTypeName -InstanceCount 10 -DiskType Premium_LRS -VmSize "Standard_DS2" -MultiplePlacementGroup
```

Buat jenis node non primer dengan 10 simpul, jenis disk premium, dan beberapa grup penempatan.

### Contoh 4
```powershell
$rgName = "testRG"
$clusterName = "testCluster"
$NodeTypeName = "nt2"
$identityId = "/subscriptions/00000000-0000-0000-0000-00000000/resourceGroups/testRG/providers/Microsoft.ManagedIdentity/userAssignedIdentities/testIdentity"
New-AzServiceFabricManagedNodeType -ResourceGroupName $rgName -ClusterName $clusterName -Name $NodeTypeName -InstanceCount 5 -VmUserAssignedIdentity $identityId -IsStateless
```

Buat jenis node dengan identitas yang ditetapkan pengguna dan ditandai untuk menghosting beban kerja tanpa status.

## PARAMETERS

### -ApplicationEndPort
Port Akhir Aplikasi dari berbagai port.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationStartPort
Port awal aplikasi dari berbagai port.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### -Kapasitas
Tag kapasitas diterapkan ke simpul dalam jenis node sebagai pasangan kunci/nilai, manajer sumber daya kluster menggunakan tag ini untuk memahami berapa banyak sumber daya yang dimiliki simpul.
Memperbarui ini akan menggantikan nilai saat ini.

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

### -DiskSize
Ukuran disk untuk setiap vm dalam jenis node dalam GB.
Default 100.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: DataDiskSize

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskType
Jenis disk data terkelola. IOPS dan throughput diberikan oleh ukuran disk, untuk melihat informasi selengkapnya, buka https://docs.microsoft.com/en-us/azure/virtual-machines/disks-types. Default StandardSSD_LRS

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.PSDiskType
Parameter Sets: (All)
Aliases: DataDiskType
Accepted values: Standard_LRS, StandardSSD_LRS, Premium_LRS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EphemeralEndPort
Port akhir Ephemeral dari berbagai port.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EphemeralStartPort
Port awal Ephemeral dari berbagai port.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceCount
Jumlah simpul dalam jenis node.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsStateless
Menunjukkan apakah jenis node hanya dapat menghosting beban kerja Stateless.

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

### -MultiplePlacementGroup
Menunjukkan apakah set skala yang terkait dengan jenis node dapat terdiri dari beberapa grup penempatan.

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

### -Name
Tentukan nama jenis simpul.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NodeTypeName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PlacementProperty
Tag penempatan diterapkan ke simpul dalam jenis node sebagai pasangan kunci/nilai, yang dapat digunakan untuk menunjukkan di mana layanan tertentu (beban kerja) harus berjalan.
Memperbarui ini akan menggantikan nilai saat ini.

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

### -Primer
Tentukan apakah jenis node adalah primer.
Pada jenis simpul ini akan menjalankan layanan sistem.
Hanya satu jenis node yang harus ditandai sebagai primer.
Jenis node primer tidak dapat dihapus atau diubah untuk kluster yang ada.

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

### -VmImageOffer
Jenis penawaran gambar Azure Virtual Machines Marketplace.
Default: WindowsServer.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "WindowsServer"
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmImagePublisher
Penerbit gambar Azure Virtual Machines Marketplace.
Default: MicrosoftWindowsServer.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "MicrosoftWindowsServer"
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmImageSku
SKU gambar Azure Virtual Machines Marketplace.
Default: 2019-Pusat Data.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "2019-Datacenter"
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmImageVersion
Versi gambar Azure Virtual Machines Marketplace.
Default: terbaru.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "latest"
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmSize
Ukuran komputer virtual di kumpulan.
Semua komputer virtual dalam satu kumpulan berukuran sama.
Default: Standard_D2.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "Standard_D2"
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmUserAssignedIdentity
Daftar identitas assigend pengguna yang terkait dengan set skala komputer virtual di bawah jenis node. Setiap entri akan menjadi id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/{identityName}'. Ikuti langkah-langkah untuk membuat identitas dan menambahkan penetapan peran dengan penyedia sumber Service Fabric sebelumnya di sini:https://docs.microsoft.com/en-us/azure/service-fabric/how-to-managed-identity-managed-cluster-virtual-machine-scale-sets

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedNodeType

## NOTES

## RELATED LINKS
