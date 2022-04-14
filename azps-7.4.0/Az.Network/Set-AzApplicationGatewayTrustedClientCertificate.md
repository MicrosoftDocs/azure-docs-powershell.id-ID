---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/set-azapplicationgatewaytrustedclientcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzApplicationGatewayTrustedClientCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzApplicationGatewayTrustedClientCertificate.md
ms.openlocfilehash: 0b5adb95ee06bd6e1d0420e5ef0dab532150a1f5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141994931"
---
# Set-AzApplicationGatewayTrustedClientCertificate

## SYNOPSIS
Mengubah rantai sertifikat CA klien tepercaya gateway aplikasi.

## SYNTAX

```
Set-AzApplicationGatewayTrustedClientCertificate -ApplicationGateway <PSApplicationGateway> -Name <String>
 -CertificateFile <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzApplicationGatewayTrustedClientCertificate** mengubah rantai sertifikat CA klien tepercaya gateway aplikasi.

## EXAMPLES

### Contoh 1
```powershell
$gw = Get-AzApplicationGateway -Name $appgwName -ResourceGroupName $resgpName
$gw = Set-AzApplicationGatewayTrustedClientCertificate -ApplicationGateway $gw -Name $certName --CertificateFile ".\clientCAUpdated.cer"
$gw = Set-AzApplicationGateway -ApplicationGateway $gw
```

Contoh skenario di atas memperlihatkan cara memperbarui objek rantai sertifikat CA klien tepercaya yang sudah ada. Perintah pertama mendapatkan gateway aplikasi dan menyimpannya dalam variabel $gw. Perintah kedua mengubah objek rantai sertifikat CA klien tepercaya yang sudah ada dengan file rantai sertifikat CA baru. Perintah ketiga memperbarui gateway aplikasi di Azure.

## PARAMETERS

### -ApplicationGateway
ApplicationGateway

```yaml
Type: PSApplicationGateway
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CertificateFile
Jalur file rantai sertifikat CA klien tepercaya

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama rantai sertifikat CA klien tepercaya

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## CATATAN

## RELATED LINKS

[Add-AzApplicationGatewayTrustedClientCertificate](./Add-AzApplicationGatewayTrustedClientCertificate.md)

[New-AzApplicationGatewayTrustedClientCertificate](./New-AzApplicationGatewayTrustedClientCertificate.md)

[Get-AzApplicationGatewayTrustedClientCertificate](./Get-AzApplicationGatewayTrustedClientCertificate.md)

[Remove-AzApplicationGatewayTrustedClientCertificate](./Remove-AzApplicationGatewayTrustedClientCertificate.md)