---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareScriptStringExecutionParameterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptStringExecutionParameterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptStringExecutionParameterObject.md
ms.openlocfilehash: 022386e36067f16cbbf46028abe0941f68d49f29
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136562604"
---
# New-AzVMwareScriptStringExecutionParameterObject

## SYNOPSIS
Membuat objek dalam memori untuk ScriptStringExecutionParameter

## SYNTAX

```
New-AzVMwareScriptStringExecutionParameterObject -Name <String> [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ScriptStringExecutionParameter

## EXAMPLES

### Contoh 1: Membuat objek Eksekusi String Skrip lokal
```powershell
PS C:\> New-AzVMwareScriptStringExecutionParameterObject -Name azps_test_stringvalue -Value "stringValue"

Name                  Type   Value
----                  ----   -----
azps_test_stringvalue Value  stringValue
```

Membuat objek Eksekusi String Skrip lokal

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

### -Value
Nilai untuk parameter yang lolos.

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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20210601.ScriptStringExecutionParameter

## CATATAN

ALIAS

## RELATED LINKS

