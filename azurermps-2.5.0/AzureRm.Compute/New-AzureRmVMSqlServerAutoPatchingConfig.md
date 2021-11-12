---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 7016BAA9-C25D-404E-9F75-2BE49FBF91A8
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/new-azurermvmsqlserverautopatchingconfig
schema: 2.0.0
ms.openlocfilehash: 9cc694591bb7107978f0ce4f90dc11f2a3d584044fa15381628a5c38294554fc
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417368"
---
# New-AzureRmVMSqlServerAutoPatchingConfig

## SYNOPSIS
Membuat objek konfigurasi untuk patching otomatis pada komputer virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmVMSqlServerAutoPatchingConfig [-Enable] [-DayOfWeek <String>]
 [-MaintenanceWindowStartingHour <Int32>] [-MaintenanceWindowDuration <Int32>] [-PatchCategory <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmVMSqlServerAutoPatchingConfig** membuat objek konfigurasi untuk patch otomatis pada komputer virtual.

## EXAMPLES

### Contoh 1: Buat objek konfigurasi untuk mengonfigurasi patching otomatis
```
PS C:\> $AutoPatchingConfig = New-AzureRmVMSqlServerAutoPatchingConfig -Enable -DayOfWeek "Thursday" -MaintenanceWindowStartingHour 11 -MaintenanceWindowDuration 120 -PatchCategory "Important"
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
Anda dapat menentukan item konfigurasi ini untuk cmdlet lain, seperti cmdlet Set-AzureRmVMSqlServerExtension cmdlet.

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
Type: String
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
Type: SwitchParameter
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
Type: Int32
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
Type: Int32
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
Type: String
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### AutoPatchingSettings
Cmdlet ini mengembalikan objek berisi pengaturan untuk patching otomatis.

## CATATAN

## RELATED LINKS



[Set-AzureRmVMSqlServerExtension](./Set-AzureRMVMSqlServerExtension.md)


