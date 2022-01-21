---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistry.dll-Help.xml
Module Name: Az.ContainerRegistry
online version: https://docs.microsoft.com/powershell/module/az.containerregistry/get-azcontainerregistrytag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerRegistry/ContainerRegistry/help/Get-AzContainerRegistryTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerRegistry/ContainerRegistry/help/Get-AzContainerRegistryTag.md
ms.openlocfilehash: c90e7592539824735f44a754c4d98f5a089acdd0
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136549061"
---
# Get-AzContainerRegistryTag

## SYNOPSIS
Dapatkan atau list tag ACR. 

## SYNTAX

### ListParameterSet (Default)
```
Get-AzContainerRegistryTag -RepositoryName <String> -RegistryName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetParameterSet
```
Get-AzContainerRegistryTag -RepositoryName <String> -Name <String> -RegistryName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan atau list tag ACR.
Untuk menggunakan cmdlet ini silakan jalankan `Update-AzContainerRegistryRepository -RegistryName XXX -Repository XXX -ReadEnable $true -ListEnable $true`
pertama.

## EXAMPLES

### Contoh 1
```powershell
Get-AzContainerRegistryTag -RegistryName registry -RepositoryName alpine

Registry                    ImageName Tags
--------                    --------- ----
registry.azurecr.io alpine    {latest}
```

Daftar tag untuk repositori alpine di bawah registri.

### Contoh 2
```powershell
Get-AzContainerRegistryTag -RegistryName registry -RepositoryName alpine -name latest

Registry                    ImageName Attributes
--------                    --------- ----------
registry.azurecr.io alpine    Microsoft.Azure.Commands.ContainerRegistry.Models.PSTagAttributeBase
```

Dapatkan tag terbaru untuk repositori alpine di bawah registri.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Beri tag.

```yaml
Type: System.String
Parameter Sets: GetParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RegistryName
Nama Registri Azure Container.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RepositoryName
Nama Penyimpanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ContainerRegistry.Models.PSTagAttribute

### Microsoft.Azure.Commands.ContainerRegistry.Models.PSTagList

## CATATAN

## RELATED LINKS
