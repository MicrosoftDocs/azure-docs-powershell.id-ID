---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 17BA2ED5-E347-45C0-AF20-CDD288469514
online version: ''
schema: 2.0.0
ms.openlocfilehash: 02c001d3ce4a2372e38debccc60b4c5eea2d060c
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428023"
---
# Stop-AzureApplicationGateway

## SYNOPSIS
Menghentikan gateway aplikasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Stop-AzureApplicationGateway -Name <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Stop-AzureApplicationGateway** menghentikan gateway aplikasi.

## EXAMPLES

### Contoh 1: Menghentikan gateway aplikasi
```
PS C:\> Stop-AzureApplicationGateway -Name "ApplicationGateway06"
```

Perintah ini menghentikan gateway aplikasi bernama ApplicationGateway06.

## PARAMETERS

### -Nama
Menentukan nama gateway aplikasi yang perhentian cmdlet ini.

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

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### Microsoft.WindowsAzure.Management.ApplicationGateway.Models.ApplicationGatewayOperationResponse

## CATATAN

## RELATED LINKS

[Get-AzureApplicationGateway](./Get-AzureApplicationGateway.md)

[New-AzureApplicationGateway](./New-AzureApplicationGateway.md)

[Remove-AzureApplicationGateway](./Remove-AzureApplicationGateway.md)

[Start-AzureApplicationGateway](./Start-AzureApplicationGateway.md)

[Update-AzureApplicationGateway](./Update-AzureApplicationGateway.md)
