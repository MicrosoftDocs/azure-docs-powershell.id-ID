---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwarePSCredentialExecutionParameterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwarePSCredentialExecutionParameterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwarePSCredentialExecutionParameterObject.md
ms.openlocfilehash: 6fd9f5bc57d7b1e150b634cbf260207ee4c679ec
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136381273"
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
PS C:\> New-AzVMwarePSCredentialExecutionParameterObject -Name azps_test_credentialvalue -Password "passwordValue" -Username "usernameValue"

Name                      Type       Password      Username
----                      ----       --------      --------
azps_test_credentialvalue Credential passwordValue usernameValue
```

Membuat objek Eksekusi Kredensial PS lokal

## PARAMETERS

### -Nama
Nama parameter.

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

### -Password
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20210601.PsCredentialExecutionParameter

## CATATAN

ALIAS

## RELATED LINKS

