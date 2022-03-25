---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareScriptStringExecutionParameterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptStringExecutionParameterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptStringExecutionParameterObject.md
ms.openlocfilehash: bdfee05009ffd1b0418cd507bb95d0e017087e69
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140080865"
---
# New-AzVMwareScriptStringExecutionParameterObject

## SYNOPSIS
Membuat objek dalam memori untuk ScriptStringExecutionParameter

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.vmware/new-azvmwarescriptstringexecutionparameterobject) untuk informasi terkini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20210601.ScriptStringExecutionParameter

## CATATAN

ALIAS

## RELATED LINKS

