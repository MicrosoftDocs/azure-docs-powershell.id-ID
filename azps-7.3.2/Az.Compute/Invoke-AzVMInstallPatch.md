---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/invoke-azvminstallpatch
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Invoke-AzVMInstallPatch.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Invoke-AzVMInstallPatch.md
ms.openlocfilehash: b1222ba2a375db8a5da2a739bf84acfd122c7b23
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142072525"
---
# Invoke-AzVMInstallPatch

## SYNOPSIS
Menginstal patch pada VM

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/invoke-azvminstallpatch) untuk informasi terbaru.

## SYNTAX

### WindowsDefaultParameterSet (Default)
```
Invoke-AzVMInstallPatch -ResourceGroupName <String> -VMName <String> [-Windows] -RebootSetting <String>
 -MaximumDuration <String> [-KBNumberToInclude <String[]>] [-KBNumberToExclude <String[]>]
 [-ExcludeKBsRequiringReboot] [-ClassificationToIncludeForWindows <String[]>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LinuxDefaultParameterSet
```
Invoke-AzVMInstallPatch -ResourceGroupName <String> -VMName <String> [-Linux] -RebootSetting <String>
 -MaximumDuration <String> [-PackageNameMaskToInclude <String[]>] [-PackageNameMaskToExclude <String[]>]
 [-ClassificationToIncludeForLinux <String[]>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### WindowsResourceIDParameterSet
```
Invoke-AzVMInstallPatch -ResourceId <String> [-Windows] -RebootSetting <String> -MaximumDuration <String>
 [-KBNumberToInclude <String[]>] [-KBNumberToExclude <String[]>] [-ExcludeKBsRequiringReboot]
 [-ClassificationToIncludeForWindows <String[]>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### LinuxResourceIDParameterSet
```
Invoke-AzVMInstallPatch -ResourceId <String> [-Linux] -RebootSetting <String> -MaximumDuration <String>
 [-PackageNameMaskToInclude <String[]>] [-PackageNameMaskToExclude <String[]>]
 [-ClassificationToIncludeForLinux <String[]>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### WindowsInputObjectParameterSet
```
Invoke-AzVMInstallPatch [-VM] <PSVirtualMachine> [-Windows] -RebootSetting <String> -MaximumDuration <String>
 [-KBNumberToInclude <String[]>] [-KBNumberToExclude <String[]>] [-ExcludeKBsRequiringReboot]
 [-ClassificationToIncludeForWindows <String[]>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### LinuxInputObjectParameterSet
```
Invoke-AzVMInstallPatch [-VM] <PSVirtualMachine> [-Linux] -RebootSetting <String> -MaximumDuration <String>
 [-PackageNameMaskToInclude <String[]>] [-PackageNameMaskToExclude <String[]>]
 [-ClassificationToIncludeForLinux <String[]>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menginstal patch pada VM

## EXAMPLES

### Contoh 1
```powershell
Invoke-AzVmInstallPatch -ResourceGroupName 'MyRG' -VmName 'MyVM' -Windows -RebootSetting 'never' -MaximumDuration PT2H -ClassificationToIncludeForWindows Critical
```

Contoh ini menginstal patch penting pada VM. 

### Contoh 2
```powershell
$myVM = Get-AzVM -ResourceGroupName 'MyRG' -Name 'MyVM'
Invoke-AzVmInstallPatch -VM $myVM -MaximumDuration "PT90M" -RebootSetting "Always" -Windows -ClassificationToIncludeForWindows "Security" -KBNumberToInclude ["KB1234567", "KB123567"] -KBNumberToExclude ["KB1234702", "KB1234802"] -ExcludeKBsRequiringReboot
```

Contoh ini melewati objek PSVirtualMachine ke parameter '-VM'. Ini juga menginstal patch keamanan sambil menyertakan dan tidak termasuk KB tertentu dengan menggunakan '-KBNumberToExclude' dan '-KBNumberToInclude'. Ini juga tidak termasuk KB yang mengharuskan boot ulang dengan menggunakan '-ExcludeKBsRequiringReboot'.

### Contoh 3
```powershell
$myLinuxVM = Get-AzVM -ResourceGroupName 'MyRG' -Name 'MyLinuxVM'
Invoke-AzVMInstallPatch -ResourceId $myLinuxVM.id -MaximumDuration "PT90M" -RebootSetting "Always" -Linux -ClassificationToIncludeForLinux "Security" -PackageNameMaskToInclude ["package123"] -PackageNameMaskToExclude ["package567"]
```

Contoh ini menginstal paket tertentu ke VM Linux yang disediakan oleh RESOURCE ID. 

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

### -ClassificationToIncludeForLinux
Klasifikasi pembaruan untuk dipilih saat menginstal patch.
Nilai yang mungkin berbeda untuk Windows dan Linux.

```yaml
Type: System.String[]
Parameter Sets: LinuxDefaultParameterSet, LinuxResourceIDParameterSet, LinuxInputObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClassificationToIncludeForWindows
Klasifikasi pembaruan untuk dipilih saat menginstal patch.
Nilai yang mungkin berbeda untuk Windows dan Linux.

```yaml
Type: System.String[]
Parameter Sets: WindowsDefaultParameterSet, WindowsResourceIDParameterSet, WindowsInputObjectParameterSet
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

### -ExcludeKBsRequiringReboot
Memfilter KB yang tidak memiliki perilaku boot ulang 'NeverReboots' saat ini diatur.
Parameter ini hanya tersedia untuk Windows VM.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WindowsDefaultParameterSet, WindowsResourceIDParameterSet, WindowsInputObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KBNumberToExclude
KB untuk dikecualikan dalam operasi patch.
Parameter ini hanya tersedia untuk Windows VM.

```yaml
Type: System.String[]
Parameter Sets: WindowsDefaultParameterSet, WindowsResourceIDParameterSet, WindowsInputObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KBNumberToInclude
KB untuk disertakan dalam operasi patch.
Parameter ini hanya tersedia untuk Windows VM.

```yaml
Type: System.String[]
Parameter Sets: WindowsDefaultParameterSet, WindowsResourceIDParameterSet, WindowsInputObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Linux
Untuk Linux VM

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LinuxDefaultParameterSet, LinuxResourceIDParameterSet, LinuxInputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumDuration
Menentukan jumlah waktu maksimum operasi yang akan dijalankan.
String durasi yang sesuai dengan ISO 8601 seperti PT2H (2 jam).

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

### -PackageNameMaskToExclude
Paket untuk dikecualikan dalam operasi patch.
Format: packageName_packageVersion.
Parameter ini hanya tersedia untuk Linux VM.

```yaml
Type: System.String[]
Parameter Sets: LinuxDefaultParameterSet, LinuxResourceIDParameterSet, LinuxInputObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageNameMaskToInclude
Paket untuk disertakan dalam operasi patch.
Format: packageName_packageVersion.
Parameter ini hanya tersedia untuk Linux VM.

```yaml
Type: System.String[]
Parameter Sets: LinuxDefaultParameterSet, LinuxResourceIDParameterSet, LinuxInputObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RebootSetting
Menentukan kapan VM dapat diterima untuk memulai ulang selama operasi pembaruan perangkat lunak.

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
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: WindowsDefaultParameterSet, LinuxDefaultParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya untuk mesin virtual Anda.

```yaml
Type: System.String
Parameter Sets: WindowsResourceIDParameterSet, LinuxResourceIDParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VM
Objek Mesin Virtual PowerShell

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: WindowsInputObjectParameterSet, LinuxInputObjectParameterSet
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMName
Nama Mesin Virtual

```yaml
Type: System.String
Parameter Sets: WindowsDefaultParameterSet, LinuxDefaultParameterSet
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Windows
Untuk Windows VM

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WindowsDefaultParameterSet, WindowsResourceIDParameterSet, WindowsInputObjectParameterSet
Aliases:

Required: True
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

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineInstallPatchesResult

## CATATAN

## RELATED LINKS
