---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 5765F6BD-38BC-451B-85C5-F5D1A5AF2831
online version: ''
schema: 2.0.0
ms.openlocfilehash: d1585afac1a6e95d1e2de47c84667f9f8b7ee65e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428044"
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
Cmdlet **Resize-AzureVNetGateway** mengubah ukuran gateway jaringan virtual privat virtual (VPN) menjadi SKU berbeda.
SKU yang valid untuk gateway jaringan virtual adalah Default, Standard, dan HighPerformance.

## EXAMPLES

### Contoh 1: Mengubah SKU untuk gateway jaringan virtual
```
PS C:\> Resize-AzureVNetGateway -VNetName "ContosoVN07" -GatewaySKU "HighPerformance"
```

Perintah ini mengubah SKU gateway jaringan virtual untuk jaringan virtual yang bernama ContosoVN07 menjadi HighPerformance.

## PARAMETERS

### -GatewaySKU
Menentukan SKU di mana cmdlet ini mengubah ukuran gateway jaringan virtual.
Nilai valid adalah: 

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
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureVNetGateway](./Get-AzureVNetGateway.md)

[New-AzureVNetGateway](./New-AzureVNetGateway.md)

[Remove-AzureVNetGateway](./Remove-AzureVNetGateway.md)

[Reset-AzureVNetGateway](./Reset-AzureVNetGateway.md)

[Set-AzureVNetGatewayKey](./Set-AzureVNetGatewayKey.md)


