---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: D7C275E5-BC43-454B-BF1E-48D639C4B4F0
online version: https://docs.microsoft.com/powershell/module/az.network/set-azapplicationgatewaysslcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzApplicationGatewaySslCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzApplicationGatewaySslCertificate.md
ms.openlocfilehash: c59368aacb70da0cf4c2e31de3fbe2ffa58d5d2d
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144583292"
---
# Set-AzApplicationGatewaySslCertificate

## SYNOPSIS
Memperbarui sertifikat SSL untuk gateway aplikasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/set-azapplicationgatewaysslcertificate) untuk informasi terbaru.

## SYNTAX

```
Set-AzApplicationGatewaySslCertificate -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-CertificateFile <String>] [-Password <SecureString>] [-KeyVaultSecretId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzApplicationGatewaySslCertificate** memperbarui sertifikat SSL untuk gateway aplikasi.

## EXAMPLES

### Contoh 1: Memperbarui sertifikat SSL yang ada di Application Gateway
```powershell
$appGW = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$password = ConvertTo-SecureString $passwordPlainString -AsPlainText -Force
$cert = Set-AzApplicationGatewaySslCertificate -ApplicationGateway $AppGW -Name "Cert01" -CertificateFile "D:\cert01.pfx" -Password $password
```

Perbarui sertifikat SSL yang ada untuk gateway aplikasi bernama ApplicationGateway01.

### Contoh 2: Memperbarui sertifikat SSL yang ada menggunakan Rahasia KeyVault (secretId tanpa versi) di Application Gateway
```powershell
$secret = Get-AzKeyVaultSecret -VaultName "keyvault01" -Name "sslCert01"
$secretId = $secret.Id.Replace($secret.Version, "") # https://<keyvaultname>.vault.azure.net/secrets/
$cert = Set-AzApplicationGatewaySslCertificate -ApplicationGateway $AppGW -Name "Cert01" -KeyVaultSecretId $secretId
```

Dapatkan rahasia dan perbarui Sertifikat SSL yang ada menggunakan `Set-AzApplicationGatewaySslCertificate`.

### Contoh 3: Memperbarui sertifikat SSL yang ada menggunakan Rahasia KeyVault di Application Gateway
```powershell
$secret = Get-AzKeyVaultSecret -VaultName "keyvault01" -Name "sslCert01"
$secretId = $secret.Id # https://<keyvaultname>.vault.azure.net/secrets/<hash>
$cert = Set-AzApplicationGatewaySslCertificate -ApplicationGateway $AppGW -Name "Cert01" -KeyVaultSecretId $secretId
```

Dapatkan rahasia dan perbarui Sertifikat SSL yang ada menggunakan `Set-AzApplicationGatewaySslCertificate`.
Catatan: Jika diperlukan bahwa Application Gateway menyinkronkan sertifikat dengan KeyVault, berikan secretId tanpa versi.

## PARAMETERS

### -ApplicationGateway
Menentukan gateway aplikasi tempat sertifikat Secure Socket Layer (SSL) dikaitkan.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGateway
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CertificateFile
Menentukan jalur sertifikat SSL.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultSecretId
SecretId (uri) dari Rahasia KeyVault. Gunakan opsi ini ketika versi rahasia tertentu perlu digunakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Menentukan nama sertifikat SSL.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kata sandi
Menentukan kata sandi sertifikat SSL.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES

## RELATED LINKS

[Add-AzApplicationGatewaySslCertificate](./Add-AzApplicationGatewaySslCertificate.md)

[Get-AzApplicationGatewaySslCertificate](./Get-AzApplicationGatewaySslCertificate.md)

[New-AzApplicationGatewaySslCertificate](./New-AzApplicationGatewaySslCertificate.md)

[Remove-AzApplicationGatewaySslCertificate](./Remove-AzApplicationGatewaySslCertificate.md)


