---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
Module Name: AzureRM
ms.assetid: 9595E785-6DBF-433C-83B3-8506A3B49B13
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.siterecovery/get-azurermsiterecoveryvaultsettingsfile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Get-AzureRmSiteRecoveryVaultSettingsFile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Get-AzureRmSiteRecoveryVaultSettingsFile.md
ms.openlocfilehash: 621e5ac05c5f975ff3878781bcb8c5a1b40c04bf
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421764"
---
# Get-AzureRmSiteRecoveryVaultSettingsFile

## SYNOPSIS
Mendapatkan file pengaturan vault Pemulihan Situs.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByParam (Default)
```
Get-AzureRmSiteRecoveryVaultSettingsFile [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Default
```
Get-AzureRmSiteRecoveryVaultSettingsFile -Vault <ASRVault> [-Path <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ForSite
```
Get-AzureRmSiteRecoveryVaultSettingsFile -Vault <ASRVault> -SiteIdentifier <String> -SiteFriendlyName <String>
 [-Path <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmSiteRecoveryVaultSettingsFile** mendapatkan file pengaturan untuk vault Pemulihan Situs Azure.

## EXAMPLES

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Menentukan jalur ke file pengaturan vault Pemulihan Situs.
Untuk menyimpan file ini secara lokal, unduh dari portal vault Pemulihan Situs setelah perintah selesai.

```yaml
Type: String
Parameter Sets: Default, ForSite
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteFriendlyName
Menentukan nama yang mudah digunakan untuk vault ketika situs merupakan situs Hyper-V.

```yaml
Type: String
Parameter Sets: ForSite
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteIdentifier
Menentukan pengidentifikasi situs untuk vault jika situs merupakan situs Hyper-V.

```yaml
Type: String
Parameter Sets: ForSite
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vault
Menentukan objek vault untuk situs.

```yaml
Type: ASRVault
Parameter Sets: Default, ForSite
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### ASRVault
Parameter 'Vault' menerima nilai tipe 'ASRVault' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.SiteRecovery.VaultSettingsFilePath

## CATATAN

## RELATED LINKS

[Import-AzureRmSiteRecoveryVaultSettingsFile](./Import-AzureRmSiteRecoveryVaultSettingsFile.md)

[Set-AzureRmSiteRecoveryVaultSettings](./Set-AzureRmSiteRecoveryVaultSettings.md)
