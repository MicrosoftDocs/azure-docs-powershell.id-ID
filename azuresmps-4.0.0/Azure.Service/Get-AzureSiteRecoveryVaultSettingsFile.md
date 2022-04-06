---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: AFAA1BDF-3F6A-437A-ADC2-C5EBD970F57D
online version: ''
schema: 2.0.0
ms.openlocfilehash: 777a1a6063eb0d318594aaaf9c1280bdc95333ee
ms.sourcegitcommit: ea4f0db405efec935ac72601b51807dbb45674c9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/28/2022
ms.locfileid: "132415664"
---
# Get-AzureSiteRecoveryVaultSettingsFile

## SYNOPSIS
Mendapatkan file pengaturan vault Pemulihan Situs.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByParam (Default)
```
Get-AzureSiteRecoveryVaultSettingsFile -Name <String> -Location <String> [-SiteName <String>]
 [-SiteId <String>] [-Path <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByObject
```
Get-AzureSiteRecoveryVaultSettingsFile -Vault <ASRVault> [-Site <ASRSite>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSiteRecoveryVaultSettingsFile** mendapatkan file pengaturan untuk vault Pemulihan Situs Azure.

## EXAMPLES

### Contoh 1: Mendapatkan file pengaturan untuk vault
```
PS C:\> $Vault = Get-AzureSiteRecoveryVault -Name "ContosoVault"
PS C:\> Get-AzureSiteRecoveryVaultSettingsFile -Vault $Vault
FilePath 
-------- 
C:\Users\ContosoAdmin\ContosoVault_2015-02-02T05-39-23.VaultCredentials
```

Perintah pertama mendapatkan penyimpanan Pemulihan Situs Azure aktif bernama ContosoVault menggunakan cmdlet **Get-AzureSiteRecoveryVault** .
Perintah menyimpan vault tersebut di $Vault variabel.

Perintah kedua akan mendapatkan file pengaturan untuk vault yang disimpan di $Vault.

## PARAMETERS

### -Lokasi
Menentukan lokasi geografis tempat penyimpanan berada.

```yaml
Type: String
Parameter Sets: ByParam
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama vault.

```yaml
Type: String
Parameter Sets: ByParam
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Menentukan jalur file pengaturan vault Pemulihan Situs.
Untuk menyimpan file ini secara lokal, unduh dari portal vault Pemulihan Situs setelah perintah selesai dijalankan.

```yaml
Type: String
Parameter Sets: ByParam
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Situs
Menentukan situs untuk mendapatkan file pengaturan.
Untuk mendapatkan objek **Situs** , gunakan cmdlet **Get-AzureSiteRecoverySite** .

```yaml
Type: ASRSite
Parameter Sets: ByObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteId
Menentukan ID situs.

```yaml
Type: String
Parameter Sets: ByParam
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteName
Menentukan nama situs.

```yaml
Type: String
Parameter Sets: ByParam
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vault
Menentukan vault untuk situs tersebut.

```yaml
Type: ASRVault
Parameter Sets: ByObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoverySite](./Get-AzureSiteRecoverySite.md)

[Get-AzureSiteRecoveryVault](./Get-AzureSiteRecoveryVault.md)

[Get-AzureSiteRecoveryVaultSettings](./Get-AzureSiteRecoveryVaultSettings.md)

[Import-AzureSiteRecoveryVaultSettingsFile](./Import-AzureSiteRecoveryVaultSettingsFile.md)


