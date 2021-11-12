---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: D2CE5D4B-8F1F-41FF-9E65-8956FEDD35AE
online version: ''
schema: 2.0.0
ms.openlocfilehash: dec77ee53622435302ea80300f2f03cfa3d999c0
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132419927"
---
# Get-AzureApplicationGatewaySslCertificate

## SYNOPSIS
Mendapatkan sertifikat Application Gateway.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureApplicationGatewaySslCertificate -Name <String> [-CertificateName <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureApplicationGatewaySslCertificate** mendapatkan sertifikat Secure Sockets Layer (SSL) untuk Gateway Aplikasi Azure.

## EXAMPLES

### Contoh 1: Mendapatkan sertifikat SSL
```
PS C:\> Get-AzureApplicationGatewaySslCertificate -Name "ApplicationGateway08" -CertificateName "SslCertificate13"
```

Perintah ini mendapatkan sertifikat SSL yang bernama SslCertificate13 di Gateway Aplikasi yang bernama ApplicationGateway08.

### Contoh 2: Mendapatkan semua sertifikat SSL
```
PS C:\> Get-AzureApplicationGatewaySslCertificate -Name "ApplicationGateway08"
```

Perintah ini mendapatkan semua sertifikat SSL pada Gateway Aplikasi bernama ApplicationGateway08.

## PARAMETERS

### -CertificateName
Menentukan nama sertifikat SSL.
Cmdlet ini mendapatkan sertifikat yang ditentukan parameter ini.

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

### -Nama
Menentukan nama Gateway Aplikasi asal cmdlet ini mendapatkan sertifikat SSL.

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

### Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGatewayCertificate, List<Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGatewayCertificate>

## CATATAN

## RELATED LINKS

[Add-AzureApplicationGatewaySslCertificate](./Add-AzureApplicationGatewaySslCertificate.md)

[Remove-AzureApplicationGatewaySslCertificate](./Remove-AzureApplicationGatewaySslCertificate.md)
