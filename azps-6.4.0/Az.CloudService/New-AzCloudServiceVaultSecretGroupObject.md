---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/new-azcloudservicevaultsecretgroupobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceVaultSecretGroupObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceVaultSecretGroupObject.md
ms.openlocfilehash: 41dc2de646fbc85de16ee36d5812d00260c2811a
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136195880"
---
# New-AzCloudServiceVaultSecretGroupObject

## SYNOPSIS
Membuat objek dalam memori untuk Grup Rahasia Vault

## SYNTAX

```
New-AzCloudServiceVaultSecretGroupObject [-CertificateUrl <String[]>] [-Id <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk Grup Rahasia

## EXAMPLES

### Contoh 1: Membuat objek grup rahasia vault
```powershell
$keyVault = Get-AzKeyVault -VaultName 'ContosoKeyVault'
$certificate = Get-AzKeyVaultCertificate -VaultName 'ContosoKeyVault' -Name 'ContosoCert'
$secretGroup = New-AzCloudServiceVaultSecretGroupObject -Id $keyVault.ResourceId -CertificateUrl $certificate.SecretId
```

Perintah ini membuat objek grup rahasia vault yang digunakan untuk membuat atau memperbarui layanan cloud.
Untuk detail selengkapnya, lihat New-AzCloudService.

## PARAMETERS

### -CertificateUrl
Url ini adalah sertifikat yang telah diunggah ke Key Vault sebagai rahasia.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Id Sumber Daya Key Vault.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.CloudServiceVaultSecretGroup

## CATATAN

ALIAS

## RELATED LINKS

