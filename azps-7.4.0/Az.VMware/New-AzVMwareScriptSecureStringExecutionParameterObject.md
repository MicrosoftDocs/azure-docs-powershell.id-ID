---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareScriptSecureStringExecutionParameterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptSecureStringExecutionParameterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptSecureStringExecutionParameterObject.md
ms.openlocfilehash: 8ac4048ec5adde3f2e24fed651a95a107e06c203
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143056295"
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

### Contoh 1: Membuat objek Skrip Lokal Eksekusi String Aman
```powershell
New-AzVMwareScriptSecureStringExecutionParameterObject -Name azps_test_securevalue -SecureValue "passwordValue"
```
```output
Name                  Type        SecureValue
----                  ----        -----------
azps_test_securevalue SecureValue passwordValue
```

Membuat objek Skrip Lokal Eksekusi String Aman

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
Nilai aman untuk parameter yang dilewati, tidak disimpan dalam log.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.ScriptSecureStringExecutionParameter

## NOTES

ALIAS

## RELATED LINKS

