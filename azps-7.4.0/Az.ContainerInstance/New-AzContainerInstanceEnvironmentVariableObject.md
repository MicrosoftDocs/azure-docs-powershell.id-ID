---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstanceEnvironmentVariableObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceEnvironmentVariableObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceEnvironmentVariableObject.md
ms.openlocfilehash: fa78b0ebc9d409dc76a630b0c8f6379a05abe82d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143004617"
---
# New-AzContainerInstanceEnvironmentVariableObject

## SYNOPSIS
Membuat objek dalam memori untuk EnvironmentVariable

## SYNTAX

```
New-AzContainerInstanceEnvironmentVariableObject -Name <String> [-SecureValue <SecureString>]
 [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk EnvironmentVariable

## EXAMPLES

### Contoh 1: Membuat variabel lingkungan dalam contoh kontainer
```powershell
New-AzContainerInstanceEnvironmentVariableObject -Name "env1" -Value "value1"
```

```output
Name SecureValue Value
---- ----------- -----
env1             value1
```

Perintah ini membuat variabel lingkungan di dalam instance kontainer.

### Contoh 2: Membuat variabel lingkungan yang aman dalam instans kontainer
```powershell
New-AzContainerInstanceEnvironmentVariableObject -Name "env2" -SecureValue (ConvertTo-SecureString -String "******" -AsPlainText -Force)
```

```output
Name SecureValue Value
---- ----------- -----
env2 ******
```

Perintah ini membuat variabel lingkungan yang aman dalam contoh kontainer

## PARAMETERS

### -Nama
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
Nilai variabel lingkungan yang aman.

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

### -Value
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.EnvironmentVariable

## NOTES

ALIAS

## RELATED LINKS

