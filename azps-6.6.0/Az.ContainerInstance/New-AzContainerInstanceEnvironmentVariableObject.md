---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstanceEnvironmentVariableObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceEnvironmentVariableObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceEnvironmentVariableObject.md
ms.openlocfilehash: d8d5e47b79099c175e4f838691b0cc56b5b0a999
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141806468"
---
# New-AzContainerInstanceEnvironmentVariableObject

## SYNOPSIS
Membuat objek dalam memori untuk EnvironmentVariable

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/new-azcontainerinstanceenvironmentvariableobject) untuk informasi terbaru.

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
PS C:\> {{ Add code here }}

New-AzContainerInstanceEnvironmentVariableObject -Name "env1" -Value "value1"

Name SecureValue Value
---- ----------- -----
env1             value1
```

Perintah ini membuat variabel lingkungan di dalam instance kontainer.

### Contoh 2: Membuat variabel lingkungan yang aman dalam instans kontainer
```powershell
PS C:\> New-AzContainerInstanceEnvironmentVariableObject -Name "env2" -SecureValue (ConvertTo-SecureString -String "******" -AsPlainText -Force)

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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.EnvironmentVariable

## CATATAN

ALIAS

## RELATED LINKS

