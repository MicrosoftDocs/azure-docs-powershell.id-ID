---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 3E6EF9B8-9709-4E59-A1E5-78CDA4EAAE1B
online version: ''
schema: 2.0.0
ms.openlocfilehash: b6b56145e5e2e92c570eda063dc072c489ccee59
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142244333"
---
# Remove-AzureVNetGateway

## SYNOPSIS
Menghapus gateway VPN.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureVNetGateway -VNetName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureVNetGateway** menghapus gateway jaringan privat virtual (VPN) yang sudah ada untuk jaringan virtual.

## EXAMPLES

### Contoh 1: Menghapus gateway jaringan virtual
```
PS C:\> Remove-AzureVNetGateway -VNetName "ContosoVN07"
```

Perintah ini menghapus gateway jaringan virtual dari jaringan virtual bernama ContosoVN07.

## PARAMETERS

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
Menentukan jaringan maya di mana cmdlet ini menghapus gateway VPN.

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

## CATATAN

## RELATED LINKS

[Get-AzureVNetGateway](./Get-AzureVNetGateway.md)

[AzureVNetGateway baru](./New-AzureVNetGateway.md)

[Mengatur ulang AzureVNetGateway](./Reset-AzureVNetGateway.md)

[Mengubah ukuran AzureVNetGateway](./Resize-AzureVNetGateway.md)

[Set-AzureVNetGatewayKey](./Set-AzureVNetGatewayKey.md)


