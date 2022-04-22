---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 5765F6BD-38BC-451B-85C5-F5D1A5AF2831
online version: ''
schema: 2.0.0
ms.openlocfilehash: d1585afac1a6e95d1e2de47c84667f9f8b7ee65e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143042201"
---
# Resize-AzureVNetGateway

## SYNOPSIS
Mengubah ukuran gateway VPN.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Resize-AzureVNetGateway -VNetName <String> -GatewaySKU <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Resize-AzureVNetGateway** mengubah ukuran jaringan virtual jaringan privat virtual (VPN) gateway ke SKU yang berbeda.
SKU yang valid untuk gateway jaringan virtual adalah Default, Standard, dan HighPerformance.

## EXAMPLES

### Contoh 1: Mengubah SKU untuk gateway jaringan virtual
```
PS C:\> Resize-AzureVNetGateway -VNetName "ContosoVN07" -GatewaySKU "HighPerformance"
```

Perintah ini mengubah SKU gateway jaringan virtual untuk jaringan virtual bernama ContosoVN07 menjadi HighPerformance.

## PARAMETERS

### -GatewaysKU
Menentukan SKU tempat cmdlet ini mengubah ukuran gateway jaringan virtual.
Nilai yang valid adalah: 

- Default 
- Standar 
- HighPerformance

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VNetName
Menentukan jaringan virtual di mana cmdlet ini mengubah ukuran gateway jaringan virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVNetGateway](./Get-AzureVNetGateway.md)

[AzureVNetGateway baru](./New-AzureVNetGateway.md)

[Hapus-AzureVNetGateway](./Remove-AzureVNetGateway.md)

[Mengatur ulang AzureVNetGateway](./Reset-AzureVNetGateway.md)

[Set-AzureVNetGatewayKey](./Set-AzureVNetGatewayKey.md)


