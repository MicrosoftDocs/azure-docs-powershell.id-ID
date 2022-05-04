---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DevTestLabs.dll-Help.xml
Module Name: Az.DevTestLabs
ms.assetid: 869167AA-54F8-4A1C-AC08-5555A63EE1BC
online version: https://docs.microsoft.com/powershell/module/az.devtestlabs/get-azdtlallowedvmsizespolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevTestLabs/DevTestLabs/help/Get-AzDtlAllowedVMSizesPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevTestLabs/DevTestLabs/help/Get-AzDtlAllowedVMSizesPolicy.md
ms.openlocfilehash: ad8fd49aac416fa5612c790724b31e7bd93f3311
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144627312"
---
# Get-AzDtlAllowedVMSizesPolicy

## SYNOPSIS
Mendapatkan kebijakan ukuran komputer virtual yang diizinkan dari lab di DevTest Labs.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.devtestlabs/get-azdtlallowedvmsizespolicy) untuk informasi terbaru.

## SYNTAX

```
Get-AzDtlAllowedVMSizesPolicy [-LabName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDtlAllowedVMSizesPolicy** mendapatkan kebijakan ukuran komputer virtual yang diizinkan, yang memungkinkan Anda menentukan daftar ukuran komputer virtual yang diizinkan di lab.
Cmdlet mengembalikan status kebijakan yang diaktifkan atau dinonaktifkan dan daftar semua ukuran komputer virtual yang diizinkan yang telah Anda tetapkan dalam kebijakan yang ditentukan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzDtlAllowedVMSizesPolicy -LabName debtestlab -ResourceGroupName yuzhi-rg
```

```output
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
Mendapatkan kebijakan ukuran komputer virtual yang diizinkan dari lab di DevTest Labs.


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
Menentukan nama lab yang cmdlet ini mendapatkan kebijakan ukuran komputer virtual.

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

[Set-AzDtlAllowedVMSizesPolicy](./Set-AzDtlAllowedVMSizesPolicy.md)


