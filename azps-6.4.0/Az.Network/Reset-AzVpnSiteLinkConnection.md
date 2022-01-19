---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/reset-azvpnsitelinkconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Reset-AzVpnSiteLinkConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Reset-AzVpnSiteLinkConnection.md
ms.openlocfilehash: 0982534805c664ab70a56f68f1b7754bccf032a0
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136200209"
---
# Reset-AzVpnSiteLinkConnection

## SYNOPSIS
Mereset Koneksi Link Situs VPN

## SYNTAX

### ByName
```
Reset-AzVpnSiteLinkConnection -ResourceGroupName <String> -VpnGatewayName <String> -VpnConnectionName <String>
 -Name <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByInputObject
```
Reset-AzVpnSiteLinkConnection -InputObject <PSVpnSiteLinkConnection> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResourceId
```
Reset-AzVpnSiteLinkConnection -ResourceId <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Reset-AzVpnSiteLinkConnection** mengatur ulang Koneksi Link VPN Anda berdasarkan Nama Koneksi Link Situs VPN, Nama Koneksi VPN, Nama Gateway VPN dan Nama Grup Sumber Daya.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Reset-AzVpnSiteLinkConnection -ResourceGroupName test-rg -VpnGatewayName test-gateway -VpnConnectionName test-connection -ResourceName test-linkConnection
```

Mereset Koneksi Link Situs VPN dengan nama "test-linkConnection" di dalam grup sumber daya "test-rg"

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

### -Nama
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
ID sumber daya Azure dari koneksi tautan situs VPN yang harus diatur ulang.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnSiteLinkConnection

### System.String

## OUTPUTS

## CATATAN

## RELATED LINKS