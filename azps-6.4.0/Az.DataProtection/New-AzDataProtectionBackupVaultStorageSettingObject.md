---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionbackupvaultstoragesettingobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupVaultStorageSettingObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupVaultStorageSettingObject.md
ms.openlocfilehash: 6120dc17ebd4743db0f205cf70d8f2899bed1deb
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136204899"
---
# New-AzDataProtectionBackupVaultStorageSettingObject

## SYNOPSIS
Dapatkan objek pengaturan penyimpanan Vault Cadangan

## SYNTAX

```
New-AzDataProtectionBackupVaultStorageSettingObject -DataStoreType <DataStoreType> -Type <StorageSettingType>
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan objek pengaturan penyimpanan Vault Cadangan

## EXAMPLES

### Contoh 1: Membuat objek pengaturan penyimpanan vault baru
```powershell
PS C:\> New-AzDataProtectionBackupVaultStorageSettingObject -Type GeoRedundant -DataStoreType VaultStore

DatastoreType Type
------------- ----
VaultStore    GeoRedundant
```

Perintah ini akan membuat objek pengaturan penyimpanan vault baru yang digunakan untuk membuat cadangan vault.

## PARAMETERS

### -DataStoreType
Tipe Penyimpanan Data vault

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.DataStoreType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Storage Tipe vault

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.StorageSettingType
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

## OUTPUTS

### System.Management.Automation.PSObject

## CATATAN

ALIAS

## RELATED LINKS

