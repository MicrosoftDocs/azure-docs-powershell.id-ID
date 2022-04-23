---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 7016BAA9-C25D-404E-9F75-2BE49FBF91A8
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmsqlserverautopatchingconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMSqlServerAutoPatchingConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMSqlServerAutoPatchingConfig.md
ms.openlocfilehash: 64518555942f84d87a495fd611e4618e64b38542
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143231021"
---
# New-AzVMSqlServerAutoPatchingConfig

## SYNOPSIS
Membuat objek konfigurasi untuk patch otomatis pada mesin virtual.

## SYNTAX

```
New-AzVMSqlServerAutoPatchingConfig [-Enable] [-DayOfWeek <String>] [-MaintenanceWindowStartingHour <Int32>]
 [-MaintenanceWindowDuration <Int32>] [-PatchCategory <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVMSqlServerAutoPatchingConfig** membuat objek konfigurasi untuk patching otomatis pada mesin virtual.

## EXAMPLES

### Contoh 1: Membuat objek konfigurasi untuk mengonfigurasi patching otomatis
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
Konfigurasi ini memungkinkan patch yang menggunakan nilai ini.
Perintah menyimpan hasil dalam variabel $AutoBackupConfig.
Anda dapat menentukan item konfigurasi ini untuk cmdlet lain, seperti cmdlet Set-AzVMSqlServerExtension.

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
- Everyday

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
Menunjukkan bahwa patch otomatis untuk mesin virtual diaktifkan.
Jika Anda mengaktifkan patch otomatis cmdlet menempatkan Windows Update ke mode interaktif.
Jika Anda menonaktifkan patch otomatis, pengaturan Windows Update tidak berubah.

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
Menentukan durasi, dalam menit, dari jendela pemeliharaan.
Patch otomatis menghindari melakukan tindakan yang dapat mempengaruhi ketersediaan mesin virtual di luar jendela tersebut.
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
Menentukan jam hari ketika jendela pemeliharaan dimulai.
Waktu ini menentukan kapan pembaruan mulai diinstal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Compute.AutoPatchingSettings

## NOTES

## RELATED LINKS

[New-AzVMSqlServerAutoBackupConfig](./New-AzVMSqlServerAutoBackupConfig.md)

[Set-AzVMSqlServerExtension](./Set-AzVMSqlServerExtension.md)


