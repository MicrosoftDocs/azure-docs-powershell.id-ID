---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: D50984B7-FD97-4713-8E56-1C06D2B008E3
online version: ''
schema: 2.0.0
ms.openlocfilehash: e630cd21c8ec33d1bd20ae880797aa5c6acb6256
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141965979"
---
# Start-AzureApplicationGateway

## SYNOPSIS
Memulai gateway aplikasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Start-AzureApplicationGateway -Name <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureApplicationGateway** memulai gateway aplikasi.

## EXAMPLES

### Contoh 1: Memulai gateway aplikasi
```
PS C:\> Start-AzureApplicationGateway -Name "ApplicationGateway06"
```

Perintah ini memulai gateway aplikasi bernama ApplicationGateway06.

## PARAMETERS

### -Nama
Menentukan nama gateway aplikasi yang dimulai cmdlet ini.

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

### Microsoft.WindowsAzure.Management.ApplicationGateway.Models.ApplicationGatewayOperationResponse

## CATATAN

## RELATED LINKS

[Get-AzureApplicationGateway](./Get-AzureApplicationGateway.md)

[AzureApplicationGateway baru](./New-AzureApplicationGateway.md)

[Hapus-AzureApplicationGateway](./Remove-AzureApplicationGateway.md)

[Stop-AzureApplicationGateway](./Stop-AzureApplicationGateway.md)

[Update-AzureApplicationGateway](./Update-AzureApplicationGateway.md)


