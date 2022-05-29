---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/set-azexpressrouteportidentity
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzExpressRoutePortIdentity.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzExpressRoutePortIdentity.md
ms.openlocfilehash: e58bae4cbc0531f3037316a78750e28e8ed02c20
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145666462"
---
# Set-AzExpressRoutePortIdentity

## SYNOPSIS
Memperbarui identitas yang ditetapkan ke ExpressRoutePort.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/set-azexpressrouteportidentity) untuk informasi terbaru.

## SYNTAX

```
Set-AzExpressRoutePortIdentity -ExpressRoutePort <PSExpressRoutePort> -UserAssignedIdentityId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzExpressRoutePortIdentity** memperbarui objek Azure ExpressRoutePort lokal. Gunakan **Set-AzExpressRoutePort** untuk menetapkannya ke ExpressRoutePort.

## EXAMPLES

### Contoh 1
```powershell
$exrport = Get-AzExpressRoutePort -Name $portName -ResourceGroupName $rgName
$identity = New-AzUserAssignedIdentity -Name $identityName -ResourceGroupName $rgName -Location $location
$exrPortIdentity = Set-AzExpressRoutePortIdentity -UserAssignedIdentity $identity.Id -ExpressRoutePort $exrPort
$updatedExrPort = Set-AzExpressRoutePort -ExpressRoutePort $exrPort
```

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

### -ExpressRoutePort
The ExpressRoutePort

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSExpressRoutePort
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UserAssignedIdentityId
ResourceId dari identitas yang ditetapkan pengguna untuk ditetapkan ke ExpressRoutePort.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: UserAssignedIdentity

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRoutePort

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRoutePort

## NOTES

## RELATED LINKS
[Get-AzExpressRoutePortIdentity](./Get-AzExpressRoutePortIdentity.md)

[New-AzExpressRoutePortIdentity](./New-AzExpressRoutePortIdentity.md)

[Remove-AzExpressRoutePortIdentity](./Remove-AzExpressRoutePortIdentity.md)
