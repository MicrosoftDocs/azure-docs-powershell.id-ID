---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistry.dll-Help.xml
Module Name: Az.ContainerRegistry
online version: https://docs.microsoft.com/powershell/module/az.containerregistry/get-azcontainerregistryrepository
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerRegistry/ContainerRegistry/help/Get-AzContainerRegistryRepository.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerRegistry/ContainerRegistry/help/Get-AzContainerRegistryRepository.md
ms.openlocfilehash: 9c93a57e7b8db8db208d2acd91553eae2ad6e968
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140485167"
---
# Get-AzContainerRegistryRepository

## SYNOPSIS
Dapatkan atau daftarkan penyimpanan ACR.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.containerregistry/get-azcontainerregistryrepository) untuk informasi terkini.

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
Dapatkan atau daftarkan penyimpanan ACR.
Daftar hanya mengembalikan nama penyimpanan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzContainerRegistryRepository -RegistryName registry
alpine
test/busybox0
test/busybox1
test/busybox10
```

Membuat daftar semua penyimpanan dalam registri.

### Contoh 2
```powershell
Get-AzContainerRegistryRepository -RegistryName registry -First 3
alpine
test/busybox0
test/busybox1
```

Membuat daftar 3 penyimpanan pertama dalam registri.

### Contoh 3
```powershell
Get-AzContainerRegistryRepository -RegistryName registry -Name alpine

Registry             : registry.azurecr.io
ImageName            : alpine
CreatedTime          : 2020-10-13T05:45:25.5896115Z
LastUpdateTime       : 2021-01-04T08:31:46.2406505Z
ManifestCount        : 7
TagCount             : 1
ChangeableAttributes : Microsoft.Azure.Commands.ContainerRegistry.Models.PSChangeableAttribute
```

Dapatkan penyimpanan alpine di bawah registri.

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
Nama Penyimpanan.

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

### -First
Pertama n hasil.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.String

### Microsoft.Azure.Commands.ContainerRegistry.Models.PSRepositoryAttribute

## CATATAN

## RELATED LINKS
