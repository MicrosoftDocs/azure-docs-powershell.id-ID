---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 6FFE1B64-C80B-423D-A043-55C90A224752
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewaysslcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewaySslCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewaySslCertificate.md
ms.openlocfilehash: 16f8a1211b74b63402a1476667b8dcfcfb7de969
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145677028"
---
# New-AzApplicationGatewaySslCertificate

## SYNOPSIS
Membuat sertifikat SSL untuk gateway aplikasi Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azapplicationgatewaysslcertificate) untuk informasi terbaru.

## SYNTAX

```
New-AzApplicationGatewaySslCertificate -Name <String> [-CertificateFile <String>] [-Password <SecureString>]
 [-KeyVaultSecretId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApplicationGatewaySslCertificate** membuat sertifikat SSL untuk gateway aplikasi Azure.

## EXAMPLES

### Contoh 1: Buat sertifikat SSL untuk gateway aplikasi Azure.
```powershell
$password = ConvertTo-SecureString $passwordPlainString -AsPlainText -Force
$cert = New-AzApplicationGatewaySslCertificate -Name "Cert01" -CertificateFile "D:\cert01.pfx" -Password $password
```

Perintah ini membuat sertifikat SSL bernama Cert01 untuk gateway aplikasi default dan menyimpan hasilnya dalam variabel bernama $Cert.

### Contoh 2: Buat sertifikat SSL menggunakan Rahasia KeyVault (secretId tanpa versi) dan tambahkan ke gateway aplikasi.
```powershell
$secret = Get-AzKeyVaultSecret -VaultName "keyvault01" -Name "sslCert01"
$secretId = $secret.Id.Replace($secret.Version, "") # https://<keyvaultname>.vault.azure.net/secrets/
$cert = New-AzApplicationGatewaySslCertificate -Name "Cert01" -KeyVaultSecretId $secretId
```

Dapatkan rahasia dan buat Sertifikat SSL menggunakan `New-AzApplicationGatewaySslCertificate`.
Catatan: Karena secretId tanpa versi disediakan di sini, Application Gateway akan menyinkronkan sertifikat secara berkala dengan KeyVault.

### Contoh 3: Buat sertifikat SSL menggunakan Rahasia KeyVault dan tambahkan ke Application Gateway.
```powershell
$secret = Get-AzKeyVaultSecret -VaultName "keyvault01" -Name "sslCert01"
$secretId = $secret.Id # https://<keyvaultname>.vault.azure.net/secrets/<hash>
$cert = New-AzApplicationGatewaySslCertificate -Name "Cert01" -KeyVaultSecretId $secretId
```

Dapatkan rahasia dan buat Sertifikat SSL menggunakan `New-AzApplicationGatewaySslCertificate`.
Catatan: Jika diperlukan bahwa Application Gateway menyinkronkan sertifikat dengan KeyVault, berikan secretId tanpa versi.

## PARAMETERS

### -CertificateFile
Menentukan jalur file .pfx dari sertifikat SSL yang dibuat cmdlet ini.

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

### -Kata sandi
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslCertificate

## NOTES

## RELATED LINKS

[Add-AzApplicationGatewaySslCertificate](./Add-AzApplicationGatewaySslCertificate.md)

[Get-AzApplicationGatewaySslCertificate](./Get-AzApplicationGatewaySslCertificate.md)

[Remove-AzApplicationGatewaySslCertificate](./Remove-AzApplicationGatewaySslCertificate.md)

[Set-AzApplicationGatewaySslCertificate](./Set-AzApplicationGatewaySslCertificate.md)


