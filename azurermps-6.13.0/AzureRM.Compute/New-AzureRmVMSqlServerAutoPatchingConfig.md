---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 7016BAA9-C25D-404E-9F75-2BE49FBF91A8
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/new-azurermvmsqlserverautopatchingconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/New-AzureRmVMSqlServerAutoPatchingConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/New-AzureRmVMSqlServerAutoPatchingConfig.md
ms.openlocfilehash: ab10ac7b48eac782657af6212e178afbd7b710c5
ms.sourcegitcommit: ea4f0db405efec935ac72601b51807dbb45674c9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/28/2022
ms.locfileid: "132415411"
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Compute.AutoPatchingSettings

## CATATAN

## RELATED LINKS


[Set-AzureRmVMSqlServerExtension](./Set-AzureRMVMSqlServerExtension.md)


