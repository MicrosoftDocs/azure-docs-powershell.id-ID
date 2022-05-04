---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azvpnsitelinkconnectionikesa
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVpnSiteLinkConnectionIkeSa.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVpnSiteLinkConnectionIkeSa.md
ms.openlocfilehash: 41eb36283a4a88d74c2c8ab3f41f5b6ae3f47d33
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144729428"
---
# Get-AzVpnSiteLinkConnectionIkeSa

## SYNOPSIS
Mendapatkan Asosiasi Keamanan IKE dari Koneksi Tautan Situs VPN

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azvpnsitelinkconnectionikesa) untuk informasi terbaru.

## SYNTAX

### ByName (Default)
```
Get-AzVpnSiteLinkConnectionIkeSa -ResourceGroupName <String> -VpnGatewayName <String>
 -VpnConnectionName <String> -Name <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByInputObject
```
Get-AzVpnSiteLinkConnectionIkeSa -InputObject <PSVpnSiteLinkConnection> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResourceId
```
Get-AzVpnSiteLinkConnectionIkeSa -ResourceId <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVpnSiteLinkConnectionIkeSa** mengembalikan Asosiasi Keamanan IKE Koneksi TAUTAN VPN Anda berdasarkan Nama Koneksi VPN Site Link, Nama Koneksi VPN, Nama Koneksi VPN Gateway, dan Nama Grup Sumber Daya.
Jika cmdlet **Get-AzVpnSiteLinkConnectionIkeSa** dikeluarkan tanpa menentukan parameter yang disebutkan di atas, output tidak akan menampilkan Asosiasi Keamanan IKE.

## EXAMPLES

### Contoh 1
```powershell
Get-AzVpnSiteLinkConnectionIkeSa -ResourceGroupName test-rg -VpnGatewayName test-gateway -VpnConnectionName test-connection -ResourceName test-linkConnection
```

```output
LocalEndpoint              : 52.148.27.69
RemoteEndpoint             : 13.78.223.113
InitiatorCookie            : 10994953846917485010
ResponderCookie            : 4652217515638795111
LocalUdpEncapsulationPort  : 0
RemoteUdpEncapsulationPort : 0
Encryption                 : AES256
Integrity                  : SHA1
DhGroup                    : DHGroup2
LifeTimeSeconds            : 28800
IsSaInitiator              : True
ElapsedTimeInseconds       : 21437
Quick Mode SA              : 1 item(s)
```

Mengembalikan Asosiasi Keamanan IKE untuk Koneksi Tautan Situs VPN dengan nama "test-linkConnection" dalam grup sumber daya "test-rg"

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang.

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

### -InputObject
Objek koneksi tautan situs Vpn.

```yaml
Type: PSVpnSiteLinkConnection
Parameter Sets: ByInputObject
Aliases: VpnSiteLinkConnection

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama koneksi tautan situs Vpn.

```yaml
Type: String
Parameter Sets: ByName
Aliases: ResourceName, VpnSiteLinkConnectionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya Azure dari koneksi tautan situs Vpn tempat Asosiasi Keamanan IKE perlu diambil.

```yaml
Type: String
Parameter Sets: ByResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VpnConnectionName
Nama koneksi Vpn.

```yaml
Type: String
Parameter Sets: ByName
Aliases: ParentName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VpnGatewayName
Nama gateway Vpn.

```yaml
Type: String
Parameter Sets: ByName
Aliases: GrandParentName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnSiteLinkConnection

### System.String

## OUTPUTS

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.Network.Models.Cortex.PSVpnSiteLinkConnectionIkeSaMainModeSa, Microsoft.Azure.PowerShell.Cmdlets.Network, Version=4.5.0.0, Culture=netral, PublicKeyToken=null]]

## NOTES

## RELATED LINKS
