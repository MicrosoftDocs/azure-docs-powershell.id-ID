---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistry.dll-Help.xml
Module Name: Az.ContainerRegistry
online version: https://docs.microsoft.com/powershell/module/az.containerregistry/get-azcontainerregistryrepository
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerRegistry/ContainerRegistry/help/Get-AzContainerRegistryRepository.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerRegistry/ContainerRegistry/help/Get-AzContainerRegistryRepository.md
ms.openlocfilehash: 77bb2d119a53892b71194245300d3a10722e63de
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145801322"
---
# Get-AzContainerRegistryRepository

## SYNOPSIS
Mendapatkan atau mencantumkan repositori ACR.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.containerregistry/get-azcontainerregistryrepository) untuk informasi terbaru.

## SYNTAX

### ListParameterSet (Default)
```
Get-AzContainerRegistryRepository [-First <Int32>] -RegistryName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetParameterSet
```
Get-AzContainerRegistryRepository -Name <String> -RegistryName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan atau mencantumkan repositori ACR.
Daftar hanya mengembalikan nama repositori.

## EXAMPLES

### Contoh 1
```powershell
Get-AzContainerRegistryRepository -RegistryName registry
```

```output
alpine
test/busybox0
test/busybox1
test/busybox10
```

Mencantumkan semua repositori dalam registri.

### Contoh 2
```powershell
Get-AzContainerRegistryRepository -RegistryName registry -First 3
```

```output
alpine
test/busybox0
test/busybox1
```

Mencantumkan 3 repositori pertama dalam registri.

### Contoh: 3
```powershell
Get-AzContainerRegistryRepository -RegistryName registry -Name alpine
```

```output
Registry             : registry.azurecr.io
ImageName            : alpine
CreatedTime          : 2020-10-13T05:45:25.5896115Z
LastUpdateTime       : 2021-01-04T08:31:46.2406505Z
ManifestCount        : 7
TagCount             : 1
ChangeableAttributes : Microsoft.Azure.Commands.ContainerRegistry.Models.PSChangeableAttribute
```

Dapatkan repositori alpine di bawah registri.

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
Nama Repositori.

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
nama Azure Container Registry.

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

### -First
Hasil n pertama.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: ListParameterSet
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

### System.String

## OUTPUTS

### System.String

### Microsoft.Azure.Commands.ContainerRegistry.Models.PSRepositoryAttribute

## NOTES

## RELATED LINKS
