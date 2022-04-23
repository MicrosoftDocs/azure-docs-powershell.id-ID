---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 6FFE1B64-C80B-423D-A043-55C90A224752
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewaysslcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewaySslCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewaySslCertificate.md
ms.openlocfilehash: 273f8e4bde9231f1df84fa5b57b2d00fdbdd79a7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143313749"
---
# New-AzApplicationGatewaySslCertificate

## SYNOPSIS
Membuat sertifikat SSL untuk gateway aplikasi Azure.

## SYNTAX

```
New-AzApplicationGatewaySslCertificate -Name <String> [-CertificateFile <String>] [-Password <SecureString>]
 [-KeyVaultSecretId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApplicationGatewaySslCertificate** membuat sertifikat SSL untuk gateway aplikasi Azure.

## EXAMPLES

### Contoh 1: Membuat sertifikat SSL untuk gateway aplikasi Azure.
```powershell
$password = ConvertTo-SecureString $passwordPlainString -AsPlainText -Force
$cert = New-AzApplicationGatewaySslCertificate -Name "Cert01" -CertificateFile "D:\cert01.pfx" -Password $password
```

Perintah ini membuat sertifikat SSL bernama Cert01 untuk gateway aplikasi default dan menyimpan hasilnya dalam variabel bernama $Cert.

### Contoh 2: Buat sertifikat SSL menggunakan KeyVault Secret (version-less secretId) dan tambahkan ke gateway aplikasi.
```powershell
$secret = Get-AzKeyVaultSecret -VaultName "keyvault01" -Name "sslCert01"
$secretId = $secret.Id.Replace($secret.Version, "") # https://<keyvaultname>.vault.azure.net/secrets/
$cert = New-AzApplicationGatewaySslCertificate -Name "Cert01" -KeyVaultSecretId $secretId
```

Dapatkan rahasia dan buat Sertifikat SSL menggunakan `New-AzApplicationGatewaySslCertificate`.
Catatan: Karena version-less secretId disediakan di sini, Application Gateway akan menyinkronkan sertifikat dalam interval reguler dengan KeyVault.

### Contoh 3: Membuat sertifikat SSL menggunakan KeyVault Secret dan tambahkan ke Gateway Aplikasi.
```powershell
$secret = Get-AzKeyVaultSecret -VaultName "keyvault01" -Name "sslCert01"
$secretId = $secret.Id # https://<keyvaultname>.vault.azure.net/secrets/<hash>
$cert = New-AzApplicationGatewaySslCertificate -Name "Cert01" -KeyVaultSecretId $secretId
```

Dapatkan rahasia dan buat Sertifikat SSL menggunakan `New-AzApplicationGatewaySslCertificate`.
Catatan: Jika diperlukan bahwa Application Gateway menyinkronkan sertifikat dengan KeyVault, harap sediakan version-less secretId.

## PARAMETERS

### -CertificateFile
Menentukan jalur file .pfx sertifikat SSL yang dibuat cmdlet ini.

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
SecretId (uri) dari KeyVault Secret. Gunakan opsi ini saat versi rahasia tertentu perlu digunakan.

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

### -Nama
Menentukan nama sertifikat SSL yang dibuat cmdlet ini.

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

### -Password
Menentukan kata sandi SSL yang dibuat cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslCertificate

## NOTES

## RELATED LINKS

[Add-AzApplicationGatewaySslCertificate](./Add-AzApplicationGatewaySslCertificate.md)

[Get-AzApplicationGatewaySslCertificate](./Get-AzApplicationGatewaySslCertificate.md)

[Remove-AzApplicationGatewaySslCertificate](./Remove-AzApplicationGatewaySslCertificate.md)

[Set-AzApplicationGatewaySslCertificate](./Set-AzApplicationGatewaySslCertificate.md)


