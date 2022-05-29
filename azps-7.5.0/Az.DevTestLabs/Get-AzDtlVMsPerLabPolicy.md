---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DevTestLabs.dll-Help.xml
Module Name: Az.DevTestLabs
ms.assetid: A3F653C7-6F9D-4B2B-81F8-0A012D80ECC7
online version: https://docs.microsoft.com/powershell/module/az.devtestlabs/get-azdtlvmsperlabpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevTestLabs/DevTestLabs/help/Get-AzDtlVMsPerLabPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevTestLabs/DevTestLabs/help/Get-AzDtlVMsPerLabPolicy.md
ms.openlocfilehash: 2cd434ba1c9c087cbbd54ccc5800b4a88b32ced0
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145742734"
---
# Get-AzDtlVMsPerLabPolicy

## SYNOPSIS
Mendapatkan komputer virtual per kebijakan lab lab di DevTest Labs.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.devtestlabs/get-azdtlvmsperlabpolicy) untuk informasi terbaru.

## SYNTAX

```
Get-AzDtlVMsPerLabPolicy [-LabName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDtlVMsPerLabPolicy** mendapatkan komputer virtual per kebijakan lab lab, yang memungkinkan Anda mengatur jumlah total komputer virtual yang diizinkan di laboratorium.
Cmdlet mengembalikan status kebijakan yang diaktifkan atau dinonaktifkan, dan jumlah total komputer virtual yang diizinkan di lab yang telah Anda tetapkan dalam kebijakan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzDtlVMsPerLabPolicy -LabName debtestlab -ResourceGroupName yuzhi-rg
```

```output
Name               : MaxVmsAllowedPerLab
Type               : Microsoft.DevTestLab/labs/policySets/policies
Tags               : 
Id                 : /subscriptions/0b1f6471-1bf0-4dda-aec3-cb9272f09590/resourcegroups/yuzhi-rg/providers/microsoft.devtestlab/labs/debte
                     stlab/policysets/default/policies/maxvmsallowedperlab
Location           : 
Fact Name          : LabVmCount
Threshold          : 1
Evaluator Type     : MaxValuePolicy
Description        : 
Status             : Enabled
Provisioning State : 
```
Mendapatkan komputer virtual per kebijakan lab lab di DevTest Labs.


## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -LabName
Menentukan nama lab tempat cmdlet ini mendapatkan komputer virtual.

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
Menentukan nama grup sumber daya tempat lab berada.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DevTestLabs.Models.PSPolicy

## NOTES

## RELATED LINKS

[Set-AzDtlVMsPerLabPolicy](./Set-AzDtlVMsPerLabPolicy.md)


