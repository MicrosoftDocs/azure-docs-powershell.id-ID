---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/get-azfrontdoorcdnsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzFrontDoorCdnSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzFrontDoorCdnSecret.md
ms.openlocfilehash: 2d994085bb97198a29371528b756f1350fe8f78f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143370557"
---
# Get-AzFrontDoorCdnSecret

## SYNOPSIS
Dapatkan rahasianya.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cdn/get-azfrontdoorcdnsecret) untuk informasi terbaru.

## SYNTAX

### ByFieldsParameterSet (Default)
```
Get-AzFrontDoorCdnSecret -ProfileName <String> -ResourceGroupName <String> [-SecretName <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByObjectParameterSet
```
Get-AzFrontDoorCdnSecret -Profile <PSAfdProfile> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Get-AzFrontDoorCdnSecret -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan rahasianya.

## EXAMPLES

### Contoh 1
```powershell
Get-AzFrontDoorCdnSecret -ProfileName $profileName -ResourceGroupName $resourceGroupName -SecretName $secretName
```

Dapatkan rahasianya.

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

### -Profil
Objek profil Pintu Depan Azure.

```yaml
Type: PSAfdProfile
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProfileName
Nama profil Azure Front Door.

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

### -SecretName
Nama rahasia Azure Front Door.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdProfile

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdSecret

## NOTES

## RELATED LINKS
