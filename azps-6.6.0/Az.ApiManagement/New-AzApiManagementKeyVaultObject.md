---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementkeyvaultobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementKeyVaultObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementKeyVaultObject.md
ms.openlocfilehash: 8f0f49cf6796e096cd98e14a8abda52dd3341c20
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136341702"
---
# New-AzApiManagementKeyVaultObject

## SYNOPSIS
Membuat contoh PsApiManagementKeyVaultObject.

## SYNTAX

```
New-AzApiManagementKeyVaultObject -SecretIdentifier <String> [-IdentityClientId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApiManagementKeyVaultObject** membuat contoh PsApiManagementKeyVaultObjecte.

## EXAMPLES

### Contoh 1 : Membuat kunciVault Namedvalue
```powershell
PS C:\>$secretIdentifier = 'https://contoso.vault.azure.net/secrets/xxxx'
PS C:\>$keyvault = New-AzApiManagementKeyVaultObject -SecretIdentifier $secretIdentifier 
PS C:\>$keyVaultNamedValue = New-AzApiManagementNamedValue -Context $context -NamedValueId $keyVaultNamedValueId -Name $keyVaultNamedValueName -keyVault $keyvault -Secret
```

Perintah pertama membuat keyvault.
Perintah kedua membuat nilai bernama menggunakan rahasia dari keyvault ini.

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
Id Klien Identitas dari Identitas Terkelola yang ditetapkan pengguna.
Akan ditetapkan sistem default jika biarkan kosong.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementKeyVaultEntity

## CATATAN

## RELATED LINKS
