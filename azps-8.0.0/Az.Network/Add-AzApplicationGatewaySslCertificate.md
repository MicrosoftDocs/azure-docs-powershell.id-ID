---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 7EC4C642-1D23-4699-AE00-6E180C38271E
online version: https://docs.microsoft.com/powershell/module/az.network/add-azapplicationgatewaysslcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzApplicationGatewaySslCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzApplicationGatewaySslCertificate.md
ms.openlocfilehash: 8cd87bcaac12294ccb644f40f7e07fbf2ebc62a8
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145561230"
---
# Add-AzApplicationGatewaySslCertificate

## SYNOPSIS
Menambahkan sertifikat SSL ke gateway aplikasi.

## SYNTAX

```
Add-AzApplicationGatewaySslCertificate -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-CertificateFile <String>] [-Password <SecureString>] [-KeyVaultSecretId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzApplicationGatewaySslCertificate** menambahkan sertifikat SSL ke gateway aplikasi.

## EXAMPLES

### Contoh 1: Tambahkan sertifikat SSL menggunakan pfx ke gateway aplikasi.
```powershell
$AppGW = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$password = ConvertTo-SecureString $passwordPlainString -AsPlainText -Force
$AppGW = Add-AzApplicationGatewaySslCertificate -ApplicationGateway $AppGW -Name "Cert01" -CertificateFile "D:\cert01.pfx" -Password $password
```

Perintah ini mendapatkan gateway aplikasi bernama ApplicationGateway01 dan kemudian menambahkan sertifikat SSL bernama Cert01 ke dalamnya.

### Contoh 2: Tambahkan sertifikat SSL menggunakan Rahasia KeyVault (secretId tanpa versi) ke gateway aplikasi.
```powershell
$AppGW = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$secret = Get-AzKeyVaultCertificate -VaultName "keyvault01" -Name "sslCert01"
$secretId = $secret.SecretId.Replace($secret.Version, "") # https://<keyvaultname>.vault.azure.net/secrets/
$AppGW = Add-AzApplicationGatewaySslCertificate -ApplicationGateway $AppGW -Name "Cert01" -KeyVaultSecretId $secretId
```

Dapatkan rahasia dan referensikan di `Add-AzApplicationGatewaySslCertificate` untuk menambahkannya ke Application Gateway dengan nama `Cert01`.
Catatan: Karena secretId tanpa versi disediakan di sini, Application Gateway akan menyinkronkan sertifikat secara berkala dengan KeyVault.

### Contoh 3: Tambahkan sertifikat SSL menggunakan Rahasia KeyVault (secretId versi) ke gateway aplikasi.
```powershell
$AppGW = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
$secret = Get-AzKeyVaultCertificate -VaultName "keyvault01" -Name "sslCert01"
$secretId = $secret.Id # https://<keyvaultname>.vault.azure.net/secrets/<hash>
$AppGW = Add-AzApplicationGatewaySslCertificate -ApplicationGateway $AppGW -Name "Cert01" -KeyVaultSecretId $secretId
```

Dapatkan rahasia dan referensikan di `Add-AzApplicationGatewaySslCertificate` untuk menambahkannya ke Application Gateway dengan nama `Cert01`.
Catatan: Jika diperlukan bahwa Application Gateway menyinkronkan sertifikat dengan KeyVault, berikan secretId tanpa versi.

## PARAMETERS

### -ApplicationGateway
Menentukan nama gateway aplikasi tempat cmdlet ini menambahkan sertifikat SSL.

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
Menentukan file .pfx dari sertifikat SSL yang ditambahkan cmdlet ini.

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
Menentukan nama sertifikat SSL yang ditambahkan cmdlet ini.

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
Menentukan kata sandi sertifikat SSL yang ditambahkan cmdlet ini.

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

[Get-AzApplicationGatewaySslCertificate](./Get-AzApplicationGatewaySslCertificate.md)

[New-AzApplicationGatewaySslCertificate](./New-AzApplicationGatewaySslCertificate.md)

[Remove-AzApplicationGatewaySslCertificate](./Remove-AzApplicationGatewaySslCertificate.md)

[Set-AzApplicationGatewaySslCertificate](./Set-AzApplicationGatewaySslCertificate.md)


