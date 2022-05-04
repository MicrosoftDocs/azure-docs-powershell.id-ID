---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azvirtualnetworkgatewayconnectionvpndeviceconfigscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVirtualNetworkGatewayConnectionVpnDeviceConfigScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVirtualNetworkGatewayConnectionVpnDeviceConfigScript.md
ms.openlocfilehash: 13b9fd038755a8f7fc9db0049a5b456ac366a8f3
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144599414"
---
# Dapatkan-AzVirtualNetworkGatewayConnectionVpnDeviceConfigScript

## SYNOPSIS
Commandlet ini mengambil sumber daya koneksi, merek perangkat VPN, model, versi firmware, dan mengembalikan skrip konfigurasi yang sesuai yang dapat diterapkan pelanggan langsung di perangkat VPN lokal mereka. Skrip akan mengikuti sintaks perangkat yang dipilih, dan mengisi parameter yang diperlukan seperti alamat IP publik gateway Azure, prefiks alamat jaringan virtual, kunci pra-berbagi terowongan VPN, dll. sehingga pelanggan cukup menyalin-tempel ke konfigurasi perangkat VPN mereka.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azvirtualnetworkgatewayconnectionvpndeviceconfigscript) untuk informasi terbaru.

## SYNTAX

```
Get-AzVirtualNetworkGatewayConnectionVpnDeviceConfigScript -Name <String> -ResourceGroupName <String>
 -DeviceVendor <String> -DeviceFamily <String> -FirmwareVersion <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Commandlet ini mengambil sumber daya koneksi, merek perangkat VPN, model, versi firmware, dan mengembalikan skrip konfigurasi yang sesuai yang dapat diterapkan pelanggan langsung di perangkat VPN lokal mereka. Skrip akan mengikuti sintaks perangkat yang dipilih, dan mengisi parameter yang diperlukan seperti alamat IP publik gateway Azure, prefiks alamat jaringan virtual, kunci pra-berbagi terowongan VPN, dll. sehingga pelanggan cukup menyalin-tempel ke konfigurasi perangkat VPN mereka.

## EXAMPLES

### Contoh 1
```powershell
Get-AzVirtualNetworkGatewaySupportedVpnDevice -ResourceGroupName TestRG -Name TestGateway
Get-AzVirtualNetworkGatewayConnectionVpnDeviceConfigScript -ResourceGroupName TestRG -Name TestConnection -DeviceVendor "Cisco-Test" -DeviceFamily "IOS-Test" -FirmwareVersion "20"
```

Contoh di atas menggunakan Get-AzVirtualNetworkGatewaySupportedVpnDevice untuk mendapatkan merek, model, dan versi firmware Perangkat VPN yang didukung.
Kemudian menggunakan salah satu informasi model yang dikembalikan untuk menghasilkan skrip konfigurasi Perangkat VPN untuk VirtualNetworkGatewayConnection "TestConnection". Perangkat yang digunakan dalam contoh ini memiliki DeviceFamily "IOS-Test", DeviceVendor "Cisco-Test" dan FirmwareVersion 20.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -DeviceFamily
Nama model/keluarga perangkat VPN.

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

### -DeviceVendor
Nama vendor perangkat VPN.

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

### -FirmwareVersion
Versi firmware perangkat VPN.

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
Nama sumber daya koneksi yang konfigurasinya akan dihasilkan.

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

### -ResourceGroupName
Nama grup sumber daya.

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

### System.String

## NOTES

## RELATED LINKS
