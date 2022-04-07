---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 7016BAA9-C25D-404E-9F75-2BE49FBF91A8
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmsqlserverautopatchingconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMSqlServerAutoPatchingConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMSqlServerAutoPatchingConfig.md
ms.openlocfilehash: 64518555942f84d87a495fd611e4618e64b38542
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140386919"
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
```powershell
$AutoPatchingConfig = New-AzVMSqlServerAutoPatchingConfig -Enable -DayOfWeek "Thursday" -MaintenanceWindowStartingHour 11 -MaintenanceWindowDuration 120 -PatchCategory "Important"
```

```output
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
Jika Anda mengaktifkan patching otomatis, cmdlet meletakkan Windows Update ke dalam mode interaktif.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Compute.AutoPatchingSettings

## CATATAN

## RELATED LINKS

[New-azvmSqlServerAutoBackupConfig](./New-AzVMSqlServerAutoBackupConfig.md)

[Set-AzVMSqlServerExtension](./Set-AzVMSqlServerExtension.md)


