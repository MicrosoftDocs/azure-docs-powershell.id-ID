---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstanceEnvironmentVariableObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceEnvironmentVariableObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceEnvironmentVariableObject.md
ms.openlocfilehash: 89531c79c8547f8061f82b90449b8ad3f1d65eb2
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144669958"
---
# New-AzContainerInstanceEnvironmentVariableObject

## SYNOPSIS
Membuat objek dalam memori untuk EnvironmentVariable

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/new-azcontainerinstanceenvironmentvariableobject) untuk informasi terbaru.

## SYNTAX

```
New-AzContainerInstanceEnvironmentVariableObject -Name <String> [-SecureValue <SecureString>]
 [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk EnvironmentVariable

## EXAMPLES

### Contoh 1: Membuat variabel lingkungan dalam instans kontainer
```powershell
New-AzContainerInstanceEnvironmentVariableObject -Name "env1" -Value "value1"
```

```output
Name SecureValue Value
---- ----------- -----
env1             value1
```

Perintah ini membuat variabel lingkungan dalam instans kontainer.

### Contoh 2: Membuat variabel lingkungan yang aman dalam instans kontainer
```powershell
New-AzContainerInstanceEnvironmentVariableObject -Name "env2" -SecureValue (ConvertTo-SecureString -String "******" -AsPlainText -Force)
```

```output
Name SecureValue Value
---- ----------- -----
env2 ******
```

Perintah ini membuat variabel lingkungan yang aman dalam instans kontainer

## PARAMETERS

### -Name
Nama variabel lingkungan.

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
Nilai variabel lingkungan aman.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nilai
Nilai variabel lingkungan.

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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.EnvironmentVariable

## NOTES

ALIAS

## RELATED LINKS

