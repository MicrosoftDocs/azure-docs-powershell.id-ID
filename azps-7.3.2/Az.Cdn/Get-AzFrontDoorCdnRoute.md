---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/get-azfrontdoorcdnroute
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzFrontDoorCdnRoute.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzFrontDoorCdnRoute.md
ms.openlocfilehash: ac5b6ff118343b09f2b22ef64031dce517528c2a
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140373662"
---
# Get-AzFrontDoorCdnRoute

## SYNOPSIS
Mendapatkan rute.

## SYNTAX

### ByFieldsParameterSet (Default)
```
Get-AzFrontDoorCdnRoute -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 [-RouteName <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByObjectParameterSet
```
Get-AzFrontDoorCdnRoute -Endpoint <PSAfdEndpoint> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Get-AzFrontDoorCdnRoute -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan rute.

## EXAMPLES

### Contoh 1
```powershell
Get-AzFrontDoorCdnRoute -EndpointName $endpointName -ProfileName $profileName -ResourceGroupName $resourceGroupName -RouteName $routeName
```

Mendapatkan rute.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Titik akhir
Objek titik akhir Azure Front Pintu.

```yaml
Type: PSAfdEndpoint
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -EndpointName
Nama titik akhir Azure Front Pintu.

```yaml
Type: String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileName
Nama profil Pintu Depan Azure.

```yaml
Type: String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya Azure.

```yaml
Type: String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya Azure.

```yaml
Type: String
Parameter Sets: ByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteName
Nama rute Pintu Depan Azure.

```yaml
Type: String
Parameter Sets: ByFieldsParameterSet
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

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdEndpoint

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdRoute

## CATATAN

## RELATED LINKS
