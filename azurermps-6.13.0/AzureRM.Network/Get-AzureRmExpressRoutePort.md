---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermexpressrouteport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmExpressRoutePort.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmExpressRoutePort.md
ms.openlocfilehash: f4a949fe4599e4ea4b0f4cc870ed48c3f474c8eb3454394ca660db34fb7d078d
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140855972"
---
# Get-AzureRmExpressRoutePort

## SYNOPSIS
Mendapatkan sumber daya Azure ExpressRoutePort.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ResourceNameParameterSet (Default)
```
Get-AzureRmExpressRoutePort [-ResourceGroupName <String>] [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Get-AzureRmExpressRoutePort -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmExpressRoutePort** digunakan untuk mengambil objek ExpressRoutePort dari langganan Anda. Objek expressrouteport yang dikembalikan dapat digunakan sebagai input ke cmdlet lain yang beroperasi di ExpressRoutePort.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzureRmExpressRoutePort -Name $PortName -ResourceGroupName $rg
```

Dapatkan objek ExpressRoutePort dengan nama yang $PortName grup sumber daya $rg dalam langganan Anda.

### Contoh 2
```powershell
PS C:\> Get-AzureRmExpressRoutePort -ResourceId $id
```

Dapatkan objek ExpressRoutePort dengan ResourceId $id. 

## PARAMETERS

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
Nama ExpressRoutePort.

```yaml
Type: System.String
Parameter Sets: ResourceNameParameterSet
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya ExpressRoutePort.

```yaml
Type: System.String
Parameter Sets: ResourceNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ResourceId dari port rute ekspres.

```yaml
Type: System.String
Parameter Sets: ResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRoutePort

## CATATAN

## RELATED LINKS
