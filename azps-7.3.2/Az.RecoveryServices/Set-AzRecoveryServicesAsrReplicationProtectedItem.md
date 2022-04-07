---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/set-azrecoveryservicesasrreplicationprotecteditem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesAsrReplicationProtectedItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesAsrReplicationProtectedItem.md
ms.openlocfilehash: b95cf3761d64d948ce1419ac51c80e6542e6b735
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140391690"
---
# Set-AzRecoveryServicesAsrReplicationProtectedItem

## SYNOPSIS
Mengatur properti pemulihan seperti jaringan target dan ukuran mesin virtual untuk item dilindungi replikasi tertentu.

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
Cmdlet **Set-AzRecoveryServicesAsrReplicationProtectedItem** mengatur properti pemulihan untuk Replikasi Item yang Diproteksi.

## EXAMPLES

### Contoh 1
```
PS C:\> $currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -ReplicationProtectedItem $RPI -UpdateNic $NicId -RecoveryNetworkId $AzureNetworkID -RecoveryNicSubnetName $subnetName
```

Memulai operasi pembaruan item replikasi yang diproteksi pengaturan menggunakan parameter yang ditentukan dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

### Contoh 2
```
PS C:\> $currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -UpdateNic "00:50:56:8F:3F:7B" -RecoveryNetworkId $recoveryNetwork -RecoveryNicSubnetName $recoverySubnet -NicSelectionType NotSelected
```

Memulai operasi untuk memperbarui item replikasi yang diproteksi pengaturan Kartu Antarmuka Jaringan (Pengurangan NIC) menggunakan parameter yang ditentukan dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

### Contoh 3
```
PS C:\> $currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -PrimaryNic "00:50:56:8F:3F:7B"
```

Memulai operasi pembaruan item terlindungi replikasi NIC(untuk digunakan untuk pengaturan recovered vm )menggunakan parameter tertentu dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

### Contoh 4
```
PS C:\> Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -UpdateNic $updateNic -RecoveryNetworkId $recoveryNetworkId -RecoveryNicSubnetName $recoveryNicSubnetName -NicSelectionType SelectedByUser
```

Memulai operasi untuk memperbarui item dilindungi replikasi NIC (untuk digunakan bagi pengaturan recovered vm )menggunakan parameter tertentu dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

### Contoh 5
```
PS C:\> $currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -UpdateNic $updateNic `
        -RecoveryNetworkId $recoveryNetworkId -RecoveryNicSubnetName $recoveryNicSubnetName -EnableAcceleratedNetworkingOnRecovery
```

Memulai operasi pembaruan item terlindungi replikasi yang dipilih noc tp enable yang dipercepat dalam pemulihan VM(untuk Azure ke pemulihan bencana Azure).
Jangan lewati -EnableAcceleratedNetworkingOnRecovery untuk menonaktifkan Jaringan yang dipercepat.

### Contoh 6
```
PS C:\> $currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi `
        -DiskEncryptionVaultId $DiskEncryptionVaultId -DiskEncryptionSecertUrl $DiskEncryptionSecertUrl `
        -KeyEncryptionVaultId $KeyEncryptionVaultId -KeyEncryptionKeyUrl $KeyEncryptionKeyUrl
