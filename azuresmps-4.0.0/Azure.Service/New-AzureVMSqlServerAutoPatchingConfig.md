---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 7317DAC1-B535-4650-86BF-73E96F61EECD
online version: ''
schema: 2.0.0
ms.openlocfilehash: 3a88889cabf884e4f1f6b5a8272cb8b3bdf0033a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141816534"
---
# New-AzureVMSqlServerAutoPatchingConfig

## SYNOPSIS
Membuat objek konfigurasi untuk patch otomatis mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureVMSqlServerAutoPatchingConfig [-Enable] [-DayOfWeek <String>] [-MaintenanceWindowStartingHour <Int32>]
 [-MaintenanceWindowDuration <Int32>] [-PatchCategory <String>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureVMSqlServerAutoPatchingConfig** membuat objek konfigurasi untuk patch otomatis mesin virtual.

## EXAMPLES

### Contoh 1: Membuat objek konfigurasi untuk mengonfigurasi patching otomatis
```
PS C:\> $APS = New-AzureVMSqlServerAutoPatchingConfig -Enable -DayOfWeek "Thursday" -MaintenanceWindowStartingHour 11 -MaintenanceWindowDuration 120 -PatchCategory "Important"
          Enable                        : True
          DayOfWeek                     : Thursday
          MaintenanceWindowStartingHour : 11
          MaintenanceWindowDuration     : 120
          PatchCategory                 : Important
```

Perintah ini membuat objek konfigurasi yang dapat digunakan untuk mengonfigurasi patching otomatis menggunakan Set-AzureVMSqlServerExtension.

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
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Aktifkan
Menunjukkan bahwa patch otomatis untuk mesin virtual diaktifkan.
Jika Anda mengaktifkan patch otomatis cmdlet akan menempatkan Windows Update ke mode interaktif.
Jika Anda menonaktifkan patch otomatis, pengaturan Windows Update tidak akan berubah.

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

### -InformationAction
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaintenanceWindowDuration
Menentukan durasi jendela pemeliharaan.
Patch otomatis akan menghindari melakukan tindakan yang dapat memengaruhi ketersediaan mesin virtual di luar jendela tersebut.
Hanya 30 menit kenaikan yang diperbolehkan.

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
Menentukan jam hari ketika jendela pemeliharaan dimulai.
Waktu ini menentukan kapan pembaruan mulai diinstal dan dibulatkan ke jam.

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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### AutoPatchingSettings
Cmdlet ini mengembalikan objek berisi pengaturan untuk patch otomatis.

## CATATAN

## RELATED LINKS

[Set-AzureVMSqlServerExtension](./Set-AzureVMSqlServerExtension.md)

[Remove-AzureVMSqlServerExtension](./Remove-AzureVMSqlServerExtension.md)

[Set-AzureVMSqlServerExtension](./Set-AzureVMSqlServerExtension.md)


