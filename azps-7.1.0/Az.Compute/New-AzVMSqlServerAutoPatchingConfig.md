---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 7016BAA9-C25D-404E-9F75-2BE49FBF91A8
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmsqlserverautopatchingconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMSqlServerAutoPatchingConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMSqlServerAutoPatchingConfig.md
ms.openlocfilehash: 2447c67943f4dead9e2ff88f367713462346ed0c
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136737805"
---
# New-AzVMSqlServerAutoPatchingConfig

## SYNOPSIS
Membuat objek konfigurasi untuk patching otomatis pada komputer virtual.

## SYNTAX

```
New-AzVMSqlServerAutoPatchingConfig [-Enable] [-DayOfWeek <String>] [-MaintenanceWindowStartingHour <Int32>]
 [-MaintenanceWindowDuration <Int32>] [-PatchCategory <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVMSqlServerAutoPatchingConfig** membuat objek konfigurasi untuk patch otomatis pada komputer virtual.

## EXAMPLES

### Contoh 1: Buat objek konfigurasi untuk mengonfigurasi patching otomatis
```
PS C:\> $AutoPatchingConfig = New-AzVMSqlServerAutoPatchingConfig -Enable -DayOfWeek "Thursday" -MaintenanceWindowStartingHour 11 -MaintenanceWindowDuration 120 -PatchCategory "Important"
Enable                        : True
DayOfWeek                     : Thursday
MaintenanceWindowStartingHour : 11
MaintenanceWindowDuration     : 120
PatchCategory                 : Important
```

Perintah ini membuat objek konfigurasi untuk patching.
Perintah menentukan hari dalam seminggu dan menentukan jendela pemeliharaan.
Konfigurasi ini mengaktifkan patching yang menggunakan nilai ini.
Perintah menyimpan hasilnya dalam $AutoBackupConfig variabel.
Anda dapat menentukan item konfigurasi ini untuk cmdlet lain, seperti cmdlet Set-AzVMSqlServerExtension cmdlet.

## PARAMETERS

### -DayOfWeek
Menentukan hari dalam seminggu ketika pembaruan harus diinstal.
Nilai yang dapat diterima untuk parameter ini adalah:
- Minggu
- Senin
- Selasa
- Rabu
- Kamis
- Jumat
- Sabtu
- Sehari-hari

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Everyday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Aktifkan
Menunjukkan bahwa patch otomatis untuk mesin virtual telah diaktifkan.
Jika Anda mengaktifkan patching otomatis, cmdlet Windows Update ke dalam mode interaktif.
Jika Anda menonaktifkan patching otomatis, Windows Pengaturan pembaruan tidak berubah.

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

### -MaintenanceWindowDuration
Menentukan durasi, dalam menit, jendela pemeliharaan.
Patching otomatis menghindari melakukan tindakan yang bisa mempengaruhi ketersediaan mesin virtual di luar jendela itu.
Tentukan kelipatan 30 menit.

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

### -MaintenanceWindowStartingHour
Menentukan jam pada hari ketika jendela pemeliharaan dimulai.
Kali ini menentukan kapan pembaruan mulai diinstal.

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

### -PatchCategory
Menentukan apakah pembaruan penting harus disertakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Important

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Compute.AutoPatchingSettings

## CATATAN

## RELATED LINKS

[New-azvmSqlServerAutoBackupConfig](./New-AzVMSqlServerAutoBackupConfig.md)

[Set-AzVMSqlServerExtension](./Set-AzVMSqlServerExtension.md)


