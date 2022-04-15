---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionbackupvaultstoragesettingobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupVaultStorageSettingObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupVaultStorageSettingObject.md
ms.openlocfilehash: cfe76391cc27ce8d02fd0ff7291e3a49e4ff4a82
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142476233"
---
# New-AzDataProtectionBackupVaultStorageSettingObject

## SYNOPSIS
Dapatkan objek pengaturan penyimpanan Vault Cadangan

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/new-azdataprotectionbackupvaultstoragesettingobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDataProtectionBackupVaultStorageSettingObject -DataStoreType <DataStoreType> -Type <StorageSettingType>
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan objek pengaturan penyimpanan Vault Cadangan

## EXAMPLES

### Contoh 1: Membuat objek pengaturan penyimpanan kubah baru
```powershell
PS C:\> New-AzDataProtectionBackupVaultStorageSettingObject -Type GeoRedundant -DataStoreType VaultStore

DatastoreType Type
------------- ----
VaultStore    GeoRedundant
```

Perintah ini membuat objek pengaturan penyimpanan kubah baru yang digunakan untuk membuat kubah cadangan.

## PARAMETERS

### -DataStoreType
Tipe DataStore dari kubah

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
Storage Tipe kubah

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Management.Automation.PSObject

## CATATAN

ALIAS

## RELATED LINKS

