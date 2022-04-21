---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 98AC0FAA-4786-4172-908E-FEB8588B0D74
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1eae51b014c2c5dd9f9ed44b59205775157c162e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142723708"
---
# Remove-AzureApplicationGatewaySslCertificate

## SYNOPSIS
Menghapus sertifikat SSL dari gateway aplikasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureApplicationGatewaySslCertificate -Name <String> -CertificateName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureApplicationGatewaySslCertificate** menghapus sertifikat Secure Sockets Layer (SSL) dari gateway aplikasi.

## EXAMPLES

### Contoh 1: Menghapus sertifikat SSL
```
PS C:\> Remove-AzureApplicationGatewaySslCertificate -Name "ApplicationGateway08" -CertificateName "SslCertificate13"
```

Perintah ini menghapus sertifikat SSL bernama SslCertificate13 dari gateway aplikasi bernama ApplicationGateway08.

## PARAMETERS

### -CertificateName
Menentukan nama sertifikat SSL.
Cmdlet ini menghapus sertifikat yang ditentukan parameter ini.

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

### -Nama
Menentukan nama gateway aplikasi tempat cmdlet ini menghapus sertifikat SSL.

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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewaySslCertificate](./Add-AzureApplicationGatewaySslCertificate.md)

[Get-AzureApplicationGatewaySslCertificate](./Get-AzureApplicationGatewaySslCertificate.md)
