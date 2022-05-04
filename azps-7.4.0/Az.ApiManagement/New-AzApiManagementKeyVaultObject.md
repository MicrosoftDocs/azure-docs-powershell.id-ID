---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementkeyvaultobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementKeyVaultObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementKeyVaultObject.md
ms.openlocfilehash: bbf080fdc62fce460340c786b4eb99b335b66992
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144570278"
---
# New-AzApiManagementKeyVaultObject

## SYNOPSIS
Membuat instans PsApiManagementKeyVaultObject.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/new-azapimanagementkeyvaultobject) untuk informasi terbaru.

## SYNTAX

```
New-AzApiManagementKeyVaultObject -SecretIdentifier <String> [-IdentityClientId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApiManagementKeyVaultObject** membuat instans PsApiManagementKeyVaultObjecte.

## EXAMPLES

### Contoh 1 : Membuat keyVault Namedvalue
```powershell
$secretIdentifier = 'https://contoso.vault.azure.net/secrets/xxxx'
$keyvault = New-AzApiManagementKeyVaultObject -SecretIdentifier $secretIdentifier 
$keyVaultNamedValue = New-AzApiManagementNamedValue -Context $context -NamedValueId $keyVaultNamedValueId -Name $keyVaultNamedValueName -keyVault $keyvault -Secret
```

Perintah pertama membuat keyvault.
Perintah kedua membuat nilai bernama menggunakan rahasia dari keyvault ini.

### Contoh 2 : Membuat Sertifikat keyVault
```powershell
$secretIdentifier = 'https://contoso.vault.azure.net/secrets/xxxx'
$keyvault = New-AzApiManagementKeyVaultObject -SecretIdentifier $secretIdentifier 
$keyVaultcert = New-AzApiManagementCertificate -Context $context -CertificateId $kvcertId -KeyVault $keyvault
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
Akan ditetapkan sistem default jika dikosongkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementKeyVaultEntity

## NOTES

## RELATED LINKS
