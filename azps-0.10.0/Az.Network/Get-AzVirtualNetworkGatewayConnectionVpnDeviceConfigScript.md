---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/get-azvirtualnetworkgatewayconnectionvpndeviceconfigscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Get-AzVirtualNetworkGatewayConnectionVpnDeviceConfigScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Get-AzVirtualNetworkGatewayConnectionVpnDeviceConfigScript.md
ms.openlocfilehash: 3d955b2133f4a262b69de1413c5a4bf4d8e719b9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142910081"
---
# Get-AzVirtualNetworkGatewayConnectionVpnDeviceConfigScript

## SYNOPSIS
Commandlet ini mengambil sumber daya koneksi, merek perangkat VPN, model, versi firmware, dan mengembalikan skrip konfigurasi terkait yang dapat diterapkan langsung oleh pelanggan di perangkat VPN lokal mereka. Skrip akan mengikuti sintaks perangkat yang dipilih, dan mengisi parameter yang diperlukan seperti alamat IP publik gateway Azure, prefiks alamat jaringan virtual, kunci terowongan VPN yang telah dibagikan sebelumnya, dll. sehingga pelanggan cukup menyalin-tempel ke konfigurasi perangkat VPN mereka.

## SYNTAX

```
Get-AzVirtualNetworkGatewayConnectionVpnDeviceConfigScript -Name <String> -ResourceGroupName <String>
 -DeviceVendor <String> -DeviceFamily <String> -FirmwareVersion <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Commandlet ini mengambil sumber daya koneksi, merek perangkat VPN, model, versi firmware, dan mengembalikan skrip konfigurasi terkait yang dapat diterapkan langsung oleh pelanggan di perangkat VPN lokal mereka. Skrip akan mengikuti sintaks perangkat yang dipilih, dan mengisi parameter yang diperlukan seperti alamat IP publik gateway Azure, prefiks alamat jaringan virtual, kunci terowongan VPN yang telah dibagikan sebelumnya, dll. sehingga pelanggan cukup menyalin-tempel ke konfigurasi perangkat VPN mereka.

## EXAMPLES

### Contoh 1
```
PS C:\> Get-AzVirtualNetworkGatewaySupportedVpnDevice -ResourceGroupName TestRG -Name TestGateway
PS C:\> Get-AzVirtualNetworkGatewayConnectionVpnDeviceConfigScript -ResourceGroupName TestRG -Name TestConnection -DeviceVendor "Cisco-Test" -DeviceFamily "IOS-Test" -FirmwareVersion "20"
```

Contoh di atas menggunakan Get-AzVirtualNetworkGatewaySupportedVpnDevice untuk mendapatkan merek, model, dan versi firmware Perangkat VPN yang didukung.
Lalu menggunakan salah satu informasi model yang dikembalikan untuk menghasilkan skrip konfigurasi Perangkat VPN untuk VirtualNetworkGatewayConnection "TestConnection". Perangkat yang digunakan dalam contoh ini memiliki DeviceFamily "IOS-Test", DeviceVendor "Cisco-Test" dan FirmwareVersion 20.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceFamily
Nama model/keluarga perangkat VPN.

```yaml
Type: String
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
Type: String
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
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya koneksi tempat konfigurasi akan dihasilkan.

```yaml
Type: String
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
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

