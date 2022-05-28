---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwarePSCredentialExecutionParameterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwarePSCredentialExecutionParameterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwarePSCredentialExecutionParameterObject.md
ms.openlocfilehash: a27c7e19ad90e2a82d4625dccb1942e02729b7ca
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145553303"
---
# New-AzVMwarePSCredentialExecutionParameterObject

## SYNOPSIS
Membuat objek dalam memori untuk PSCredentialExecutionParameter

## SYNTAX

```
New-AzVMwarePSCredentialExecutionParameterObject -Name <String> [-Password <String>] [-Username <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk PSCredentialExecutionParameter

## EXAMPLES

### Contoh 1: Membuat objek Eksekusi Kredensial PS lokal
```powershell
New-AzVMwarePSCredentialExecutionParameterObject -Name azps_test_credentialvalue -Password "passwordValue" -Username "usernameValue"
```
```output
Name                      Type       Password      Username
----                      ----       --------      --------
azps_test_credentialvalue Credential passwordValue usernameValue
```

Membuat objek Eksekusi Kredensial PS lokal

## PARAMETERS

### -Name
Nama parameternya.

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

### -Kata sandi
kata sandi untuk masuk.

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

### -Nama pengguna
nama pengguna untuk masuk.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.PsCredentialExecutionParameter

## NOTES

ALIAS

## RELATED LINKS

