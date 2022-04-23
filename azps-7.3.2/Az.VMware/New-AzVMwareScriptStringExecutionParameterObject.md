---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareScriptStringExecutionParameterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptStringExecutionParameterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptStringExecutionParameterObject.md
ms.openlocfilehash: 887a6a1f34dbd042353154ccd3a810534c0fb563
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143068931"
---
# New-AzVMwareScriptStringExecutionParameterObject

## SYNOPSIS
Membuat objek dalam memori untuk ScriptStringExecutionParameter

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.vmware/new-azvmwarescriptstringexecutionparameterobject) untuk informasi terbaru.

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

Membuat objek Skrip Skrip Eksekusi String lokal

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
Nilai untuk parameter yang dilewati.

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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.ScriptStringExecutionParameter

## NOTES

ALIAS

## RELATED LINKS

