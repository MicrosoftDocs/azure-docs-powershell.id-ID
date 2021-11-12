---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: A2F0ECAD-595C-45E6-98AC-2C7DB8E4BEF0
online version: ''
schema: 2.0.0
ms.openlocfilehash: 89be2a1fb9483a7514394acc28636abd40c01c2f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132419498"
---
# Get-AzureApplicationGatewayConfig

## SYNOPSIS
Mendapatkan konteks konfigurasi Gateway Aplikasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureApplicationGatewayConfig -Name <String> [-ExportToFile <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureApplicationGatewayConfig** mendapatkan konteks konfigurasi Azure Application Gateway.
Konteks mencakup objek konfigurasi dan konfigurasi XML.
Anda bisa menyimpan konfigurasi XML ke file.

## EXAMPLES

### Contoh 1: Dapatkan konfigurasi Gateway Aplikasi dan simpan ke file
```
PS C:\> Get-AzureApplicationGatewayConfig -Name "ApplicationGateway06" -ExportToFile "D:\config.xml"
```

Perintah ini mendapatkan konfigurasi untuk Gateway Aplikasi bernama ApplicationGateway06.
Perintah menyimpannya dalam file di jalur yang ditentukan.

## PARAMETERS

### -ExportToFile
Menentukan jalur file di mana cmdlet ini menyimpan konfigurasi dalam format XML.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama Gateway Aplikasi di mana cmdlet ini mendapatkan informasi konfigurasi.

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

### Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGatewayConfigContext

## CATATAN

## RELATED LINKS

[Set-AzureApplicationGatewayConfig](./Set-AzureApplicationGatewayConfig.md)


