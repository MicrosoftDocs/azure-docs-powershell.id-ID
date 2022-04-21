---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 9953AF91-2424-4BD1-9133-E0E07AC1087E
online version: ''
schema: 2.0.0
ms.openlocfilehash: c6c6ba205c44fe5f70b0bb4d9324ddb7796bd4ed
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142656388"
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

### Contoh 1: Dapatkan informasi penggunaan untuk SQL Database
```
PS C:\> Get-AzureSqlDatabaseUsages -ServerName "Server01" -DatabaseName "Database01"
```

Perintah ini mendapatkan informasi batas ukuran dan ukuran untuk SQL Database bernama Database01 di Server01.

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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

