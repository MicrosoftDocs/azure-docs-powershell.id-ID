---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/set-azrecoveryservicesasrreplicationprotecteditem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesAsrReplicationProtectedItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesAsrReplicationProtectedItem.md
ms.openlocfilehash: 83f5c8c6ddf1d8fbd94678a0ad0ddc26de27ff0e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142166419"
---
# Set-AzRecoveryServicesAsrReplicationProtectedItem

## SYNOPSIS
Mengatur properti pemulihan seperti jaringan target dan ukuran mesin virtual untuk item yang diproteksi replikasi tertentu.

## SYNTAX

```
Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject <ASRReplicationProtectedItem> [-Name <String>]
 [-Size <String>] [-UpdateNic <String>] [-RecoveryNetworkId <String>] [-PrimaryNic <String>]
 [-RecoveryCloudServiceId <String>] [-RecoveryNicSubnetName <String>] [-RecoveryNicStaticIPAddress <String>]
 [-TestNicSubnetName <String>] [-TestNicStaticIPAddress <String>] [-NicSelectionType <String>]
 [-RecoveryResourceGroupId <String>] [-LicenseType <String>] [-RecoveryAvailabilitySet <String>]
 [-SqlServerLicenseType <String>]
 [-RecoveryVmTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-DiskTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-RecoveryNicTag <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-RecoveryAvailabilityZone <String>] [-RecoveryProximityPlacementGroupId <String>]
 [-RecoveryVirtualMachineScaleSetId <String>] [-RecoveryCapacityReservationGroupId <String>]
 [-EnableAcceleratedNetworkingOnRecovery] [-RecoveryBootDiagStorageAccountId <String>]
 [-AzureToAzureUpdateReplicationConfiguration <ASRAzuretoAzureDiskReplicationConfig[]>]
 [-DiskEncryptionVaultId <String>] [-DiskEncryptionSecretUrl <String>] [-KeyEncryptionKeyUrl <String>]
 [-KeyEncryptionVaultId <String>] [-UseManagedDisk <String>]
 [-DiskIdToDiskEncryptionSetMap <System.Collections.Generic.IDictionary`2[System.String,System.String]>]
 [-RecoveryPublicIPAddressId <String>] [-RecoveryNetworkSecurityGroupId <String>]
 [-RecoveryLBBackendAddressPoolId <String[]>] [-TfoAzureVMName <String>]
 [-ASRVMNicConfiguration <ASRVMNicConfig[]>] [-TestNetworkId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzRecoveryServicesAsrReplicationProtectedItem** mengatur properti pemulihan untuk Item terproteksi Replikasi.

## EXAMPLES

### Contoh 1
```powershell
$currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -ReplicationProtectedItem $RPI -UpdateNic $NicId -RecoveryNetworkId $AzureNetworkID -RecoveryNicSubnetName $subnetName
```

Memulai operasi memperbarui pengaturan item yang diproteksi replikasi menggunakan parameter tertentu dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

### Contoh 2
```powershell
$currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -UpdateNic "00:50:56:8F:3F:7B" -RecoveryNetworkId $recoveryNetwork -RecoveryNicSubnetName $recoverySubnet -NicSelectionType NotSelected
```

Memulai operasi memperbarui item terproteksi replikasi pengaturan kartu Antarmuka Jaringan (Reduksi NIC) menggunakan parameter yang ditentukan dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

### Contoh 3
```powershell
$currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -PrimaryNic "00:50:56:8F:3F:7B"
```

Memulai operasi memperbarui item terproteksi replikasi primer NIC(untuk digunakan untuk pulih vm )pengaturan menggunakan parameter yang ditentukan dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

### Contoh 4
```powershell
Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -UpdateNic $updateNic -RecoveryNetworkId $recoveryNetworkId -RecoveryNicSubnetName $recoveryNicSubnetName -NicSelectionType SelectedByUser
```

Memulai operasi memperbarui item yang dilindungi replikasi NIC (untuk digunakan untuk vm )pengaturan yang dipulihkan menggunakan parameter yang ditentukan dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

### Contoh 5
```powershell
$currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -UpdateNic $updateNic `
        -RecoveryNetworkId $recoveryNetworkId -RecoveryNicSubnetName $recoveryNicSubnetName -EnableAcceleratedNetworkingOnRecovery
```

Memulai operasi memperbarui item yang dilindungi replikasi dipilih noc tp mengaktifkan percepatan jaringan pada pemulihan VM(untuk Azure ke Azure pemulihan bencana).
Jangan lewat -EnableAcceleratedNetworkingOnRecovery untuk menonaktifkan jaringan yang dipercepat.

### Contoh 6
```powershell
$currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi `
        -DiskEncryptionVaultId $DiskEncryptionVaultId -DiskEncryptionSecertUrl $DiskEncryptionSecertUrl `
        -KeyEncryptionVaultId $KeyEncryptionVaultId -KeyEncryptionKeyUrl $KeyEncryptionKeyUrl
```

Mulai operasi pembaruan untuk item terproteksi replikasi terenkripsi tertentu untuk menggunakan detail enkripsi yang disediakan untuk VM failover.

### Contoh 7
```powershell
$currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -RecoveryProximityPlacementGroupId $ppg
```

Mulai operasi pembaruan untuk item yang diproteksi replikasi tertentu untuk menggunakan grup penempatan kedekatan yang disediakan untuk VM failover.

### Contoh 8
```powershell
$currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -RecoveryVirtualMachineScaleSetId $vmss
```

Mulai operasi pembaruan untuk item yang dilindungi replikasi tertentu untuk menggunakan kumpulan skala mesin virtual yang disediakan untuk VM failover.

## PARAMETERS

### -ASRVMNicConfiguration
Menentukan detail konfigurasi NIC failover dan failover uji coba.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRVMNicConfig[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureToAzureUpdateReplicationConfiguration
Menentukan konfigurasi disk yang akan diperbarui untuk Vm disk terkelola (Azure ke Azure DR scenrio).

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRAzuretoAzureDiskReplicationConfig[]
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

### -DiskEncryptionSecretUrl
Menentukan URL rahasia enkripsi disk dengan versi(Enkripsi disk Azure) untuk digunakan sebagai pemulihan VM setelah failover.

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

### -DiskEncryptionVaultId
Menentukan ID kubah kunci rahasia enkripsi disk(enkripsi disk Azure) untuk digunakan sebagai pemulihan VM setelah failover.

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

### -DiskIdToDiskEncryptionSetMap
Kamus Id sumber daya disk untuk mengenkripsi disk set ARM Id.

```yaml
Type: System.Collections.Generic.IDictionary`2[System.String,System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskTag
Tentukan tag untuk disk VM. Ini berlaku untuk Vmware untuk Azure dan HyperV untuk penyedia Azure.

```yaml
Type: System.Collections.Generic.IDictionary`2[System.String,System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAcceleratedNetworkingOnRecovery
Menentukan NIC yang ditentukan pada vm pemulihan setelah failover menggunakan jaringan yang dipercepat.

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
Objek input ke cmdlet: Objek item yang diproteksi replikasi ASR terkait dengan item yang diproteksi replikasi untuk diperbarui.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRReplicationProtectedItem
Parameter Sets: (All)
Aliases: ReplicationProtectedItem

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyEncryptionKeyUrl
Menentukan versi URL kunci enkripsi disk(enkripsi disk Azure) untuk digunakan sebagai pemulihan VM setelah failover.

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

### -KeyEncryptionVaultId
Menentukan kunci enkripsi disk KeyVault ID(Enkripsi disk Azure) untuk digunakan sebagai pemulihan VM setelah failover.


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

### -LicenseType
Specifiy pilihan tipe lisensi yang akan digunakan untuk mesin virtual server Windows. Jika Anda berhak menggunakan Manfaat Penggunaan Hibrid Azure (HUB) untuk migrasi dan ingin menentukan bahwa pengaturan HUB digunakan saat gagal atas item yang diproteksi ini, atur tipe lisensi menjadi WindowsServer.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: NoLicenseType, WindowsServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama mesin virtual pemulihan yang akan dibuat pada failover.

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

### -NicSelectionType
Menentukan properti kartu antarmuka jaringan (NIC) yang diatur oleh pengguna atau diatur secara default.
Anda dapat menentukan NotSelected untuk kembali ke nilai default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: NotSelected, SelectedByUser

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryNic
Menentukan NIC yang akan digunakan sebagai NIC utama untuk pemulihan VM setelah failover.

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

### -RecoveryAvailabilitySet
Ketersediaan yang diatur untuk item yang diproteksi replikasi setelah failover.

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

### -RecoveryAvailabilityZone
Menentukan zona ketersediaan untuk item yang dilindungi replikasi setelah failover.

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

### -RecoveryBootDiagStorageAccountId
Menentukan akun penyimpanan untuk diagnostik boot untuk pemulihan Azure VM.

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

### -RecoveryCapacityReservationGroupId
Tentukan Id grup reservasi kapasitas yang akan digunakan oleh VM failover di wilayah pemulihan target.

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

### -RecoveryCloudServiceId
ID sumber daya layanan cloud pemulihan untuk gagalover mesin virtual ini.

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

### -RecoveryLBBackendAddressPoolId
Menentukan kumpulan alamat backend target yang akan dikaitkan dengan NIC pemulihan.

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

### -RecoveryNetworkId
Menentukan ID jaringan virtual Azure tempat item yang diproteksi harus gagal.

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

### -RecoveryNetworkSecurityGroupId
Menentukan ID grup keamanan jaringan yang akan dikaitkan dengan NIC pemulihan.

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

### -RecoveryNicStaticIPAddress
Menentukan alamat IP statis yang harus ditetapkan ke NIC utama pada pemulihan.

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

### -RecoveryNicSubnetName
Menentukan nama subnet pada jaringan virtual Azure pemulihan tempat NIC item yang dilindungi ini harus tersambung pada failover.

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

### -RecoveryNicTag
Tentukan tag untuk NIC target VM. Ini berlaku untuk Vmware untuk Azure dan HyperV untuk penyedia Azure.

```yaml
Type: System.Collections.Generic.IDictionary`2[System.String,System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryProximityPlacementGroupId
Menentukan Id Sumber Daya dari grup penempatan kedekatan pemulihan untuk kegagalan mesin virtual.

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

### -RecoveryPublicIPAddressId
Menentukan ID sumber daya alamat IP publik yang akan dikaitkan dengan NIC pemulihan.

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

### -RecoveryResourceGroupId
ID grup sumber daya Azure di wilayah pemulihan tempat item yang diproteksi akan dipulihkan saat gagal.

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

### -RecoveryVirtualMachineScaleSetId
Menentukan skala mesin virtual target yang akan dikonfigurasi.

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

### -RecoveryVmTag
Tentukan tag untuk VM target. Ini berlaku untuk Vmware untuk Azure dan HyperV untuk penyedia Azure.

```yaml
Type: System.Collections.Generic.IDictionary`2[System.String,System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Size
Menentukan ukuran mesin virtual pemulihan.
Nilai harus berasal dari kumpulan ukuran yang didukung oleh mesin virtual Azure.

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

### -SqlServerLicenseType
Tentukan tipe lisensi SQL Server VM. Ini berlaku untuk Vmware untuk Azure dan HyperV untuk penyedia Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: NoLicenseType, PAYG, AHUB

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestNetworkId
Menentukan ID ARM jaringan uji (Berlaku hanya untuk skenario replikasi VMware ke Azure).

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

### -TestNicStaticIPAddress
Menentukan alamat IP statis uji (Berlaku hanya untuk VMware ke skenario replikasi Azure).

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

### -TestNicsubnetName
Menentukan nama subnet uji (Berlaku hanya untuk VMware ke skenario replikasi Azure).

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

### -TfoAzurevmName
Menentukan nama VM failover uji.

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

### -UpdateNic
Menentukan NIC mesin virtual tempat cmdlet ini mengatur properti jaringan pemulihan perlu diperbarui.

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

### -UseManagedDisk
Menentukan apakah mesin virtual Azure yang dibuat pada failover harus menggunakan disk terkelola.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRReplicationProtectedItem

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRJob

## CATATAN

## RELATED LINKS

[Get-AzRecoveryServicesAsrReplicationProtectedItem](./Get-AzRecoveryServicesAsrReplicationProtectedItem.md)

[New-AzRecoveryServicesAsrReplicationProtectedItem](./New-AzRecoveryServicesAsrReplicationProtectedItem.md)

[Remove-AzRecoveryServicesAsrReplicationProtectedItem](./Remove-AzRecoveryServicesAsrReplicationProtectedItem.md)
