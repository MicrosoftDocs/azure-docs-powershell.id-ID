---
external help file: Azs.Compute.Admin-help.xml
Module Name: Azs.Compute.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 06f2d231754fc422115cf800ef66189378e0cd4d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142310857"
---
# Get-AzsDiskMigrationJob

## SYNOPSIS
Mengembalikan daftar pekerjaan migrasi disk terkelola.

## SYNTAX

### Daftar (Default)
```
Get-AzsDiskMigrationJob [-Status <String>] [-Location <String>] [<CommonParameters>]
```

### ResourceId
```
Get-AzsDiskMigrationJob -ResourceId <String> [<CommonParameters>]
```

### Mendapatkan
```
Get-AzsDiskMigrationJob [-Location <String>] -Name <String> [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan daftar pekerjaan migrasi disk.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
$migration = Get-AzsDiskMigrationJob -location local -Name "mymigrationName"
```

Dapatkan pekerjaan migrasi disk terkelola tertentu.

### -------------------------- CONTOH 2 --------------------------
```
$migration = Get-AzsDiskMigrationJob -location local
```

Mengembalikan daftar pekerjaan migrasi disk terkelola di lokasi lokal.

## PARAMETERS

### -Lokasi
Lokasi sumber daya.

```yaml
Type: String
Parameter Sets: List, Get
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama panduan pekerjaan migrasi.

```yaml
Type: String
Parameter Sets: Get
Aliases: MigrationId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya.

```yaml
Type: String
Parameter Sets: ResourceId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
Parameter status pekerjaan migrasi disk.

```yaml
Type: String
Parameter Sets: List
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Compute.Admin.Models.DiskMigrationJob

## CATATAN

## RELATED LINKS

