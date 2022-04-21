---
external help file: Microsoft.Azure.Commands.DeploymentManager.dll-Help.xml
Module Name: AzureRM.DeploymentManager
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.deploymentmanager/get-azurermdeploymentmanagerartifactsource
schema: 2.0.0
ms.openlocfilehash: baf5059d3a952e90422f3e16d83634291aa87614
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142736542"
---
# Get-AzureRmDeploymentManagerArtifactSource

## SYNOPSIS
Mendapatkan sumber artefak.

## SYNTAX

### Interaktif (Default)
```
Get-AzureRmDeploymentManagerArtifactSource [-ResourceGroupName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceId
```
Get-AzureRmDeploymentManagerArtifactSource [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### InputObject
```
Get-AzureRmDeploymentManagerArtifactSource [-ArtifactSource] <PSArtifactSource>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmDeploymentManagerArtifactSource** mendapatkan sumber artefak, dan mengembalikan objek yang mewakili sumber artefak tersebut.
Tentukan sumber artefak menurut nama dan nama grup sumber dayanya. Alternatifnya, Anda dapat menyediakan objek ArtifactSource atau ResourceId.

Anda dapat mengubah objek ini secara lokal, lalu menerapkan perubahan ke sumber artefak menggunakan cmdlet Set-AzureRmDeploymentManagerArtifactSource.

## EXAMPLES

### Contoh 1: Dapatkan sumber artefak
```powershell
PS C:\> Get-AzureRmDeploymentManagerArtifactSource -ResourceGroupName "ContosoResourceGroup" -Name "ContosoArtifactSource"
```

Perintah ini mendapatkan sumber artefak bernama ContosoArtifactSource di ContosoResourceGroup.

### Contoh 2: Dapatkan sumber artefak menggunakan pengidentifikasi sumber daya
```powershell
PS C:\> Get-AzureRmDeploymentManagerArtifactSource -ResourceId "/subscriptions/subscriptionId/resourcegroups/ContosoResourceGroup/providers/Microsoft.DeploymentManager/artifactSources/ContosoArtifactSource"
```

Perintah ini mendapatkan sumber artefak bernama ContosoArtifactSource di ContosoResourceGroup.

### Contoh 3: Mendapatkan sumber artefak menggunakan objek yang dikembalikan oleh New-AzureRmDeploymentManagerArtifactSource
```powershell
PS C:\> Get-AzureRmDeploymentManagerArtifactSource -ArtifactSource $artifactSourceObject
```

Perintah ini mendapatkan sumber artefak yang nama dan ResourceGroupnya masing-masing cocok dengan properti Nama dan ResourceGroupName $artifactSourceObject.

## PARAMETERS

### -ArtifactSource
Objek Sumber Artefak.

```yaml
Type: Microsoft.Azure.Commands.DeploymentManager.Models.PSArtifactSource
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber artefak.

```yaml
Type: System.String
Parameter Sets: Interactive
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Interactive
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.DeploymentManager.Models.PSArtifactSource

## NOTES

## RELATED LINKS

[New-AzureRmDeploymentManagerArtifactSource](./New-AzureRmDeploymentManagerArtifactSource.md)

[Remove-AzureRmDeploymentManagerArtifactSource](./Remove-AzureRmDeploymentManagerArtifactSource.md)

[Set-AzureRmDeploymentManagerArtifactSource](./Set-AzureRmDeploymentManagerArtifactSource.md)