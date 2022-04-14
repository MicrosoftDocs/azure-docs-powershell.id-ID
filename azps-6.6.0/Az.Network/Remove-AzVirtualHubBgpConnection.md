---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azvirtualhubbgpconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVirtualHubBgpConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVirtualHubBgpConnection.md
ms.openlocfilehash: dec07c1e48cf060969dd87e1f24f111b61835706
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141862900"
---
# Remove-AzVirtualHubBgpConnection

## SYNOPSIS
Cmdlet Remove-AzVirtualHubBgpConnection menghapus sumber daya HubBgpConnection yang mengintip Azure Virtual WAN Hub Router dengan peer berkemampuan BGP dalam jaringan virtual yang tersambung ke Hub Virtual WAN.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/remove-azvirtualhubbgpconnection) untuk informasi terbaru.

## SYNTAX

### ByVirtualHubName (Default)
```
Remove-AzVirtualHubBgpConnection -ResourceGroupName <String> -VirtualHubName <String> -Name <String> [-AsJob]
 [-Force] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVirtualHubObject
```
Remove-AzVirtualHubBgpConnection -Name <String> -VirtualHub <PSVirtualHub> [-AsJob] [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByHubBgpConnectionObject
```
Remove-AzVirtualHubBgpConnection -InputObject <PSBgpConnection> [-AsJob] [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByHubBgpConnectionResourceId
```
Remove-AzVirtualHubBgpConnection -ResourceId <String> [-AsJob] [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Remove-AzVirtualHubBgpConnection menghapus sumber daya HubBgpConnection yang rekan Azure Virtual WAN Hub Router dengan peer berkemampuan BGP di jaringan virtual yang tersambung ke Hub Virtual WAN.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Remove-AzVirtualHubBgpConnection -ResourceGroupName "testRG" -VirtualHubName "testHub" -Name "testBgpConnection"
```

Hal di atas akan menghapus Koneksi BGP Hub Virtual WAN menggunakan nama grup sumber dayanya, nama hub Virtual WAN dan nama Koneksi.

### Contoh 2
```powershell
PS C:\> Get-AzVirtualHubBgpConnection -ResourceGroupName "testRG" -VirtualHubName "testHub" -Name "testBgpConnection" | Remove-AzVirtualHubBgpConnection
```

Hal di atas akan menghapus Virtual WAN Hub BGP Connection menggunakan powershell piping pada output dari Get-AzVirtualHubBgpConnection.

### Contoh 3
```powershell
PS C:\> $bgpConnectionId = "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroup}/providers/Microsoft.Network/virtualHubs/{virtualHubName}/bgpConnections/{bgpConnectionName}"
PS C:\> Remove-AzVirtualHubBgpConnection -ResourceId $bgpConnectionId
```

Hal di atas akan menghapus Virtual WAN Hub BGP Connection menggunakan id sumber daya Koneksi BGP.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -Paksa
Jangan meminta konfirmasi jika Anda ingin menimpa sumber daya

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

### -InputObject
Sumber daya koneksi bgp hub virtual.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSBgpConnection
Parameter Sets: ByHubBgpConnectionObject
Aliases: VirtualHubBgpConnection

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubName, ByVirtualHubObject
Aliases: ResourceName, BgpConnectionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili item tempat operasi ini dijalankan.

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya.

```yaml
Type: System.String
Parameter Sets: ByHubBgpConnectionResourceId
Aliases: BgpConnectionId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHub
Sumber daya hub virtual.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualHub
Parameter Sets: ByVirtualHubObject
Aliases: ParentObject, ParentVirtualHub

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualHubName
Nama hub virtual.

```yaml
Type: System.String
Parameter Sets: ByVirtualHubName
Aliases: ParentResourceName, ParentVirtualHubName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualHub

### Microsoft.Azure.Commands.Network.Models.PSBgpConnection

### System.String

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[Get-AzVirtualHubBgpConnection](./Get-AzVirtualHubBgpConnection.md)

[New-AzVirtualHubBgpConnection](./Remove-AzVirtualHubBgpConnection.md)

[Update-AzVirtualHubBgpConnection](./Update-AzVirtualHubBgpConnection.md)