```

Mulai operasi pembaruan untuk item terproteksi replikasi terenkripsi yang ditentukan agar menggunakan detail enkripsi yang disertakan untuk vm failover.

### Contoh 7
```
PS C:\> $currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -RecoveryProximityPlacementGroupId $ppg
```

Mulai operasi pembaruan untuk item dilindungi replikasi tertentu untuk menggunakan grup penempatan kedekatan yang disediakan untuk VM failover.

### Contoh 8
```
PS C:\> $currentJob = Set-AzRecoveryServicesAsrReplicationProtectedItem -InputObject $rpi -RecoveryVirtualMachineScaleSetId $vmss
```

Mulai operasi pembaruan untuk item dilindungi replikasi tertentu agar menggunakan skala mesin virtual yang disediakan yang diatur untuk VM failover.

## PARAMETERS

### -ASRVMNicConfiguration
Menentukan detail konfigurasi failover dan failover NIC uji.

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
Menentukan konfigurasi disk yang akan diperbarui untuk disk terkelola Vm (Azure ke Azure DR scenrio).

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
Menentukan URL rahasia enkripsi disk dengan version(Enkripsi disk Azure) untuk digunakan sebagai VM pemulihan setelah failover.

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
Menentukan ID penyimpanan kunci rahasia enkripsi disk(Enkripsi disk Azure) untuk digunakan sebagai VM pemulihan setelah failover.

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
Kamus Id sumber daya disk ke set enkripsi disk Id ARM.

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
Tentukan tag untuk disk VM. Ini berlaku untuk Vmware ke Azure dan HyperV ke penyedia Azure.

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
Menentukan NIC tertentu pada pemulihan vm setelah failover menggunakan jaringan yang dipercepat.

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
Objek input ke cmdlet: Objek item terproteksi replikasi ASR yang terkait dengan item dilindungi replikasi untuk diperbarui.

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
Menentukan versi URL kunci enkripsi disk(Enkripsi disk Azure) untuk digunakan sebagai VM pemulihan setelah failover.

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
Menentukan kunci enkripsi diskVault ID(Enkripsi disk Azure) untuk digunakan sebagai vm pemulihan setelah failover.


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
Spesifikasi pilihan tipe lisensi yang akan digunakan untuk mesin virtual Windows Server. Jika Anda berhak menggunakan Manfaat Penggunaan Hibrid Azure (HUB) untuk migrasi dan ingin menentukan bahwa pengaturan HUB akan digunakan saat gagal atas item yang diproteksi ini, atur tipe lisensi menjadi WindowsServer.

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
Tentukan nama mesin virtual pemulihan yang akan dibuat di failover.

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
Kumpulan ketersediaan untuk replikasi item yang diproteksi setelah failover.

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
Menentukan zona ketersediaan untuk item replikasi yang diproteksi setelah failover.

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
Menentukan akun penyimpanan untuk diagnostik boot bagi pemulihan Azure VM.

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
Tentukan ID grup reservasi kapasitas yang akan digunakan oleh vm failover di kawasan pemulihan target.

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
ID sumber daya layanan awan pemulihan untuk failover komputer virtual ini.

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
Menentukan kolam renang alamat backend target untuk dikaitkan dengan NIC pemulihan.

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
Menentukan nama subnet pada jaringan virtual Azure pemulihan di mana NIC item yang diproteksi ini harus tersambung ke pada failover.

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
Tentukan tag untuk  NICs target VM. Ini berlaku untuk Vmware ke Azure dan HyperV ke penyedia Azure.

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
Menentukan Id Sumber Daya grup penempatan kedekatan pemulihan ke failover mesin virtual.

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
ID grup sumber daya Azure di kawasan pemulihan tempat item yang diproteksi akan dipulihkan dalam failover.

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

### -RecoveryVirtualMachinescaleSetId
Menentukan skala mesin virtual target yang diatur untuk dikonfigurasi.

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
Tentukan tag untuk VM target. Ini berlaku untuk Vmware ke Azure dan HyperV ke penyedia Azure.

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
Tentukan SQL Server lisensi VM. Ini berlaku untuk Vmware ke Azure dan HyperV ke penyedia Azure.

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
Menentukan Id ARM dari jaringan uji (Hanya berlaku untuk skenario replikasi VMware ke Azure).

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
Menentukan uji alamat IP statis (Hanya berlaku untuk skenario replikasi VMware ke Azure).

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

### -TestNicSubnetName
Menentukan nama subnet uji (Hanya berlaku untuk skenario replikasi VMware ke Azure).

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

### -TfoAzureVMName
Menentukan nama uji vm failover.

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
Menentukan NIC mesin virtual di mana cmdlet ini mengatur properti jaringan pemulihan perlu diperbarui.

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
Menentukan apakah mesin virtual Azure yang dibuat di failover harus menggunakan disk terkelola.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRReplicationProtectedItem

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRJob

## CATATAN

## RELATED LINKS

[Get-AzRecoveryServicesAsrReplicationProtectedItem](./Get-AzRecoveryServicesAsrReplicationProtectedItem.md)

[New-AzRecoveryServicesAsrReplicationProtectedItem](./New-AzRecoveryServicesAsrReplicationProtectedItem.md)

[Remove-AzRecoveryServicesAsrReplicationProtectedItem](./Remove-AzRecoveryServicesAsrReplicationProtectedItem.md)
