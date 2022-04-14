---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 56026A74-A6DC-47A5-9643-5828C3D0E83B
online version: ''
schema: 2.0.0
ms.openlocfilehash: e18800e1f7deddda47ef0f8d80bcd4ffc2012086
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141772378"
---
# Get-AzureSqlDatabaseOperation

## SYNOPSIS
Mendapatkan status operasi database di server Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByConnectionContext (Default)
```
Get-AzureSqlDatabaseOperation -ConnectionContext <IServerDataServiceContext> [-Database <Database>]
 [-DatabaseName <String>] [-OperationGuid <Guid>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByServerName
```
Get-AzureSqlDatabaseOperation -ServerName <String> [-Database <Database>] [-DatabaseName <String>]
 [-OperationGuid <Guid>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSqlDatabaseOperation** mendapatkan status operasi database di server Azure yang ditentukan.
Jika Anda hanya menentukan parameter *ServerName* atau *ConnectionContext* , cmdlet akan mendapatkan semua operasi database untuk server.
Jika Anda juga menentukan database dengan menggunakan parameter *Database* atau *DatabaseName* , cmdlet ini mendapatkan semua operasi untuk database yang ditentukan.
Jika Anda menentukan operasi GUID, dan *ServerName* atau *ConnectionContext*, cmdlet mendapatkan operasi database tunggal.

## EXAMPLES

### Contoh 1: Mendapatkan status semua operasi database untuk database
```
PS C:\> $Operations = Get-AzureSqlDatabaseOperation -ConnectionContext $Context -DatabaseName "Database17"
```

Perintah ini mendapatkan status semua operasi database pada database bernama Database17 di server yang ditentukan konteks koneksi $Context.

### Contoh 2: Mendapatkan status semua operasi database untuk server
```
PS C:\> $Operations = Get-AzureSqlDatabaseOperation -ConnectionContext $Context
```

Perintah ini mendapatkan status semua operasi database di server yang ditentukan konteks koneksi $Context.

## PARAMETERS

### -ConnectionContext
Menentukan konteks koneksi server.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByConnectionContext
Aliases: Context

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Database
Menentukan objek yang mewakili Azure SQL Database.
Jika menentukan parameter ini, Anda harus menentukan parameter *ServerName* atau parameter *ConnectionContext* .

```yaml
Type: Database
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseName
Menentukan nama database.
Jika menentukan parameter ini, Anda harus menentukan parameter *ServerName* atau parameter *ConnectionContext* .

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

### -OperationGuid
Menentukan ID operasi yang mewakili operasi database tertentu yang mana cmdlet ini mendapatkan status.
Anda dapat memperoleh ID operasi dengan meminta semua operasi database untuk Azure SQL Database atau server.
Jika menentukan parameter ini, Anda harus menentukan parameter *ServerName* atau parameter *ConnectionContext* .

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Menentukan nama server.

```yaml
Type: String
Parameter Sets: ByServerName
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerContext

### System.Guid

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database.DatabaseOperationResponseList[]
Cmdlet ini mengembalikan array objek **DatabaseOperationResponseList** jika Anda mendapatkan beberapa operasi.

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database.DatabaseOperationResponse

## CATATAN

## RELATED LINKS

[Azure SQL Database](https://msdn.microsoft.com/library/ee336279.aspx)

[Status Operasi Database](https://msdn.microsoft.com/en-us/library/azure/dn720371.aspx)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabase](./Get-AzureSqlDatabase.md)

[Baru-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)


