---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstanceEnvironmentVariableObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceEnvironmentVariableObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceEnvironmentVariableObject.md
ms.openlocfilehash: d6162600ec7aa6964858ee58114f5e4bcf616c68
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136174665"
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

### Contoh 1: Membuat variabel lingkungan dalam contoh wadah
```powershell
PS C:\> {{ Add code here }}

New-AzContainerInstanceEnvironmentVariableObject -Name "env1" -Value "value1"

Name SecureValue Value
---- ----------- -----
env1             value1
```

Perintah ini membuat variabel lingkungan dalam contoh wadah.

### Contoh 2: Membuat variabel lingkungan aman dalam contoh wadah
```powershell
PS C:\> New-AzContainerInstanceEnvironmentVariableObject -Name "env2" -SecureValue (ConvertTo-SecureString -String "******" -AsPlainText -Force)

Name SecureValue Value
---- ----------- -----
env2 ******
```

Perintah ini membuat variabel lingkungan aman dalam contoh wadah

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.EnvironmentVariable

## CATATAN

ALIAS

## RELATED LINKS

