---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 2B4A3E2A-1868-492F-9F77-932319D2CE6D
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermvpnclientpackage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmVpnClientPackage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmVpnClientPackage.md
ms.openlocfilehash: fc94bb7de5663995e75f0c4f1fed05fb36b35f40
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143217683"
---
# Get-AzureRmVpnClientPackage

## SYNOPSIS
Mendapatkan informasi tentang paket klien VPN.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmVpnClientPackage -ResourceGroupName <String> -VirtualNetworkGatewayName <String>
 -ProcessorArchitecture <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmVpnClientPackage** mendapatkan informasi tentang paket klien VPN yang tersedia dari gateway jaringan virtual.
Paket klien berisi data konfigurasi yang memungkinkan komputer klien membuat koneksi VPN ke jaringan virtual Azure; komputer klien harus memiliki paket konfigurasi yang benar yang terinstal untuk membuat koneksi VPN.
Paket konfigurasi yang berbeda tersedia berdasarkan versi Windows komputer klien (misalnya, Windows 7 atau Windows 10) dan pada arsitektur prosesor komputer klien (AMD64 atau x86).
Anda harus menentukan tipe arsitektur saat menjalankan **Get-AzureRmVpnClientPackage**.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang paket klien VPN arsitektur prosesor
```
PS C:\>Get-AzureRmVpnClientPackage -ProcessorArchitecture -VirtualNetworkGatewayName "ContosoVirtualNetworkGateway" -ResourceGroupName "ContosoResourceGroup" -ProcessorArchitecture "Amd64"
```

Perintah ini mendapatkan informasi tentang paket klien AMD64 VPN yang disimpan di gateway jaringan virtual bernama ContosoVirtualNetworkGateway.
Untuk mendapatkan informasi tentang paket klien x86, atur nilai parameter *ProcessorArchitecture* ke x86.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
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
Type: System.String
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
Type: System.String
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
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Parameter: ResourceGroupName (ByValue), VirtualNetworkGatewayName (ByValue)

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Mengubah ukuran AzureRmVirtualNetworkGateway](./Resize-AzureRmVirtualNetworkGateway.md)

[Set-AzureRmVirtualNetworkGatewayVpnClientConfig](./Set-AzureRmVirtualNetworkGatewayVpnClientConfig.md)


