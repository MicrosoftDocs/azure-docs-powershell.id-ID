---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationScopeObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationScopeObject.md
ms.openlocfilehash: 38d83d1dd13fb13c931968679b1fbec6c58c599b
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144222926"
---
# New-AzSecurityAutomationScopeObject

## SYNOPSIS
Membuat objek cakupan otomatisasi keamanan

## SYNTAX

```
New-AzSecurityAutomationScopeObject -Description <String> -ScopePath <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek cakupan otomatisasi keamanan

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzSecurityAutomationScopeObject -Description 'Security assessments that relate to the resource group myResourceGroup within the subscription a5caac9c-5c04-49af-b3d0-e204f40345d5'  -ScopePath '/subscriptions/a5caac9c-5c04-49af-b3d0-e204f40345d5/resourceGroups/myResourceGroup'
```

Membuat objek cakupan otomatisasi keamanan

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deskripsi
Deskripsi cakupan sumber daya

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScopePath
Jalur cakupan sumber daya.
Dapat menjadi langganan tempat otomatisasi ditentukan pada atau grup sumber daya di bawah langganan tersebut (ID sumber daya Azure yang sepenuhnya memenuhi syarat)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomationScope

## NOTES

## RELATED LINKS
