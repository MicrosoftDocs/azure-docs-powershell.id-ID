---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 5CBEDFF8-C441-44CC-B011-5F5AAFA2E5C6
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementCertificate.md
ms.openlocfilehash: c3d68add2f2e720323a9a4e864429aa21c9c9335
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143099152"
---
# New-AzApiManagementCertificate

## SYNOPSIS
Membuat sertifikat API Management yang akan digunakan selama Autentikasi dengan Backend.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/new-azapimanagementcertificate) untuk informasi terbaru.

## SYNTAX

### LoadFromFile (Default)
```
New-AzApiManagementCertificate -Context <PsApiManagementContext> [-CertificateId <String>]
 [-PfxFilePath <String>] [-PfxPassword <String>] [-KeyVault <PsApiManagementKeyVaultEntity>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Mentah
```
New-AzApiManagementCertificate -Context <PsApiManagementContext> [-CertificateId <String>] [-PfxBytes <Byte[]>]
 [-PfxPassword <String>] [-KeyVault <PsApiManagementKeyVaultEntity>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApiManagementCertificate** membuat sertifikat API Management Azure.

## EXAMPLES

### Contoh 1: Membuat dan mengunggah sertifikat
```powershell
PS C:\>$ApiMgmtContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
PS C:\>New-AzApiManagementCertificate -Context $ApiMgmtContext -PfxFilePath "C:\contoso\certificates\apimanagement.pfx" -PfxPassword "1111"
```

Perintah ini mengunggah sertifikat ke Manajemen Api. Sertifikat ini bisa digunakan untuk autentikasi bersama dengan backend menggunakan kebijakan.

### Contoh 2

Membuat sertifikat API Management yang akan digunakan selama Autentikasi dengan Backend. (autogenerasi)

```powershell
<!-- Aladdin Generated Example --> 
New-AzApiManagementCertificate -CertificateId '0123456789' -Context <PsApiManagementContext> -PfxFilePath 'C:\contoso\certificates\apimanagement.pfx' -PfxPassword '1111'
```

### Contoh 3 : Membuat sertifikat keyVault
```powershell
PS C:\>$secretIdentifier = 'https://contoso.vault.azure.net/secrets/xxxx'
PS C:\>$keyvault = New-AzApiManagementKeyVaultObject -SecretIdentifier $secretIdentifier 
PS C:\>$keyVaultcert = New-AzApiManagementCertificate -Context $context -CertificateId $kvcertId -KeyVault $keyvault
```

Perintah pertama membuat keyvault.
Perintah kedua membuat sertifikat menggunakan rahasia dari keyvault ini.

## PARAMETERS

### -CertificateId
Menentukan ID sertifikat yang akan dibuat.
Jika Anda tidak menentukan parameter ini, ID akan dibuat untuk Anda.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konteks
Menentukan objek **PsApiManagementContext** .

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -KeyVault
KeyVault digunakan untuk mengambil data sertifikat. Parameter ini diperlukan jika -PfxFilePath tidak ditentukan.
Lihat New-AzApiManagementKeyVaultObject untuk detailnya.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementKeyVaultEntity
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PfxBytes
Menentukan array byte file sertifikat dalam format .pfx.
Parameter ini diperlukan jika Anda tidak menentukan parameter *PfxFilePath* .

```yaml
Type: System.Byte[]
Parameter Sets: Raw
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PfxFilePath
Menentukan jalur ke file sertifikat dalam format .pfx untuk dibuat dan diunggah.
Parameter ini diperlukan jika Anda tidak menentukan parameter *PfxBytes* .

```yaml
Type: System.String
Parameter Sets: LoadFromFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PfxPassword
Menentukan kata sandi untuk sertifikat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

### System.String

### System.Byte[]

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementCertificate

## NOTES

## RELATED LINKS

[Get-AzApiManagementCertificate](./Get-AzApiManagementCertificate.md)

[Remove-AzApiManagementCertificate](./Remove-AzApiManagementCertificate.md)

[Set-AzApiManagementCertificate](./Set-AzApiManagementCertificate.md)


