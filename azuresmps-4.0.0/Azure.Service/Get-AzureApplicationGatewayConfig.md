---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: A2F0ECAD-595C-45E6-98AC-2C7DB8E4BEF0
online version: ''
schema: 2.0.0
ms.openlocfilehash: 89be2a1fb9483a7514394acc28636abd40c01c2f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142095219"
---
# Get-AzureApplicationGatewayConfig

## SYNOPSIS
Mendapatkan konteks konfigurasi Application Gateway.

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

### Contoh 1: Dapatkan konfigurasi Application Gateway dan simpan ke file
```
PS C:\> Get-AzureApplicationGatewayConfig -Name "ApplicationGateway06" -ExportToFile "D:\config.xml"
```

Perintah ini mendapatkan konfigurasi untuk Application Gateway bernama ApplicationGateway06.
Perintah menyimpannya dalam file dalam jalur yang ditentukan.

## PARAMETERS

### -ExportToFile
Menentukan jalur file tempat cmdlet ini menyimpan konfigurasi dalam format XML.

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
Menentukan nama Application Gateway di mana cmdlet ini mendapatkan informasi konfigurasi.

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

### Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGatewayConfigContext

## CATATAN

## RELATED LINKS

[Set-AzureApplicationGatewayConfig](./Set-AzureApplicationGatewayConfig.md)


