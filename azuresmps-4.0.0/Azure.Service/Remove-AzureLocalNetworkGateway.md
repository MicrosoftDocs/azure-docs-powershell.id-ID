---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: F380D98B-98EA-4013-8744-549A6F18C9B6
online version: ''
schema: 2.0.0
ms.openlocfilehash: 4fce126aced2f198326bd04b46af171107c0dc38
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142312433"
---
# Remove-AzureLocalNetworkGateway

## SYNOPSIS
Menghapus gateway jaringan lokal Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureLocalNetworkGateway -GatewayId <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureLocalNetworkGateway** menghapus gateway jaringan lokal Azure.

## EXAMPLES

## PARAMETERS

### -GatewayId
Menentukan ID gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureLocalNetworkGateway](./Get-AzureLocalNetworkGateway.md)

[AzureLocalNetworkGateway baru](./New-AzureLocalNetworkGateway.md)

[Mengatur ulang AzureLocalNetworkGateway](./Reset-AzureLocalNetworkGateway.md)


