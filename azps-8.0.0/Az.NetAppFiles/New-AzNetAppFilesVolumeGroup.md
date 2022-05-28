---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NetAppFiles.dll-Help.xml
Module Name: Az.NetAppFiles
online version: https://docs.microsoft.com/powershell/module/az.netappfiles/new-aznetappfilesvolumegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/New-AzNetAppFilesVolumeGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/New-AzNetAppFilesVolumeGroup.md
ms.openlocfilehash: 031c74bcf8ba2ae8e7fb642300de77e343ede134
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145537850"
---
# New-AzNetAppFilesVolumeGroup

## SYNOPSIS
Membuat VolumeGroup Azure NetApp Files (ANF) baru bersama dengan volume yang diperlukan.
Membuat grup volume akan membuat semua volume yang ditentukan dalam isi permintaan secara implisit. Setelah volume dibuat menggunakan grup volume, volume tersebut akan diperlakukan sebagai volume reguler setelahnya.

## SYNTAX

### ByFieldsParameterSet (Default)
```
New-AzNetAppFilesVolumeGroup -ResourceGroupName <String> -Location <String> -AccountName <String>
 -PoolName <String> [-Name <String>] [-GroupDescription <String>] [-ApplicationType <String>]
 -ApplicationIdentifier <String> -ProximityPlacementGroup <String> -NodeMemory <Int32>
 [-CapacityOverhead <Int32>] [-StartingHostId <Int32>] [-HostCount <Int32>] [-SystemRole <String>]
 [-Prefix <String>] [-Vnet <String>] [-SubnetId <String>] [-DataSize <Int64>] [-DataPerformance <Int32>]
 [-LogSize <Int64>] [-LogPerformance <Int32>] [-SharedSize <Int64>] [-SharedPerformance <Int32>]
 [-DataBackupSize <Int64>] [-DataBackupPerformance <Int32>] [-LogBackupSize <Int64>]
 [-LogBackupPerformance <Int32>] [-HannaSystemReplication] [-DisasterRecoveryDestination]
 [-BackupProtocolType <String[]>] [-ExportPolicy <PSNetAppFilesVolumeExportPolicy>]
 [-GlobalPlacementRule <System.Collections.Generic.IList`1[Microsoft.Azure.Management.NetApp.Models.PlacementKeyValuePairs]>]
 [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
New-AzNetAppFilesVolumeGroup -PoolName <String> [-Name <String>] [-GroupDescription <String>]
 [-ApplicationType <String>] -ApplicationIdentifier <String> -ProximityPlacementGroup <String>
 -NodeMemory <Int32> [-CapacityOverhead <Int32>] [-StartingHostId <Int32>] [-HostCount <Int32>]
 [-SystemRole <String>] [-Prefix <String>] [-Vnet <String>] [-SubnetId <String>] [-DataSize <Int64>]
 [-DataPerformance <Int32>] [-LogSize <Int64>] [-LogPerformance <Int32>] [-SharedSize <Int64>]
 [-SharedPerformance <Int32>] [-DataBackupSize <Int64>] [-DataBackupPerformance <Int32>]
 [-LogBackupSize <Int64>] [-LogBackupPerformance <Int32>] [-HannaSystemReplication]
 [-DisasterRecoveryDestination] [-BackupProtocolType <String[]>]
 [-ExportPolicy <PSNetAppFilesVolumeExportPolicy>]
 [-GlobalPlacementRule <System.Collections.Generic.IList`1[Microsoft.Azure.Management.NetApp.Models.PlacementKeyValuePairs]>]
 [-Tag <Hashtable>] -AccountObject <PSNetAppFilesAccount> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzNetAppFilesVolume** membuat VolumeGroup ANF.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzNetAppFilesVolumeGroup -ResourceGroupName "MyRG" -AccountName "MyAnfAccount" -PoolName "MyAnfPool" -VolumeName "MyAnfVolume" -Name "MyAnfVolumeGroupName" -l "westus2"  -GroupDescription "MyAnfVolumeGroup Description" -ApplicationIdentifier "SH1" -ProximityPlacementGroup "MyPPGResourceId" -Vnet "MyAnfVnet" -SystemRole "PRIMARY" -NodeMemory 100
```

Perintah ini membuat "PRIMARY" ANF VolumeGroup "MyAnfVolumeGroup" baru dalam Akun "MyAnfAccount" menggunakan proximityPlacementGroup "MyPPGResourceId", vnet "MyAnfVnet", dan NodeMemory 100

## PARAMETERS

### -AccountName
Nama akun ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountObject
Akun untuk objek kumpulan baru

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesAccount
Parameter Sets: ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationIdentifier
Pengidentifikasi khusus aplikasi, ID Sistem SAP default SH1

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

### -ApplicationType
Jenis Aplikasi, SAP-HANA default

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

### -BackupProtocolType
Array hashtable yang mewakili jenis protokol untuk volume Cadangan Data/Cadangan Log default NFSv4.1, untuk jenis volume lain nfsv4.1 akan digunakan.

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

### -CapacityOverhead
Overhead kapasitas %, Kuota tambahan yang disediakan untuk rekam jepret selama ukuran volume data praktik terbaik, default 50

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

### -DataBackupPerformance
Tentukan throughput dalam MiB/dtk.
Jika DataBackupPerformance yang di-ommit akan dihitung secara otomatis atau menentukan nilai bilangan bulat yang mewakili throughput.

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

### -DataBackupSize
Tentukan kapasitas (dalam GiB).
Jika DataSize yang di-ommit akan dihitung secara otomatis atau menentukan nilai bilangan bulat yang mewakili ukuran.

```yaml
Type: System.Nullable`1[System.Int64]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataPerformance
Tentukan throughput dalam MiB/dtk.
Jika DataPerformance yang di-ommit akan dihitung secara otomatis atau menentukan dan nilai bilangan bulat yang mewakili throughput.

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

### -DataSize
Tentukan kapasitas (dalam GiB).
Jika DataSize yang di-ommit akan dihitung secara otomatis atau menentukan nilai bilangan bulat yang mewakili ukuran.

```yaml
Type: System.Nullable`1[System.Int64]
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

### -DisasterRecoveryDestination
Membuat grup volume untuk DR, menggunakan Replikasi Lintas Wilayah ANF, skenario memungkinkan volume direplikasi antara wilayah yang berbeda menggunakan SnapMirror

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

### -ExportPolicy
Array hashtable yang mewakili kebijakan ekspor, yang seharusnya umum untuk semua volume.

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesVolumeExportPolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalPlacementRule
Aturan penempatan khusus aplikasi untuk grup volume

```yaml
Type: System.Collections.Generic.IList`1[Microsoft.Azure.Management.NetApp.Models.PlacementKeyValuePairs]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupDescription
Deskripsi Grup, contoh Utama untuk SH1-{HostId} (default)

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

### -HannaSystemReplication
Replikasi Sistem HANA (HSR): Replikasi antara instans SID yang sama pada host di wilayah yang sama, atau wilayah yang berbeda.
Ini bisa Scale-Up atau konfigurasi Scale-Out.

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

### -HostCount
Jumlah host SAP Hana.
Jumlah total host SAP Hana untuk skenario tunggal atau multiplehost.
Default ke 50 untuk pengaturan host tunggal.
Saat ini pada simpul maksimal 3 dapat dikonfigurasi.

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

### -Lokasi
Lokasi sumber daya

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogBackupPerformance
Tentukan throughput dalam MiB/dtk.
Jika LogBackupPerformance yang di-ommit akan dihitung secara otomatis atau menentukan nilai bilangan bulat yang mewakili throughput.

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

### -LogBackupSize
Tentukan kapasitas (dalam GiB).
Jika DataSize yang di-ommit akan dihitung secara otomatis atau menentukan nilai bilangan bulat yang mewakili ukuran.

```yaml
Type: System.Nullable`1[System.Int64]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogPerformance
Tentukan throughput dalam MiB/dtk.
Jika LogPerformance yang di-ommit akan dihitung secara otomatis atau menentukan dan nilai bilangan bulat yang mewakili throughput.

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

### -LogSize
Tentukan kapasitas (dalam GiB).
Jika LogSize yang di-ommit akan dihitung secara otomatis atau menentukan nilai bilangan bulat yang mewakili ukuran.

```yaml
Type: System.Nullable`1[System.Int64]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama ANF VolumeGroup, contoh SAP-HANA-SH00001.
Default ke SAP-HANA-{HostId}, di mana pola {HostId} dalam nama akan digantikan oleh ID host 5 digit yang dimulai pada 1 untuk Host tunggal dan dihitung untuk Beberapa host berikutnya, host

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: VolumeGroupName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeMemory
Memori simpul SAP (GiB), Memori pada host komputasi SAP

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

### -PoolName
Kumpulan kapasitas default untuk volume, gunakan kumpulan kapasitas jenis QoS manual

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

### -Awalan
Semua nama volume akan diawali dengan teks yang diberikan.
Nilai default untuk teks awalan bergantung pada peran sistem.
Untuk PRIMARY itu akan kosong dan HA itu akan menjadi "HA - "

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

### -ProximityPlacementGroup
Grup penempatan kedekatan default, untuk data, log, dan jika ada volume bersama, di semua grup volume.
Menentukan bahwa data, log, dan volume bersama akan dibuat dekat dengan VM

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

### -ResourceGroupName
Grup sumber daya ANF VolumeGroup

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedPerformance
Tentukan throughput dalam MiB/dtk.
Jika SharedPerformance yang di-ommit akan dihitung secara otomatis atau menentukan dan nilai bilangan bulat yang mewakili throughput.

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

### -SharedSize
Tentukan kapasitas (dalam GiB).
Jika SharedSize yang di-ommit akan dihitung secara otomatis atau menentukan nilai bilangan bulat yang mewakili ukuran.

```yaml
Type: System.Nullable`1[System.Int64]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartingHostId
Memulai ID Host SAP Hana.
ID Host 1 menunjukkan Host Master.
Volume Bersama, Pencadangan Data, dan Cadangan Log hanya disediakan untuk Host Master, yaitu HostID == 1.1

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

### -SubnetId
Subnet yang didelegasikan default, untuk semua grup volume

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

### -SystemRole
Peran sistem, sistem SAP Utama, Hana System Replication (HSR) atau tujuan DataRecovery untuk replikasi Lintas Wilayah (CRR) ANF

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
Hashtable yang mewakili tag sumber daya

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vnet
Jaringan virtual default, untuk semua grup volume

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesAccount

## OUTPUTS

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesVolumeGroupDetail

## NOTES

## RELATED LINKS

[Get-AzNetAppFilesVolumeGroup](./Get-AzNetAppFilesVolumeGroup.md)
 [New-AzNetAppFilesVolumeGroup](./New-AzNetAppFilesVolumeGroup.md)
 [Remove-AzNetAppFilesVolumeGroup](./Remove-AzNetAppFilesVolumeGroup.md)
 [New-AzNetAppFilesVolume](./New-AzNetAppFilesVolume.md)
 [Update-AzNetAppFilesVolume](./Update-AzNetAppFilesVolume.md)
 [Remove-AzNetAppFilesVolume](./Remove-AzNetAppFilesVolume.md)