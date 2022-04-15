---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/update-azvirtualrouter
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVirtualRouter.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVirtualRouter.md
ms.openlocfilehash: 461f5c7f2e6f057e8ff0be073519ed69b40b0331
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142430957"
---
# Update-AzVirtualRouter

## SYNOPSIS
Memperbarui Router Virtual. 

## SYNTAX

### VirtualRouterNameParameterSet (Default)
```
Update-AzVirtualRouter -ResourceGroupName <String> -RouterName <String> [-AllowBranchToBranchTraffic]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### VirtualRouterResourceIdParameterSet
```
Update-AzVirtualRouter [-AllowBranchToBranchTraffic] -ResourceId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Update Virtual Router untuk mengaktifkan atau menonaktifkan cabang ke lalu lintas cabang.

## EXAMPLES

### Contoh 1
```powershell
Update-AzVirtualRouter -ResourceGroupName $rgname -RouterName $virtualRouterName -AllowBranchToBranchTraffic
```

Memperbarui Virtual Router untuk memungkinkan cabang untuk cabang lalu lintas cabang

### Contoh 2
```powershell
Update-AzVirtualRouter -ResourceGroupName $rgname -RouterName $virtualRouterName
```

Memperbarui Virtual Router untuk memblokir cabang ke lalu lintas cabang

## PARAMETERS

### -AllowBranchToBranchTraffic
Tandai untuk mengizinkan cabang untuk cabang lalu lintas untuk router virtual.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -ResourceGroupName
Nama grup sumber daya perute virtual.

```yaml
Type: String
Parameter Sets: VirtualRouterNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ResourceId router virtual.

```yaml
Type: String
Parameter Sets: VirtualRouterResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouterName
Nama perute virtual.

```yaml
Type: String
Parameter Sets: VirtualRouterNameParameterSet
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualRouter

## CATATAN

## RELATED LINKS
