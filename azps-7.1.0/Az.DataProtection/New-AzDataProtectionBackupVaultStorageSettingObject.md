---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionbackupvaultstoragesettingobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupVaultStorageSettingObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupVaultStorageSettingObject.md
ms.openlocfilehash: 6120dc17ebd4743db0f205cf70d8f2899bed1deb
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136583363"
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

