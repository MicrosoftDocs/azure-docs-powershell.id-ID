---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azprivateendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPrivateEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPrivateEndpoint.md
ms.openlocfilehash: 19518847e51213c1b25aec3bdb63cfda97885c09
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144709048"
---
# New-AzPrivateEndpoint

## SYNOPSIS
Membuat titik akhir privat.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azprivateendpoint) untuk informasi terbaru.

## SYNTAX

```
New-AzPrivateEndpoint -Name <String> -ResourceGroupName <String> -Location <String> -Subnet <PSSubnet>
 -PrivateLinkServiceConnection <PSPrivateLinkServiceConnection[]> [-ByManualRequest] [-EdgeZone <String>]
 [-Tag <Hashtable>] [-Force] [-AsJob] [-ApplicationSecurityGroup <PSApplicationSecurityGroup[]>]
 [-IpConfiguration <PSPrivateEndpointIPConfiguration[]>] [-CustomNetworkInterfaceName <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **New-AzPrivateEndpoint** membuat titik akhir privat.

## EXAMPLES

### Contoh 1: Membuat titik akhir privat

Contoh berikut membuat titik akhir privat dengan ID layanan tautan privat tertentu di subnet yang ditentukan dalam jaringan virtual.

```powershell
$virtualNetwork = Get-AzVirtualNetwork -ResourceName 'myVirtualNetwork' -ResourceGroupName 'myResourceGroup'
$subnet = $virtualNetwork | Select-Object -ExpandProperty subnets | Where-Object Name -eq 'mySubnet'
$plsConnection= New-AzPrivateLinkServiceConnection -Name 'MyPLSConnections' -PrivateLinkServiceId '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myResourceGroup/providers/Microsoft.Network/privateLinkServices/privateLinkService' -RequestMessage 'Please Approve my request'
New-AzPrivateEndpoint -Name 'MyPrivateEndpoint' -ResourceGroup 'myResourceGroup' -Location 'centralus' -PrivateLinkServiceConnection $plsConnection -Subnet $subnet
```

## PARAMETERS

### -ApplicationSecurityGroup
Kelompok keamanan aplikasi

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationSecurityGroup[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

Jalankan cmdlet sebagai pekerjaan di latar belakang.

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

### -ByManualRequest

Gunakan permintaan manual untuk membuat koneksi.

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

### -CustomNetworkInterfaceName
Nama antarmuka jaringan kustom

```yaml
Type: System.String
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

### -EdgeZone
Zona tepi titik akhir privat

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Jangan meminta konfirmasi untuk menimpa sumber daya.

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

### -IpConfiguration
Konfigurasi IP titik akhir privat

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSPrivateEndpointIPConfiguration[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi

Menentukan lokasi untuk titik akhir privat. Gunakan [Get-AzLocation](/powershell/module/az.resources/get-azlocation) untuk menentukan nilai yang valid untuk parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Nama titik akhir privat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivateLinkServiceConnection

ID sumber daya untuk menyambungkan titik akhir privat.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSPrivateLinkServiceConnection[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName

Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subnet

Subnet titik akhir privat.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSSubnet
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag

Pasangan kunci-nilai dalam bentuk tabel hash. Misalnya: @{key0='value0';key1=$null;key2='value2'}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
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

### Microsoft.Azure.Commands.Network.Models.PSSubnet

### Microsoft.Azure.Commands.Network.Models.PSPrivateLinkServiceConnection[]

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSPrivateEndpoint

## NOTES

## RELATED LINKS

[Get-AzPrivateEndpoint](./Get-AzPrivateEndpoint.md)

[Remove-AzPrivateEndpoint](./Remove-AzPrivateEndpoint.md)

[New-AzPrivateLinkServiceConnection](./New-AzPrivateLinkServiceConnection.md)
