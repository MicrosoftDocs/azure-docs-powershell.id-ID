---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementkeyvaultobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementKeyVaultObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementKeyVaultObject.md
ms.openlocfilehash: 2aee02a1452fef85e06565bea4d20c531e3f1cb3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142971119"
---
# New-AzApiManagementKeyVaultObject

## SYNOPSIS
Membuat contoh PsApiManagementKeyVaultObject.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/new-azapimanagementkeyvaultobject) untuk informasi terbaru.

## SYNTAX

```
New-AzApiManagementKeyVaultObject -SecretIdentifier <String> [-IdentityClientId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApiManagementKeyVaultObject** membuat contoh PsApiManagementKeyVaultObjecte.

## EXAMPLES

### Contoh 1 : Membuat keyVault Bernamavalue
```powershell
PS C:\>$secretIdentifier = 'https://contoso.vault.azure.net/secrets/xxxx'
PS C:\>$keyvault = New-AzApiManagementKeyVaultObject -SecretIdentifier $secretIdentifier 
PS C:\>$keyVaultNamedValue = New-AzApiManagementNamedValue -Context $context -NamedValueId $keyVaultNamedValueId -Name $keyVaultNamedValueName -keyVault $keyvault -Secret
```

Perintah pertama membuat keyvault.
Perintah kedua membuat nilai bernama menggunakan secret dari keyvault ini.

### Contoh 2 : Membuat sertifikat keyVault
```powershell
PS C:\>$secretIdentifier = 'https://contoso.vault.azure.net/secrets/xxxx'
PS C:\>$keyvault = New-AzApiManagementKeyVaultObject -SecretIdentifier $secretIdentifier 
PS C:\>$keyVaultcert = New-AzApiManagementCertificate -Context $context -CertificateId $kvcertId -KeyVault $keyvault
```

Perintah pertama membuat keyvault.
Perintah kedua membuat sertifikat menggunakan rahasia dari keyvault ini.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -IdentityClientId
Id Klien Identitas identitas identitas terkelola yang ditetapkan pengguna.
Akan ditetapkan sistem default jika dibiarkan kosong.

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

### -SecretIdentifier
Pengidentifikasi Rahasia Key Vault ini.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementKeyVaultEntity

## NOTES

## RELATED LINKS
