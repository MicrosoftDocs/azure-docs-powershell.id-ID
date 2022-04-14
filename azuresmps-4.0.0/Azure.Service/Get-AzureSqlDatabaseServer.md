---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 0ACEDE22-1C2B-4846-A949-710AF6C148D0
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6b7072c5cd9c9e91a5c71d585be685a4dfa7700c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141921657"
---
# Get-AzureSqlDatabaseServer

## SYNOPSIS
Mendapatkan informasi tentang server Azure SQL Database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSqlDatabaseServer [-ServerName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSqlDatabaseServer** mendapatkan informasi tentang contoh server Azure SQL Database dalam langganan saat ini.
Jika Anda menentukan server menurut nama, cmdlet ini mengembalikan objek yang berisi informasi tentang server tersebut.
Jika tidak, cmdlet mengembalikan informasi tentang semua server.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang semua server
```
PS C:\> Get-AzureSqlDatabaseServer
```

Perintah ini mengembalikan informasi tentang semua contoh Azure SQL Database Server dalam langganan saat ini.

### Contoh 2: Mendapatkan informasi tentang server tertentu
```
PS C:\> Get-AzureSqlDatabaseServer -ServerName "lpqd0zbr8y"
```

Perintah ini mengembalikan informasi tentang server bernama lpqd0zbr8y.

## PARAMETERS

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
Menentukan nama server yang dihapus cmdlet ini.
Tentukan nama server, bukan nama DNS yang sepenuhnya memenuhi syarat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerContext

## OUTPUTS

### Ienumerable\<Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerContext\>

## CATATAN

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Server Daftar](https://msdn.microsoft.com/en-us/library/azure/dn505702.aspx)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Azure BaruSqlDatabaseServer](./New-AzureSqlDatabaseServer.md)

[Hapus-AzureSqlDatabaseServer](./Remove-AzureSqlDatabaseServer.md)

[Set-AzureSqlDatabaseServer](./Set-AzureSqlDatabaseServer.md)


