---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azexpressrouteport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRoutePort.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRoutePort.md
ms.openlocfilehash: 0e10e267fa37c706ba43d7d4232680756aedeecd
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136213439"
---
# Get-AzExpressRoutePort

## SYNOPSIS
Mendapatkan sumber daya Azure ExpressRoutePort.

## SYNTAX

### ResourceNameParameterSet (Default)
```
Get-AzExpressRoutePort [-ResourceGroupName <String>] [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Get-AzExpressRoutePort -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzExpressRoutePort** digunakan untuk mengambil objek ExpressRoutePort dari langganan Anda. Objek expressrouteport yang dikembalikan dapat digunakan sebagai input ke cmdlet lain yang beroperasi di ExpressRoutePort.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzExpressRoutePort -Name $PortName -ResourceGroupName $rg
```

Dapatkan objek ExpressRoutePort dengan nama yang $PortName grup sumber daya $rg dalam langganan Anda.

### Contoh 2
```powershell
PS C:\> Get-AzExpressRoutePort -Name test*
```

Dapatkan semua objek ExpressRoutePort yang namanya dimulai dengan "test".

### Contoh 3
```powershell
PS C:\> Get-AzExpressRoutePort -ResourceId $id
```

Dapatkan objek ExpressRoutePort dengan ResourceId $id. 

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
Nama ExpressRoutePort.

```yaml
Type: System.String
Parameter Sets: ResourceNameParameterSet
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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
Accept wildcard characters: True
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRoutePort

## CATATAN

## RELATED LINKS

[New-AzExpressRoutePort](./New-AzExpressRoutePort.md)

[Remove-AzExpressRoutePort](./Remove-AzExpressRoutePort.md)

[Set-AzExpressRoutePort](./Set-AzExpressRoutePort.md)
