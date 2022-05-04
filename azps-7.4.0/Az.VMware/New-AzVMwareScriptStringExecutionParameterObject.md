---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareScriptStringExecutionParameterObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptStringExecutionParameterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareScriptStringExecutionParameterObject.md
ms.openlocfilehash: 1b7af3576b9f7ee940399c36452e43ea73de1def
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144665296"
---
# New-AzVMwareScriptStringExecutionParameterObject

## SYNOPSIS
Membuat objek dalam memori untuk ScriptStringExecutionParameter

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.vmware/new-azvmwarescriptstringexecutionparameterobject) untuk informasi terbaru.

## SYNTAX

```
New-AzVMwareScriptStringExecutionParameterObject -Name <String> [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ScriptStringExecutionParameter

## EXAMPLES

### Contoh 1: Membuat objek Eksekusi String Skrip lokal
```powershell
New-AzVMwareScriptStringExecutionParameterObject -Name azps_test_stringvalue -Value "stringValue"
```
```output
Name                  Type   Value
----                  ----   -----
azps_test_stringvalue Value  stringValue
```

Membuat objek Eksekusi String Skrip lokal

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

### -Nilai
Nilai untuk parameter yang diteruskan.

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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.ScriptStringExecutionParameter

## NOTES

ALIAS

## RELATED LINKS

