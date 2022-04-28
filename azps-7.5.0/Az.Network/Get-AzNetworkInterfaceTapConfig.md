---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-aznetworkinterfacetapconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzNetworkInterfaceTapConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzNetworkInterfaceTapConfig.md
ms.openlocfilehash: 624e218a888afab9aa866693c0c043045b8af6f6
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144222170"
---
# Get-AzNetworkInterfaceTapConfig

## SYNOPSIS
Mendapatkan sumber daya konfigurasi Tap.

## SYNTAX

### GetByNameParameterSet (Default)
```
Get-AzNetworkInterfaceTapConfig -ResourceGroupName <String> -NetworkInterfaceName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GetByResourceIdParameterSet
```
Get-AzNetworkInterfaceTapConfig -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzNetworkInterfaceTapConfig** mendapatkan Azure Tap Configuration untuk grup sumber daya tertentu, antarmuka jaringan, dan mengetuk nama konfigurasi atau daftar konfigurasi ketuk dalam grup sumber daya dan antarmuka jaringan.

## EXAMPLES

### Contoh 1: Mendapatkan semua konfigurasi ketukan untuk antarmuka jaringan tertentu
```powershell
Get-AzNetworkInterfaceTapConfig -ResourceGroupName "ResourceGroup1" -NetworkInterface "sourceNicName"
```

Perintah ini akan menambahkan konfigurasi ketukan untuk antarmuka jaringan yang diberikan.

### Contoh 2: Mendapatkan konfigurasi ketukan yang diberikan
```powershell
Get-AzNetworkInterface -ResourceGroupName "ResourceGroup1" -NetworkInterface "sourceNicName" -Name "tapconfigName"
```

Perintah ini mendapatkan konfigurasi ketukan tertentu yang ditambahkan untuk antarmuka jaringan yang diberikan.

### Contoh 3: Mendapatkan konfigurasi ketukan yang diberikan
```powershell
Get-AzNetworkInterface -ResourceGroupName "ResourceGroup1" -NetworkInterface "sourceNicName" -Name "tapconfig*"
```

Perintah ini akan menambahkan konfigurasi ketukan untuk antarmuka jaringan tertentu dengan nama yang dimulai dengan "tapconfig".

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

### -Name
Nama konfigurasi ketukan tertentu.

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -NetworkInterfaceName
Nama Antarmuka Jaringan.

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ResourceId dari sumber daya TapConfiguration

```yaml
Type: System.String
Parameter Sets: GetByResourceIdParameterSet
Aliases:

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.Network.Models.PSNetworkInterfaceTapConfiguration

## NOTES

## RELATED LINKS

[Add-AzNetworkInterfaceTapConfig](./Add-AzNetworkInterfaceTapConfig.md)

[Remove-AzNetworkInterfaceTapConfig](./Remove-AzNetworkInterfaceTapConfig.md)

[Set-AzNetworkInterfaceTapConfig](./Set-AzNetworkInterfaceTapConfig.md)
