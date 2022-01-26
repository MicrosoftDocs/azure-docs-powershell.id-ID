---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareScriptSecureStringExecutionParameterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptSecureStringExecutionParameterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptSecureStringExecutionParameterObject.md
ms.openlocfilehash: 228f5754ad828bc524eca75bc2edb59b41971f79
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136742410"
---
# New-AzVMwareScriptSecureStringExecutionParameterObject

## SYNOPSIS
Membuat objek dalam memori untuk ScriptSecureStringExecutionParameter

## SYNTAX

```
New-AzVMwareScriptSecureStringExecutionParameterObject -Name <String> [-SecureValue <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ScriptSecureStringExecutionParameter

## EXAMPLES

### Contoh 1: Membuat objek Eksekusi String Aman Skrip lokal
```powershell
PS C:\> New-AzVMwareScriptSecureStringExecutionParameterObject -Name azps_test_securevalue -SecureValue "passwordValue"

Name                  Type        SecureValue
----                  ----        -----------
azps_test_securevalue SecureValue passwordValue
```

Membuat objek Eksekusi String Aman Skrip lokal

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

### -SecureValue
Nilai aman untuk parameter yang lolos, tidak akan disimpan dalam log.

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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20210601.ScriptSecureStringExecutionParameter

## CATATAN

ALIAS

## RELATED LINKS

