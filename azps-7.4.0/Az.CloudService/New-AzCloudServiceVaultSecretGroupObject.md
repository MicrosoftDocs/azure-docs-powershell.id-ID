---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/new-azcloudservicevaultsecretgroupobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceVaultSecretGroupObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceVaultSecretGroupObject.md
ms.openlocfilehash: 4a6907f72f569872db97e34fd8aa014fc276e163
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144631396"
---
# New-AzCloudServiceVaultSecretGroupObject

## SYNOPSIS
Membuat objek dalam memori untuk Grup Rahasia Vault

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cloudservice/new-azcloudservicevaultsecretgroupobject) untuk informasi terbaru.

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
Ini adalah URL sertifikat yang telah diunggah ke Key Vault sebagai rahasia.

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
Key Vault Id Sumber Daya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.CloudServiceVaultSecretGroup

## NOTES

ALIAS

## RELATED LINKS

