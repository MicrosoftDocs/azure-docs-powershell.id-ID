---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 9953AF91-2424-4BD1-9133-E0E07AC1087E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 14581b909238e6d8b8c040b07b2dc93120284437df7a1ea22f479610fcd444b0
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419395"
---
# Get-AzureSqlDatabaseUsages

## SYNOPSIS
Mendapatkan batas ukuran dan ukuran SQL Database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSqlDatabaseUsages -ServerName <String> -DatabaseName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSqlDatabaseUsages** mendapatkan batas ukuran dan ukuran saat ini dari Azure SQL Database.

## EXAMPLES

### Contoh 1: Mendapatkan informasi penggunaan untuk SQL Database
```
PS C:\> Get-AzureSqlDatabaseUsages -ServerName "Server01" -DatabaseName "Database01"
```

Perintah ini mendapatkan informasi batas ukuran dan ukuran aplikasi SQL Database Database01 di Server01.

## PARAMETERS

### -DatabaseName
Menentukan nama Azure SQL Database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### -ServerName
Menentukan nama server yang menjadi host Azure SQL Database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

