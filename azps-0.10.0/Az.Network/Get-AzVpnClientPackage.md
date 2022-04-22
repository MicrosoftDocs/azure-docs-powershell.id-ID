---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 2B4A3E2A-1868-492F-9F77-932319D2CE6D
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/get-azvpnclientpackage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Get-AzVpnClientPackage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/Get-AzVpnClientPackage.md
ms.openlocfilehash: d08f91029940d60440d50be406dbdfe3652934a7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142973459"
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
Paket klien berisi data konfigurasi yang memungkinkan komputer klien membuat koneksi VPN ke jaringan virtual Azure; komputer klien harus memiliki paket konfigurasi yang benar yang terinstal untuk membuat koneksi VPN.
Paket konfigurasi yang berbeda tersedia berdasarkan versi Windows komputer klien (misalnya, Windows 7 atau Windows 10) dan pada arsitektur prosesor komputer klien (AMD64 atau x86).
Anda harus menentukan tipe arsitektur saat menjalankan **Get-AzVpnClientPackage**.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang paket klien VPN arsitektur prosesor
```
PS C:\>Get-AzVpnClientPackage -ProcessorArchitecture -VirtualNetworkGatewayName "ContosoVirtualNetworkGateway" -ResourceGroupName "ContosoResourceGroup" -ProcessorArchitecture "Amd64"
```

Perintah ini mendapatkan informasi tentang paket klien AMD64 VPN yang disimpan di gateway jaringan virtual bernama ContosoVirtualNetworkGateway.
Untuk mendapatkan informasi tentang paket klien x86, atur nilai parameter *ProcessorArchitecture* ke x86.

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

### -ProcessorArchitecture
Menentukan tipe arsitektur CPU tempat paket klien didesain.
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
Menentukan nama grup sumber daya tempat gateway jaringan maya ditetapkan.

Grup sumber daya mengkategorikan item untuk membantu menyederhanakan manajemen inventaris dan administrasi Umum Azure.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String
Parameter 'ResourceGroupName' menerima nilai tipe 'String' dari pipeline

### String
Parameter 'VirtualNetworkGatewayName' menerima nilai tipe 'String' dari pipeline

## OUTPUTS

###  
**Get-AzVpnClientPackage** mengembalikan instance objek System.String.

## NOTES

## RELATED LINKS

[Mengubah ukuran-AzVirtualNetworkGateway](./Resize-AzVirtualNetworkGateway.md)

[Set-AzVirtualNetworkGatewayVpnClientConfig](./Set-AzVirtualNetworkGatewayVpnClientConfig.md)


