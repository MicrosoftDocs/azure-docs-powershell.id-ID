---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/new-azmigratediskmapping
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/New-AzMigrateDiskMapping.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/New-AzMigrateDiskMapping.md
ms.openlocfilehash: 48ab1cd6384d982207b01cc14389ddf22f573534
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140121363"
---
# New-AzMigrateDiskMapping

## SYNOPSIS
Membuat pemetaan disk baru

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.migrate/new-azmigratediskmapping) untuk informasi terkini.

## SYNTAX

```
New-AzMigrateDiskMapping -DiskID <String> -DiskType <String> -IsOSDisk <String>
 [-DiskEncryptionSetID <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzMigrateDiskMapping membuat pemetaan disk sumber yang terhubung ke server untuk dimigrasi

## EXAMPLES

### Contoh 1: Buat disk
```powershell
PS C:\> New-AzMigrateDiskMapping -DiskID a -DiskType Standard -IsOSDisk 'true'

DiskEncryptionSetId DiskId   DiskType  IsOSDisk LogStorageAccountId LogStorageAccountSasSecretName  
------------------- ------   --------  -------- ------------------- ------------------------------   
                      a      Standard  true  
```

Mendapatkan objek disk untuk menyediakan input bagi New-AzMigrateServerReplication

## PARAMETERS

### -DiskEncryptionSetID
Menentukan kumpulanencyption disk yang akan digunakan.

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

### -DiskID
Menentukan ID disk dari disk yang terhubung ke server yang ditemukan untuk dimigrasikan.

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
Menentukan apakah disk berisi Sistem Operasi untuk server sumber yang akan dimigrasikan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVMwareCbtDiskInput

## CATATAN

ALIAS

## RELATED LINKS

