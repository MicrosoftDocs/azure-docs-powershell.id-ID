---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Maintenance.dll-Help.xml
Module Name: Az.Maintenance
online version: https://docs.microsoft.com/powershell/module/az.maintenance/new-azmaintenanceconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maintenance/Maintenance/help/New-AzMaintenanceConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maintenance/Maintenance/help/New-AzMaintenanceConfiguration.md
ms.openlocfilehash: 6c2eb8aaff33650e61940bbd4e08500e19481f95
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142488869"
---
# New-AzMaintenanceConfiguration

## SYNOPSIS
Membuat atau Memperbarui catatan konfigurasi

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.maintenance/new-azmaintenanceconfiguration) untuk informasi terbaru.

## SYNTAX

```
New-AzMaintenanceConfiguration [-ResourceGroupName] <string> [-Name] <string> [-Location] <string> [-Tag <hashtable>]
    [-ExtensionProperty <hashtable>] [-MaintenanceScope <string>] [-StartDateTime <string>] [-ExpirationDateTime <string>]
    [-Timezone <string>] [-Duration <timespan>] [-Visibility <string>] [-RecurEvery <string>]
    [-LinuxParameterPackageNameMaskToInclude <HashSet[string]>] [-LinuxParameterPackageNameMaskToExclude <HashSet[string]>]
    [-LinuxParameterClassificationToInclude <HashSet[string]>] [-WindowParameterKbNumberToInclude <HashSet[string]>]
    [-WindowParameterKbNumberToExclude <HashSet[string]>] [-WindowParameterClassificationToInclude <HashSet[string]>]
    [-WindowParameterExcludeKbRequiringReboot <bool>] [-PreTask <string>] [-PostTask <string>] [-InstallPatchRebootSetting
    <string>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau Memperbarui catatan konfigurasi

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzMaintenanceConfiguration -ResourceGroupName smdtest -Name workervmscentralus -MaintenanceScope Host -Location centralus -StartDateTime 2020-08-01 00:00 -ExpirationDateTime 2021-08-04 00:00 -TimeZone Pacific Standard Time -Duration 05:00 -RecurEvery Day


Location            : centralus
Tags                : {}
ExtensionProperties : {}
MaintenanceScope    : Host
StartDateTime       : 2020-08-01 00:00
ExpirationDateTime  : 2021-08-04 00:00
TimeZone            : Pacific Standard Time
RecurEvery          : Day
Duration            : 05:00
MaintenanceScope    : Host
Visibility          : Custom
Id                  : /subscriptions/42c974dd-2c03-4f1b-96ad-b07f050aaa74/resourcegroups/smdtest/providers/Microsoft.Maintenance/maintenanceConfigurations/workervmscentralus
Name                : workervmscentralus
Type                : Microsoft.Maintenance/maintenanceConfigurations
```

Membuat konfigurasi pemeliharaan dengan lingkup Host

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -Durasi
Durasi


```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpirationDateTime
TanggalDaluwarsa dari jadwal dalam format YYYY-MM-DD hh:mm

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

### -ExtensionProperty
Properti Ekstensi per sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallPatchRebootSetting
Instal Patch Opsi Boot Ulang. Nilai yang diizinkan Tidak Pernah, Jika Diperlukan, Selalu

```yaml
Type: string
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinuxParameterClassificationToInclude
Daftar klasifikasi patch linux

```yaml
Type: HashSet[string]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinuxParameterPackageNameMaskToExclude
Daftar paket yang akan dikecualikan selama operasi patch vm

```yaml
Type: HashSet[string]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinuxParameterPackageNameMaskToInclude
Daftar paket yang disertakan selama operasi patch vm

```yaml
Type: HashSet[string]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi konfigurasi pemeliharaan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaintenanceScope
Lingkup Pemeliharaan.

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

### -Nama
Nama konfigurasi pemeliharaan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PreTask
Daftar tugas yang dijalankan sebelum jadwal. misalnya [{'source' :'runbook', 'taskScope': 'Resource', 'parameters': { 'arg1': 'value1'}}]

```yaml
Type: string
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PostTask
Daftar tugas yang dijalankan setelah jadwal. misalnya [{'source' :'runbook', 'taskScope': 'Resource', 'parameters': { 'arg1': 'value1'}}]

```yaml
Type: string
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurEvery
Pengulangan jadwal

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

### -ResourceGroupName
Nama Grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartDateTime
StartDateTime dari jadwal dalam format YYYY-MM-DD hh:mm

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
The ARM Tags.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zona waktu
Zona waktu

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

### -Visibilitas
Visibilitas lingkup

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

### -WindowParameterClassificationToInclude
Daftar klasifikasi patch windows

```yaml
Type: HashSet[string]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowParameterExcludeKbRequiringReboot
Tidak termasuk KB yang memerlukan boot ulang

```yaml
Type: bool
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowParameterKbNumberToExclude
Daftar KB yang akan dikecualikan selama operasi patch vm

```yaml
Type: HashSet[string]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowParameterKbNumberToInclude
Daftar KB yang disertakan selama operasi patch vm

```yaml
Type: HashSet[string]
Parameter Sets: (All)
Aliases:

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Maintenance.Models.PSMaintenanceConfiguration

## CATATAN

## RELATED LINKS
