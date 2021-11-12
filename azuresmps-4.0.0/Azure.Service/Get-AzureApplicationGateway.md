---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 0AED21E8-A638-4019-9B23-447472E56C7A
online version: ''
schema: 2.0.0
ms.openlocfilehash: c70ae603998b9fef98845d09b92d2d3d2c451936
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424146"
---
# Get-AzureApplicationGateway

## SYNOPSIS
Mendapatkan Gateway Aplikasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureApplicationGateway [-Name <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureApplicationGateway** mendapatkan Gateway Aplikasi Azure yang sudah ada.

## EXAMPLES

### Contoh 1: Dapatkan Gateway Aplikasi
```
PS C:\> Get-AzureApplicationGateway -Name "ApplicationGateway06"
```

Perintah ini mendapatkan Gateway Aplikasi bernama ApplicationGateway06.

### Contoh 2: Dapatkan semua Gateway Aplikasi
```
PS C:\> Get-AzureApplicationGateway
```

Perintah ini akan mendapatkan semua Gateway Aplikasi di bawah langganan Anda.

## PARAMETERS

### -Nama
Menentukan nama Gateway Aplikasi yang akan didaangkan cmdlet ini.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGateway, IEnumerable<Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGateway>

## CATATAN

## RELATED LINKS

[New-AzureApplicationGateway](./New-AzureApplicationGateway.md)

[Remove-AzureApplicationGateway](./Remove-AzureApplicationGateway.md)

[Start-AzureApplicationGateway](./Start-AzureApplicationGateway.md)

[Stop-AzureApplicationGateway](./Stop-AzureApplicationGateway.md)

[Update-AzureApplicationGateway](./Update-AzureApplicationGateway.md)


