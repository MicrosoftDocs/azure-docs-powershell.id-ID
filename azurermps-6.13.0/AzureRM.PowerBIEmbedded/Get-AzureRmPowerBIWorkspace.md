---
external help file: Microsoft.Azure.Commands.Management.PowerBIEmbedded.dll-Help.xml
Module Name: AzureRM.PowerBIEmbedded
ms.assetid: 5321FC62-3585-4493-A3D2-22CD82503CA7
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.powerbiembedded/get-azurermpowerbiworkspace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/PowerBIEmbedded/Commands.Management.PowerBIEmbedded/help/Get-AzureRmPowerBIWorkspace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/PowerBIEmbedded/Commands.Management.PowerBIEmbedded/help/Get-AzureRmPowerBIWorkspace.md
ms.openlocfilehash: 86d4b25845ea82b55afdd715385f516096bb20c6832ccad50940a2c4e88678b0
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132416121"
---
# Get-AzureRmPowerBIWorkspace

## SYNOPSIS
Dapatkan ruang kerja dalam kumpulan Power BI kerja Anda.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmPowerBIWorkspace [-ResourceGroupName] <String> [-WorkspaceCollectionName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmPowerBIWorkspace** dapat memperoleh ruang kerja dalam Power BI ruang kerja Anda.

## EXAMPLES

### Contoh 1: Dapatkan ruang kerja koleksi ruang kerja
```
PS C:\>Get-AzureRmPowerBIWorkspace -ResourceGroupName "ResourceGroup17" -WorkspaceCollectionName "WCN11"
```

Perintah ini mendapatkan ruang kerja yang termasuk dalam kumpulan ruang kerja bernama WCN11 dalam grup sumber daya yang ditentukan.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -ResourceGroupName
Menentukan nama grup sumber daya tempat kumpulan ruang kerja tersebut berada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkspaceCollectionName
Menentukan nama kumpulan ruang kerja di mana cmdlet ini mendapatkan ruang kerja.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name, ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Management.PowerBIEmbedded.Models.PSWorkspace

## CATATAN

## RELATED LINKS

[Get-AzureRmPowerBIWorkspaceCollection](./Get-AzureRmPowerBIWorkspaceCollection.md)


