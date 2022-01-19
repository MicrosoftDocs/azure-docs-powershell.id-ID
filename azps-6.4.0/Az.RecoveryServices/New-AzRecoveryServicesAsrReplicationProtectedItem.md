---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/new-azrecoveryservicesasrreplicationprotecteditem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrReplicationProtectedItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrReplicationProtectedItem.md
ms.openlocfilehash: 099efb3c5db1e329dd466113cd40b858d490c4cb
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136182462"
---
# New-AzRecoveryServicesAsrReplicationProtectedItem

## SYNOPSIS
Memungkinkan replikasi untuk item ASR yang dapat diproteksi dengan membuat item replikasi yang diproteksi.

## SYNTAX

### EnterpriseToEnterprise (Default)
```
New-AzRecoveryServicesAsrReplicationProtectedItem [-VmmToVmm] -ProtectableItem <ASRProtectableItem>
 -Name <String> -ProtectionContainerMapping <ASRProtectionContainerMapping>
 [-WaitForCompletion] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMwareToAzureWithDiskType
```
New-AzRecoveryServicesAsrReplicationProtectedItem [-VMwareToAzure] -ProtectableItem <ASRProtectableItem>
 -Name <String> [-RecoveryVmName <String>] -ProtectionContainerMapping <ASRProtectionContainerMapping>
 -Account <ASRRunAsAccount> [-LogStorageAccountId <String>] -ProcessServer <ASRProcessServer>
 [-RecoveryAzureNetworkId <String>] [-RecoveryAzureSubnetName <String>] -RecoveryResourceGroupId <String>
 [-ReplicationGroupName <String>] [-RecoveryAvailabilityZone <String>]
 [-RecoveryProximityPlacementGroupId <String>] [-RecoveryAvailabilitySetId <String>] [-Size <String>]
 [-SqlServerLicenseType <String>]
 [-RecoveryVmTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-DiskTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-RecoveryNicTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-WaitForCompletion] -DiskType <String> [-DiskEncryptionSetId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMwareToAzure
```
New-AzRecoveryServicesAsrReplicationProtectedItem [-VMwareToAzure] -ProtectableItem <ASRProtectableItem>
 -Name <String> [-RecoveryVmName <String>] -ProtectionContainerMapping <ASRProtectionContainerMapping>
 -Account <ASRRunAsAccount> [-LogStorageAccountId <String>]
 [-InMageAzureV2DiskInput <AsrInMageAzureV2DiskInput[]>] -ProcessServer <ASRProcessServer>
 [-RecoveryAzureNetworkId <String>] [-RecoveryAzureSubnetName <String>] -RecoveryResourceGroupId <String>
 [-ReplicationGroupName <String>] [-RecoveryAvailabilityZone <String>]
 [-RecoveryProximityPlacementGroupId <String>] [-RecoveryAvailabilitySetId <String>] [-Size <String>]
 [-SqlServerLicenseType <String>]
 [-RecoveryVmTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-DiskTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-RecoveryNicTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-WaitForCompletion] [-DiskEncryptionSetId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EnterpriseToAzure
```
New-AzRecoveryServicesAsrReplicationProtectedItem [-HyperVToAzure] -ProtectableItem <ASRProtectableItem>
 -Name <String> [-RecoveryVmName <String>] -ProtectionContainerMapping <ASRProtectionContainerMapping>
 -RecoveryAzureStorageAccountId <String> -RecoveryResourceGroupId <String>
 [-WaitForCompletion] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HyperVSiteToAzure
```
New-AzRecoveryServicesAsrReplicationProtectedItem [-HyperVToAzure] -ProtectableItem <ASRProtectableItem>
 -Name <String> [-RecoveryVmName <String>] -ProtectionContainerMapping <ASRProtectionContainerMapping>
 -RecoveryAzureStorageAccountId <String> -OSDiskName <String> -OS <String> [-LogStorageAccountId <String>]
 [-IncludeDiskId <String[]>] [-RecoveryAzureNetworkId <String>] [-RecoveryAzureSubnetName <String>]
 -RecoveryResourceGroupId <String> [-RecoveryAvailabilityZone <String>]
 [-RecoveryProximityPlacementGroupId <String>] [-RecoveryAvailabilitySetId <String>] [-Size <String>]
 [-SqlServerLicenseType <String>]
 [-RecoveryVmTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-DiskTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-RecoveryNicTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-UseManagedDisk <String>] [-WaitForCompletion] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AzureToAzure
```
New-AzRecoveryServicesAsrReplicationProtectedItem [-AzureToAzure]
 -AzureToAzureDiskReplicationConfiguration <ASRAzuretoAzureDiskReplicationConfig[]> -AzureVmId <String>
 -Name <String> [-RecoveryVmName <String>] -ProtectionContainerMapping <ASRProtectionContainerMapping>
 [-RecoveryAzureNetworkId <String>] [-RecoveryAzureSubnetName <String>] -RecoveryResourceGroupId <String>
 [-ReplicationGroupName <String>] [-RecoveryCloudServiceId <String>] [-RecoveryAvailabilityZone <String>]
 [-RecoveryProximityPlacementGroupId <String>] [-RecoveryVirtualMachineScaleSetId <String>]
 [-RecoveryAvailabilitySetId <String>] [-RecoveryBootDiagStorageAccountId <String>]
 [-DiskEncryptionVaultId <String>] [-DiskEncryptionSecretUrl <String>] [-KeyEncryptionKeyUrl <String>]
 [-KeyEncryptionVaultId <String>] [-WaitForCompletion] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AzureToAzureWithoutDiskDetails
```
New-AzRecoveryServicesAsrReplicationProtectedItem [-AzureToAzure] -AzureVmId <String> -Name <String>
 [-RecoveryVmName <String>] -ProtectionContainerMapping <ASRProtectionContainerMapping>
 [-RecoveryAzureStorageAccountId <String>] -LogStorageAccountId <String> [-RecoveryAzureNetworkId <String>]
 [-RecoveryAzureSubnetName <String>] -RecoveryResourceGroupId <String> [-ReplicationGroupName <String>]
 [-RecoveryAvailabilityZone <String>] [-RecoveryProximityPlacementGroupId <String>]
 [-RecoveryVirtualMachineScaleSetId <String>] [-RecoveryAvailabilitySetId <String>]
 [-RecoveryBootDiagStorageAccountId <String>] [-DiskEncryptionVaultId <String>]
 [-DiskEncryptionSecretUrl <String>] [-KeyEncryptionKeyUrl <String>] [-KeyEncryptionVaultId <String>]
 [-WaitForCompletion] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ReplicateVMwareToAzure
```
New-AzRecoveryServicesAsrReplicationProtectedItem [-ReplicateVMwareToAzure]
 -ProtectableItem <ASRProtectableItem> -Name <String> [-RecoveryVmName <String>] [-LicenseType <String>]
 [-TestNetworkId <String>] [-TestSubnetName <String>]
 -ProtectionContainerMapping <ASRProtectionContainerMapping> [-CredentialsToAccessVm <String>]
 -LogStorageAccountId <String> -ApplianceName <String> -Fabric <ASRFabric> [-RecoveryAzureNetworkId <String>]
 [-RecoveryAzureSubnetName <String>] -RecoveryResourceGroupId <String> [-ReplicationGroupName <String>]
 [-RecoveryAvailabilityZone <String>] [-RecoveryProximityPlacementGroupId <String>]
 [-RecoveryAvailabilitySetId <String>] [-Size <String>]
 [-RecoveryBootDiagStorageAccountId <String>] [-WaitForCompletion] -DiskType <String>
 [-DiskEncryptionSetId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ReplicateVMwareToAzureWithDiskInput
```
New-AzRecoveryServicesAsrReplicationProtectedItem [-ReplicateVMwareToAzure]
 -ProtectableItem <ASRProtectableItem> -InMageRcmDiskInput <ASRInMageRcmDiskInput[]> -Name <String>
 [-RecoveryVmName <String>] [-LicenseType <String>] [-TestNetworkId <String>] [-TestSubnetName <String>]
 -ProtectionContainerMapping <ASRProtectionContainerMapping> [-CredentialsToAccessVm <String>]
 -ApplianceName <String> -Fabric <ASRFabric> [-RecoveryAzureNetworkId <String>]
 [-RecoveryAzureSubnetName <String>] -RecoveryResourceGroupId <String> [-ReplicationGroupName <String>]
 [-RecoveryAvailabilityZone <String>] [-RecoveryProximityPlacementGroupId <String>]
 [-RecoveryAvailabilitySetId <String>] [-Size <String>]
 [-RecoveryBootDiagStorageAccountId <String>] [-WaitForCompletion] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRecoveryServicesAsrReplicationProtectedItem** membuat item baru yang diproteksi replikasi.
Gunakan cmdlet ini untuk mengaktifkan replikasi bagi item yang dapat diproteksi ASR.

## EXAMPLES

### Contoh 1
```
PS C:\> $currentJob = New-AzRecoveryServicesAsrReplicationProtectedItem -ProtectableItem $VM -Name $VM.Name -ProtectionContainerMapping $ProtectionContainerMapping
```

Memulai operasi pembuatan item dilindungi replikasi untuk item yang dapat diproteksi ASR tertentu dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

### Contoh 2
```
PS C:\>$job = New-AzRecoveryServicesAsrReplicationProtectedItem -VMwareToAzure -Account $fabric.FabricSpecificDetails.RunAsAccounts[0] `
-RecoveryResourceGroupId $RecoveryResourceGroupId -RecoveryAzureNetworkId $RecoveryAzureNetworkId  -name $name `
-ProcessServer $fabric.FabricSpecificDetails.ProcessServers[0] -ProtectableItem $protectableItem -ProtectionContainerMapping $pcm `
-RecoveryAzureSubnetName $RecoveryAzureSubnetName -RecoveryVmName $RecoveryVmName -LogStorageAccountId $LogStorageAccountId
```

Memulai operasi pembuatan item dilindungi replikasi untuk item yang dapat diproteksi ASR tertentu dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi(skenario vmWare ke Azure).

### Contoh 3
```
PS C:>$job = New-AzRecoveryServicesAsrReplicationProtectedItem -AzureToAzure -AzureToAzureDiskReplicationConfig disk1,disk2 -AzVmId $vmId `
-Name "a2aprotectedItem" -RecoveryVmName "vmName" -ProtectionContainerMapping $pcmMapping -RecoveryResourceGroupId $recoveryResourceGroup
```

Memulai operasi pembuatan item dilindungi replikasi untuk item yang dapat diproteksi ASR tertentu dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi (skenario Azure ke Azure).

### Contoh 4
```
PS C:\> $disk1 = New-AzureToAzureDiskReplicationConfiguration -vhdUri  $diskUri1 -RecoveryAzureStorageAccountId $recoveryAzureStorageAccountId `
-LogStorageAccountId $logStorageAccountId  
PS C:\> $disk2 = New-AzureToAzureDiskReplicationConfiguration -vhdUri  $diskUri2 -RecoveryAzureStorageAccountId $recoveryAzureStorageAccountId `
-LogStorageAccountId $logStorageAccountId  
PS C:\> $enableDRjob = New-AzRecoveryServicesAsrReplicationProtectedItem -AzureToAzure -AzureVmId $vmId -Name $rpiName `
-RecoveryCloudServiceId  $recoveryCloudServiceId -ProtectionContainerMapping $pcm -RecoveryResourceGroupId  $RecoveryResourceGroupId `
-AzureToAzureDiskReplicationConfiguration $disk1,$disk2 -RecoveryAzureNetworkId $RecoveryAzureNetworkId -RecoveryAzureSubnetName $RecoveryAzureSubnetName
```

Memulai operasi pembuatan item dilindungi replikasi untuk VmId yang ditentukan dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi (skenario Azure ke Azure).

### Contoh 5
```
PS C:\>$disk1 = New-AzRecoveryServicesAsrInMageAzureV2DiskInput -DiskId $diskId -LogStorageAccountId $logStorageAccountId -DiskType $diskType
PS C:\>$disk2 = New-AzRecoveryServicesAsrInMageAzureV2DiskInput -DiskId $diskId2 -LogStorageAccountId $logStorageAccountId -DiskType $diskType2

PS C:\>$job = New-AzRecoveryServicesAsrReplicationProtectedItem -VMwareToAzure -Account $fabric.FabricSpecificDetails.RunAsAccounts[0] -RecoveryResourceGroupId $RecoveryResourceGroupId `
-RecoveryAzureNetworkId $RecoveryAzureNetworkId  -name $name -ProcessServer $fabric.FabricSpecificDetails.ProcessServers[0] -ProtectableItem $protectableItem  `
-ProtectionContainerMapping $pcm -RecoveryAzureSubnetName $RecoveryAzureSubnetName -RecoveryVmName $RecoveryVmName `
-LogStorageAccountId $LogStorageAccountId -InMageAzureV2DiskInput $disk1,$disk2
```

Memulai operasi pembuatan item dilindungi replikasi untuk item yang dapat diproteksi ASR tertentu termasuk disk selektif dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi(skenario vmWare ke Azure) dengan disk yang dipilih.

### Contoh 6
```
PS C:\>$job = New-AzRecoveryServicesAsrReplicationProtectedItem -VMwareToAzure -Account $fabric.FabricSpecificDetails.RunAsAccounts[0] -RecoveryResourceGroupId $RecoveryResourceGroupId `
-RecoveryAzureNetworkId $RecoveryAzureNetworkId  -name $name -ProcessServer $fabric.FabricSpecificDetails.ProcessServers[0] -ProtectableItem $protectableItem  `
-ProtectionContainerMapping $pcm -RecoveryAzureSubnetName $RecoveryAzureSubnetName -RecoveryVmName $RecoveryVmName `
-LogStorageAccountId $LogStorageAccountId -DiskType Standard_LRS

Starts the replication protected item creation operation for the specified ASR protectable item with default disk type and returns the ASR job used to track the operation(vmWare to Azure scenario).
```

### Contoh 7
```
PS C:\> $disk1 = New-AzureToAzureDiskReplicationConfiguration -vhdUri  $diskUri1 -RecoveryAzureStorageAccountId $recoveryAzureStorageAccountId -LogStorageAccountId $logStorageAccountId  
PS C:\> $disk2 = new-AzureToAzureDiskReplicationConfiguration -vhdUri  $diskUri2 -RecoveryAzureStorageAccountId $recoveryAzureStorageAccountId -LogStorageAccountId $logStorageAccountId  
PS C:\> $enableDRjob = New-AzRecoveryServicesAsrReplicationProtectedItem -AzureToAzure -AzVmId $vmId -Name $rpiName `
-RecoveryCloudServiceId  $recoveryCloudServiceId -ProtectionContainerMapping $pcm -RecoveryResourceGroupId  $RecoveryResourceGroupId `
-AzureToAzureDiskReplicationConfiguration $disk1,$disk2 -DiskEncryptionVaultId  $DiskEncryptionVaultId -DiskEncryptionSecertUrl $DiskEncryptionSecertUrl `
 -KeyEncryptionVaultId $KeyEncryptionVaultId  -KeyEncryptionKeyUrl $KeyEncryptionKeyUrl
```

Memulai operasi pembuatan item dilindungi replikasi untuk VmId yang ditentukan dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi (skenario Azure ke Azure). Untuk detail VM failover yang disampaikan dalam cmdlet untuk enkripsi akan digunakan .

### Contoh 8
```
PS C:>$job = New-AzRecoveryServicesAsrReplicationProtectedItem -AzureToAzure -AzureToAzureDiskReplicationConfig disk1,disk2 -AzVmId $vmId `
-Name "a2aprotectedItem" -RecoveryVmName "vmName" -ProtectionContainerMapping $pcmMapping -RecoveryResourceGroupId $recoveryResourceGroup -RecoveryProximityPlacementGroupId $ppg
```

Memulai operasi pembuatan item dilindungi replikasi untuk Komputer Virtual di dalam grup penempatan Kedekatan dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi (skenario Azure ke Azure).

### Contoh 9
```
PS C:>$job = New-AzRecoveryServicesAsrReplicationProtectedItem -AzureToAzure -AzureToAzureDiskReplicationConfig disk1,disk2 -AzVmId $vmId `
-Name "a2aprotectedItem" -RecoveryVmName "vmName" -ProtectionContainerMapping $pcmMapping -RecoveryResourceGroupId $recoveryResourceGroup -RecoveryVirtualMachineScaleSetId $vmss
```

Memulai operasi pembuatan item dilindungi replikasi untuk Komputer Virtual dengan kumpulan skala mesin virtual target dikonfigurasi dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi (skenario Azure ke Azure).

## PARAMETERS

### -Akun
Jalankan sebagai akun yang digunakan untuk mendorong instalan layanan Mobilitas jika diperlukan. Must be one from the list of run as accounts in the ASR fabric.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRRunAsAccount
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplianceName
Menentukan nama alat yang akan digunakan untuk mereplikasi mesin ini.

```yaml
Type: System.String
Parameter Sets: ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureToAzure
Parameter pengalihan menentukan pembuatan item yang direplikasi di Azure ke skenario Azure.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureToAzure, AzureToAzureWithoutDiskDetails
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureToAzureDiskReplicationConfiguration
Menentukan konfigurasi disk untuk menggunakan Vm untuk Azure dalam skenario pemulihan bencana Azure.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRAzuretoAzureDiskReplicationConfig[]
Parameter Sets: AzureToAzure
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureVmId
Menentukan id Azure VM untuk perlindungan pemulihan bencana di kawasan pemulihan.

```yaml
Type: System.String
Parameter Sets: AzureToAzure, AzureToAzureWithoutDiskDetails
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CredentialsToAccessVm
Menentukan nama kredensial yang akan digunakan untuk menginstal layanan Mobilitas di komputer sumber jika diperlukan.

```yaml
Type: System.String
Parameter Sets: ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
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

### -DiskEncryptionSecretUrl
Menentukan URL rahasia enkripsi disk dengan version(Enkripsi disk Azure) untuk digunakan sebagai VM pemulihan setelah failover.

```yaml
Type: System.String
Parameter Sets: AzureToAzure, AzureToAzureWithoutDiskDetails
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskEncryptionSetId
Menentukan Id sumber daya dari kumpulan enkripsi disk, untuk digunakan untuk enkripsi disk yang dikelola.

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, ReplicateVMwareToAzure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskEncryptionVaultId
Menentukan ID penyimpanan rahasia enkripsi disk(Enkripsi disk Azure) untuk digunakan sebagai VM pemulihan setelah failover.

```yaml
Type: System.String
Parameter Sets: AzureToAzure, AzureToAzureWithoutDiskDetails
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskTag
Tentukan tag untuk disk VM.

```yaml
Type: System.Collections.Generic.IDictionary`2[System.String,System.String]
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, HyperVSiteToAzure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskType
Menentukan tipe disk terkelola VM Pemulihan.

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, ReplicateVMwareToAzure
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fabric
Specifies the ASR Fabric object.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRFabric
Parameter Sets: ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HyperVToAzure
Alihkan parameter untuk menentukan item yang direplikasi adalah mesin virtual Hyper-V yang sedang direplikasi ke Azure.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EnterpriseToAzure, HyperVSiteToAzure
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeDiskId
Daftar disk yang disertakan untuk replikasi. Secara default, semua disk disertakan.

```yaml
Type: System.String[]
Parameter Sets: HyperVSiteToAzure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InMageAzurev2DiskInput
Menentukan input konfigurasi disk untuk id disk vMWare untuk memproteksi dari item tertentu yang dapat diproteksi.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.AsrInMageAzureV2DiskInput[]
Parameter Sets: VMwareToAzure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InMagercmDiskInput
Menentukan input disk yang akan digunakan untuk VMware skenario pemulihan bencana Azure.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRInMageRcmDiskInput[]
Parameter Sets: ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyEncryptionKeyUrl
Menentukan URL kunci enkripsi disk dengan version(Enkripsi disk Azure) yang akan digunakan sebagai pemulihan VM setelah failover.

```yaml
Type: System.String
Parameter Sets: AzureToAzure, AzureToAzureWithoutDiskDetails
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyEncryptionVaultId
Menentukan ID kunci enkripsi disk key-vault(Enkripsi disk Azure) yang akan digunakan sebagai VM pemulihan setelah failover.

```yaml
Type: System.String
Parameter Sets: AzureToAzure, AzureToAzureWithoutDiskDetails
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseType
Menentukan tipe lisensi.
Nilai yang dapat diterima untuk parameter ini adalah: NoLicenseType atau WindowsServer.

```yaml
Type: System.String
Parameter Sets: ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:
Accepted values: NoLicenseType, WindowsServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogStorageAccountId
Menentukan Id akun penyimpanan log atau cache yang akan digunakan untuk menyimpan log replikasi.

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, HyperVSiteToAzure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: AzureToAzureWithoutDiskDetails, ReplicateVMwareToAzure
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama untuk item terlindungi replikasi ASR. Nama harus unik di dalam vault.

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

### -OS
Menentukan keluarga sistem operasi.
Nilai yang dapat diterima untuk parameter ini adalah: Windows atau Linux.

```yaml
Type: System.String
Parameter Sets: HyperVSiteToAzure
Aliases:
Accepted values: Windows, Linux

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSDiskName
Menentukan nama disk sistem operasi.

```yaml
Type: System.String
Parameter Sets: HyperVSiteToAzure
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProcessServer
Server Proses untuk digunakan untuk mereplikasi komputer ini. Use the list of process servers in the ASR fabric corresponding to the Configuration server to specify one.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRProcessServer
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectableItem
Menentukan objek item yang dapat diproteksi ASR untuk replikasi yang diaktifkan.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRProtectableItem
Parameter Sets: EnterpriseToEnterprise, VMwareToAzureWithDiskType, VMwareToAzure, EnterpriseToAzure, HyperVSiteToAzure, ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionContainerMapping
Menentukan objek pemetaan wadah proteksi ASR yang terkait dengan kebijakan replikasi yang akan digunakan untuk replikasi.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRProtectionContainerMapping
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryAvailabilitySetId
ID AvailabilitySet untuk memulihkan komputer dalam hal failover.

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, HyperVSiteToAzure, AzureToAzure, AzureToAzureWithoutDiskDetails, ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryAvailabilityZone
Menentukan zona ketersediaan VM pemulihan setelah failover.


```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, HyperVSiteToAzure, AzureToAzure, AzureToAzureWithoutDiskDetails, ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryAzureNetworkId
ID jaringan virtual Azure untuk memulihkan mesin dalam hal failover.

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, HyperVSiteToAzure, AzureToAzure, AzureToAzureWithoutDiskDetails, ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryAzureStorageAccountId
Menentukan ID akun penyimpanan Azure untuk direplikasi.

```yaml
Type: System.String
Parameter Sets: EnterpriseToAzure, HyperVSiteToAzure
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: AzureToAzureWithoutDiskDetails
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryAzureSubnetName
Subnet dalam jaringan virtual Azure pemulihan yang gagal melalui mesin virtual harus dilampirkan dalam kejadian failover.

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, HyperVSiteToAzure, AzureToAzure, AzureToAzureWithoutDiskDetails, ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryBootDiagStorageAccountId
Menentukan akun penyimpanan untuk diagnostik boot bagi pemulihan Azure VM.

```yaml
Type: System.String
Parameter Sets: AzureToAzure, AzureToAzureWithoutDiskDetails, ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryCloudServiceId
Menentukan ID sumber daya layanan awan pemulihan untuk perangkat virtual ini ke failover.

```yaml
Type: System.String
Parameter Sets: AzureToAzure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryNicTag
Tentukan tag untuk NICs target VM.

```yaml
Type: System.Collections.Generic.IDictionary`2[System.String,System.String]
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, HyperVSiteToAzure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryProximityPlacementGroupId
Tentukan Id grup penempatan kedekatan untuk digunakan oleh failover Vm dalam kawasan pemulihan target.

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, HyperVSiteToAzure, AzureToAzure, AzureToAzureWithoutDiskDetails, ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryResourceGroupId
Menentukan pengidentifikasi ARM dari grup sumber daya tempat mesin virtual akan dibuat dalam kejadian failover.

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, EnterpriseToAzure, HyperVSiteToAzure, AzureToAzure, AzureToAzureWithoutDiskDetails, ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryVirtualMachinescaleSetId
Tentukan Id kumpulan skala mesin virtual yang akan digunakan oleh failover Vm di kawasan pemulihan target.

```yaml
Type: System.String
Parameter Sets: AzureToAzure, AzureToAzureWithoutDiskDetails
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryVmName
Nama vm pemulihan yang dibuat setelah failover.

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, EnterpriseToAzure, HyperVSiteToAzure, AzureToAzure, AzureToAzureWithoutDiskDetails, ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryVmTag
Tentukan tag untuk VM target.

```yaml
Type: System.Collections.Generic.IDictionary`2[System.String,System.String]
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, HyperVSiteToAzure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicateVMwareToAzure
Beralih parameter untuk menentukan item yang direplikasi adalah mesin virtual VMware yang sedang direplikasi ke Azure.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationGroupName
Menentukan nama grup replikasi yang akan digunakan untuk membuat poin pemulihan yang konsisten pada multi-VM. Secara default, setiap item yang dilindungi replikasi dibuat dalam grup dengan poin pemulihan konsisten multi-VM dan grup tersebut tidak akan dihasilkan. Gunakan opsi ini hanya jika Anda perlu membuat poin pemulihan yang konsisten multi VM di seluruh grup mesin dengan melindungi semua komputer ke grup replikasi yang sama. 

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, AzureToAzure, AzureToAzureWithoutDiskDetails, ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Size
Tentukan ukuran mesin virtual pemulihan.

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, HyperVSiteToAzure, ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlServerLicenseType
Tentukan SQL Server jenis lisensi VM.

```yaml
Type: System.String
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure, HyperVSiteToAzure
Aliases:
Accepted values: NoLicenseType, PAYG, AHUB

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestNetworkId
Menentukan id ARM jaringan uji.

```yaml
Type: System.String
Parameter Sets: ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestSubnetName
Menentukan nama subnet jaringan uji.

```yaml
Type: System.String
Parameter Sets: ReplicateVMwareToAzure, ReplicateVMwareToAzureWithDiskInput
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseManagedDisk
Menentukan apakah mesin virtual Azure yang dibuat di failover harus menggunakan disk terkelola. Layanan Itu Menerima True atau False.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: True, False

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmmToVmm
Alihkan parameter untuk menentukan item yang direplikasi adalah mesin virtual Hyper-V yang sedang direplikasi antara situs VMM yang dikelola Hyper-V.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EnterpriseToEnterprise
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMwareToAzure
Alihkan parameter untuk menentukan item yang direplikasi adalah mesin virtual VMware atau server fisik yang akan direplikasi ke Azure.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: VMwareToAzureWithDiskType, VMwareToAzure
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForCompletion
Menentukan bahwa cmdlet harus menunggu penyelesaian operasi sebelum kembali.

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

### -Konfirmasi
Meminta konfirmasi sebelum memulai operasi.

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

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRProtectableItem

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRJob

## CATATAN

## RELATED LINKS

[Get-AzRecoveryServicesAsrReplicationProtectedItem](./Get-AzRecoveryServicesAsrReplicationProtectedItem.md)

[Remove-AzRecoveryServicesAsrReplicationProtectedItem](./Remove-AzRecoveryServicesAsrReplicationProtectedItem.md)

[Set-AzRecoveryServicesAsrReplicationProtectedItem](./Set-AzRecoveryServicesAsrReplicationProtectedItem.md)
