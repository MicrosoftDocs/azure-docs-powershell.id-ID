---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DevTestLabs.dll-Help.xml
Module Name: Az.DevTestLabs
ms.assetid: 5029179A-99A5-4350-A8E5-D15ABA59CC93
online version: https://docs.microsoft.com/powershell/module/az.devtestlabs/get-azdtlvmsperuserpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevTestLabs/DevTestLabs/help/Get-AzDtlVMsPerUserPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DevTestLabs/DevTestLabs/help/Get-AzDtlVMsPerUserPolicy.md
ms.openlocfilehash: b63f5c4389fe31e77143763a68ae7402f0cd24f3
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138279820"
---
# Get-AzDtlVMsPerUserPolicy

## SYNOPSIS
Dapatkan mesin virtual per kebijakan pengguna sebuah lab di DevTest Labs.

## SYNTAX

```
Get-AzDtlVMsPerUserPolicy [-LabName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDtlVMsPerUserPolicy** mendapatkan kebijakan mesin virtual per pengguna lab, yang memungkinkan Anda untuk mengatur jumlah maksimum mesin virtual yang diperbolehkan per pengguna.
Cmdlet mengembalikan status kebijakan yang diaktifkan atau dinonaktifkan dan jumlah maksimum mesin virtual yang diperbolehkan per pengguna yang Telah Anda tetapkan dalam kebijakan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzDtlVMsPerUserPolicy -LabName debtestlab -ResourceGroupName yuzhi-rg

Name               : MaxVmsAllowedPerUser
Type               : Microsoft.DevTestLab/labs/policySets/policies
Tags               : 
Id                 : /subscriptions/0b1f6471-1bf0-4dda-aec3-cb9272f09590/resourcegroups/yuzhi-rg/providers/microsoft.devtestlab/labs/debte
                     stlab/policysets/default/policies/maxvmsallowedperuser
Location           : 
Fact Name          : UserOwnedLabVmCount
Threshold          : 1
Evaluator Type     : MaxValuePolicy
Description        : 
Status             : Enabled
Provisioning State : 
```
Dapatkan mesin virtual per kebijakan pengguna sebuah lab di DevTest Labs.


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

### -LabName
Menentukan nama lab tempat cmdlet ini mendapatkan komputer virtual per kebijakan pengguna.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DevTestLabs.Models.PSPolicy

## CATATAN

## RELATED LINKS

[Set-azdtlvMsPerUserPolicy](./Set-AzDtlVMsPerUserPolicy.md)


