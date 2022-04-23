---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 0AED21E8-A638-4019-9B23-447472E56C7A
online version: ''
schema: 2.0.0
ms.openlocfilehash: c70ae603998b9fef98845d09b92d2d3d2c451936
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143158832"
---
# Get-AzureApplicationGateway

## SYNOPSIS
Mendapatkan Application Gateway.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureApplicationGateway [-Name <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureApplicationGateway** mendapatkan Azure Application Gateway yang sudah ada.

## EXAMPLES

### Contoh 1: Dapatkan Application Gateway
```
PS C:\> Get-AzureApplicationGateway -Name "ApplicationGateway06"
```

Perintah ini mendapatkan Application Gateway bernama ApplicationGateway06.

### Contoh 2: Dapatkan semua Gateway Aplikasi
```
PS C:\> Get-AzureApplicationGateway
```

Perintah ini mendapatkan semua Gateway Aplikasi di bawah langganan Anda.

## PARAMETERS

### -Nama
Menentukan nama Application Gateway yang didapat cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGateway, IEnumerable<Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGateway>

## NOTES

## RELATED LINKS

[AzureApplicationGateway baru](./New-AzureApplicationGateway.md)

[Hapus-AzureApplicationGateway](./Remove-AzureApplicationGateway.md)

[Start-AzureApplicationGateway](./Start-AzureApplicationGateway.md)

[Stop-AzureApplicationGateway](./Stop-AzureApplicationGateway.md)

[Update-AzureApplicationGateway](./Update-AzureApplicationGateway.md)


