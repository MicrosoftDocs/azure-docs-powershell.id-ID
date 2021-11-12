---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 2B4A3E2A-1868-492F-9F77-932319D2CE6D
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/get-azvpnclientpackage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Get-AzVpnClientPackage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Get-AzVpnClientPackage.md
ms.openlocfilehash: d08f91029940d60440d50be406dbdfe3652934a7
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132419857"
---
# Get-AzVpnClientPackage

## SYNOPSIS
Mendapatkan informasi tentang paket klien VPN.

## SYNTAX

```
Get-AzVpnClientPackage -ResourceGroupName <String> -VirtualNetworkGatewayName <String>
 -ProcessorArchitecture <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVpnClientPackage** mendapatkan informasi tentang paket klien VPN yang tersedia dari gateway jaringan virtual.
Paket klien berisi data konfigurasi yang memungkinkan komputer klien membuat koneksi VPN ke jaringan virtual Azure; komputer klien harus memiliki instalan paket konfigurasi yang benar agar dapat membuat koneksi VPN.
Paket konfigurasi berbeda tersedia berdasarkan versi Windows komputer klien (misalnya, Windows 7 atau Windows 10) dan pada arsitektur prosesor komputer klien (AMD64 atau x86).
Anda harus menentukan tipe arsitektur ketika menjalankan **Get-AzVpnClientPackage**.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang arsitektur prosesor paket klien VPN
```
PS C:\>Get-AzVpnClientPackage -ProcessorArchitecture -VirtualNetworkGatewayName "ContosoVirtualNetworkGateway" -ResourceGroupName "ContosoResourceGroup" -ProcessorArchitecture "Amd64"
```

Perintah ini mendapatkan informasi tentang paket klien VPN AMD64 yang disimpan di gateway jaringan virtual bernama ContosoVirtualNetworkGateway.
Untuk mendapatkan informasi tentang paket klien x86, atur nilai parameter *ProcessorArchitecture* ke x86.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -ProcessorArchitecture
Menentukan tipe arsitektur CPU yang didesain untuk paket klien.
Nilai yang valid adalah Amd64 dan X86.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Amd64, X86

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang ditetapkan untuk gateway jaringan virtual.

Grup sumber daya mengkategorikan item untuk membantu menyederhanakan manajemen inventaris dan administrasi umum Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualNetworkGatewayName
Menentukan nama gateway jaringan virtual tempat informasi paket klien disimpan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### String
Parameter 'ResourceGroupName' menerima nilai tipe 'String' dari saluran

### String
Parameter 'VirtualNetworkGatewayName' menerima nilai tipe 'String' dari saluran

## OUTPUTS

###  
**Get-AzVpnClientPackage** mengembalikan instans objek System.String.

## CATATAN

## RELATED LINKS

[Resize-AzVirtualNetworkGateway](./Resize-AzVirtualNetworkGateway.md)

[Set-AzVirtualNetworkGatewayVpnClientConfig](./Set-AzVirtualNetworkGatewayVpnClientConfig.md)


