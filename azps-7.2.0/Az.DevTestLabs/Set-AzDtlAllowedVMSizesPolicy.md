---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DevTestLabs.dll-Help.xml
Module Name: Az.DevTestLabs
ms.assetid: AAABDD1D-71BF-409C-B50B-9BE861D84229
online version: https://docs.microsoft.com/powershell/module/az.devtestlabs/set-azdtlallowedvmsizespolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevTestLabs/DevTestLabs/help/Set-AzDtlAllowedVMSizesPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevTestLabs/DevTestLabs/help/Set-AzDtlAllowedVMSizesPolicy.md
ms.openlocfilehash: dec1bb612be57a332bdf4d71d6d57efce2eb7c6d
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140237707"
---
# Set-AzDtlAllowedVMSizesPolicy

## SYNOPSIS
Mengatur kebijakan ukuran mesin virtual yang diperbolehkan dari sebuah lab di DevTest Labs.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.devtestlabs/set-azdtlallowedvmsizespolicy) untuk informasi terkini.

## SYNTAX

### Aktifkan (Default)
```
Set-AzDtlAllowedVMSizesPolicy [[-VmSizes] <String[]>] [-Enable] [-LabName] <String>
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Disable
```
Set-AzDtlAllowedVMSizesPolicy [[-VmSizes] <String[]>] [-Disable] [-LabName] <String>
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzDtlAllowedVMSizesPolicy** menetapkan kebijakan ukuran mesin virtual yang diperbolehkan, yang menentukan daftar ukuran mesin virtual yang diperbolehkan di sebuah lab.
Cmdlet menggunakan grup sumber daya tertentu dan nama lab untuk menetapkan kebijakan tersebut.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Set-AzDtlAllowedVMSizesPolicy -LabName debtestlab -ResourceGroupName yuzhi-rg

Name               : AllowedVmSizesInLab
Type               : Microsoft.DevTestLab/labs/policySets/policies
Tags               : 
Id                 : /subscriptions/0b1f6471-1bf0-4dda-aec3-cb9272f09590/resourcegroups/yuzhi-rg/providers/microsoft.devtestlab/labs/debte
                     stlab/policysets/default/policies/allowedvmsizesinlab
Location           : 
Fact Name          : LabVmSize
Threshold          : ["Basic_A0"]
Evaluator Type     : AllowedValuesPolicy
Description        : 
Status             : Enabled
Provisioning State : 
```
Mengatur kebijakan ukuran mesin virtual yang diperbolehkan dari sebuah lab di DevTest Labs.


## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Disable
Mengindikasikan bahwa cmdlet ini menonaktifkan kebijakan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Disable
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Aktifkan
Mengindikasikan bahwa cmdlet ini mengaktifkan kebijakan tersebut.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enable
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LabName
Menentukan nama lab tempat cmdlet ini menetapkan kebijakan ukuran mesin virtual.

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

### -ResourceGroupName
Menentukan nama grup sumber daya tempat lab dimiliki.

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

### -VmSizes
Menentukan, sebagai array string, daftar ukuran mesin virtual yang diperbolehkan di lab.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DevTestLabs.Models.PSPolicy

## CATATAN

## RELATED LINKS

[Get-AzDtlAllowedVMSizesPolicy](./Get-AzDtlAllowedVMSizesPolicy.md)


