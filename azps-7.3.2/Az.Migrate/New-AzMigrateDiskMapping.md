---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/new-azmigratediskmapping
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/New-AzMigrateDiskMapping.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/New-AzMigrateDiskMapping.md
ms.openlocfilehash: 48ab1cd6384d982207b01cc14389ddf22f573534
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142291651"
---
# New-AzMigrateDiskMapping

## SYNOPSIS
Membuat pemetaan disk baru

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.migrate/new-azmigratediskmapping) untuk informasi terbaru.

## SYNTAX

```
New-AzMigrateDiskMapping -DiskID <String> -DiskType <String> -IsOSDisk <String>
 [-DiskEncryptionSetID <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzMigrateDiskMapping membuat pemetaan disk sumber yang terhubung ke server yang akan dimigrasikan

## EXAMPLES

### Contoh 1: Membuat disk
```powershell
PS C:\> New-AzMigrateDiskMapping -DiskID a -DiskType Standard -IsOSDisk 'true'

DiskEncryptionSetId DiskId   DiskType  IsOSDisk LogStorageAccountId LogStorageAccountSasSecretName  
------------------- ------   --------  -------- ------------------- ------------------------------   
                      a      Standard  true  
```

Dapatkan objek disk untuk menyediakan input untuk New-AzMigrateServerReplication

## PARAMETERS

### -DiskEncryptionSetID
Menentukan set ensipsi diska yang akan digunakan.

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

### -DISKID
Menentukan ID diska diska yang terpasang ke server yang ditemukan untuk dimigrasikan.

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

### -DiskType
Menentukan tipe disk yang akan digunakan untuk Azure VM.

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

### -IsOSDisk
Menentukan apakah diska berisi Sistem Operasi untuk server sumber yang akan dimigrasikan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVMwareCbtDiskInput

## CATATAN

ALIAS

## RELATED LINKS

