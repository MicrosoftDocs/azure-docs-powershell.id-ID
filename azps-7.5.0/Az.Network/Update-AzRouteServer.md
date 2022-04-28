---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/update-azrouteserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzRouteServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzRouteServer.md
ms.openlocfilehash: 43eb64e0512d994dcb62db1cc5da9f751980f59c
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144210338"
---
# Update-AzRouteServer

## SYNOPSIS
Memperbarui Azure RouteServer.

## SYNTAX

### RouteServerNameParameterSet (Default)
```
Update-AzRouteServer -ResourceGroupName <String> -RouteServerName <String> [-AllowBranchToBranchTraffic]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RouteServerResourceIdParameterSet
```
Update-AzRouteServer [-AllowBranchToBranchTraffic] -ResourceId <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzRouteServer** mengalihkan lalu lintas cabang ke cabang ke Azure RouteServer.

## EXAMPLES

### Contoh 1
```powershell
Update-AzRouteServer -ResourceGroupName $rgname -RouteServerName $routeServerName -AllowBranchToBranchTraffic
```
Untuk mengaktifkan lalu lintas cabang ke cabang untuk server rute.

### Contoh 1
```powershell
Update-AzRouteServer -ResourceGroupName $rgname -RouteServerName $routeServerName
```
Untuk menonaktifkan lalu lintas cabang ke cabang untuk server rute.

## PARAMETERS

### -AllowBranchToBranchTraffic
Bendera untuk mengizinkan lalu lintas cabang ke cabang untuk server rute.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya server rute.

```yaml
Type: System.String
Parameter Sets: RouteServerNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ResourceId dari server rute.

```yaml
Type: System.String
Parameter Sets: RouteServerResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouteServerName
Nama server rute.

```yaml
Type: System.String
Parameter Sets: RouteServerNameParameterSet
Aliases: ResourceName

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSRouteServer

## NOTES

## RELATED LINKS
