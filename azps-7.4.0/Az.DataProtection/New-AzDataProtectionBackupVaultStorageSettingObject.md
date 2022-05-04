---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionbackupvaultstoragesettingobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupVaultStorageSettingObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupVaultStorageSettingObject.md
ms.openlocfilehash: 9694d1fee5e6a2c0f7fe14a29ae3661e35ea9ad5
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144675970"
---
# New-AzDataProtectionBackupVaultStorageSettingObject

## SYNOPSIS
Mendapatkan objek pengaturan penyimpanan Backup Vault

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/new-azdataprotectionbackupvaultstoragesettingobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDataProtectionBackupVaultStorageSettingObject -DataStoreType <DataStoreType> -Type <StorageSettingType>
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan objek pengaturan penyimpanan Backup Vault

## EXAMPLES

### Contoh 1: Membuat objek pengaturan penyimpanan vault baru
```powershell
New-AzDataProtectionBackupVaultStorageSettingObject -Type GeoRedundant -DataStoreType VaultStore
```

```output
DatastoreType Type
------------- ----
VaultStore    GeoRedundant
```

Perintah ini membuat objek pengaturan penyimpanan vault baru yang digunakan untuk membuat vault cadangan.

## PARAMETERS

### -DataStoreType
Jenis DataStore vault

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

### -Type
Storage Jenis vault

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### System.Management.Automation.PSObject

## NOTES

ALIAS

## RELATED LINKS

