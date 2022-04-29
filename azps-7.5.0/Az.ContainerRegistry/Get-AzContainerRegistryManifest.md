---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistry.dll-Help.xml
Module Name: Az.ContainerRegistry
online version: https://docs.microsoft.com/powershell/module/az.containerregistry/get-azcontainerregistrymanifest
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerRegistry/ContainerRegistry/help/Get-AzContainerRegistryManifest.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerRegistry/ContainerRegistry/help/Get-AzContainerRegistryManifest.md
ms.openlocfilehash: 723d158c6f5b5fb1be01d5b584f1611e9c57d8b1
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144227706"
---
# Get-AzContainerRegistryManifest

## SYNOPSIS
Mendapatkan atau mencantumkan manifes ACR. 

## SYNTAX

### ListParameterSet (Default)
```
Get-AzContainerRegistryManifest -RepositoryName <String> -RegistryName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetParameterSet
```
Get-AzContainerRegistryManifest -RepositoryName <String> -Name <String> -RegistryName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan atau mencantumkan manifes ACR.
Untuk menggunakan cmdlet ini, silakan jalankan `Update-AzContainerRegistryRepository -RegistryName XXX -Repository XXX -ReadEnable $true -ListEnable $true`
Pertama.

## EXAMPLES

### Contoh 1
```powershell
Get-AzContainerRegistryManifest -RegistryName registry -RepositoryName alpine
```

```output
Registry                    ImageName                   ManifestsAttributes
--------                    ---------                   -------------------
registry.azurecr.io         alpine         {Microsoft.Azure.Commands.ContainerRegistry.Models.PSManifestAttributeBase, Microsoft.Azure.Comm…}
```

Mencantumkan manifes untuk repositori alpine di bawah registri.

### Contoh 2
```powershell
Get-AzContainerRegistryManifest -RegistryName registry -RepositoryName alpine -Name sha256:a5426f084c755f4d6c1d1562a2d456aa574a24a61706f6806415627360c06ac0
```

```output
Registry                    ImageName Attributes
--------                    --------- ----------
registry.azurecr.io         alpine    Microsoft.Azure.Commands.ContainerRegistry.Models.PSManifestAttributeBase
```

Dapatkan manifes sha256:a5426f084c755f4d6c1d1562a2d456aa574a24a61706f6806415627360c06ac0 untuk repositori alpine di bawah registri.

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

### -Name
Referensi manifes.

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
Nama Azure Container Registry.

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
Nama Repositori.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ContainerRegistry.Models.PSManifestAttribute

### Microsoft.Azure.Commands.ContainerRegistry.Models.PSAcrManifest

## NOTES

## RELATED LINKS
