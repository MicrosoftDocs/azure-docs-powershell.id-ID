---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 56026A74-A6DC-47A5-9643-5828C3D0E83B
online version: ''
schema: 2.0.0
ms.openlocfilehash: 70b6628b5489401a548d8f06143c51c68e079716292475b63b174780b721870f
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419397"
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
Jika Anda hanya menentukan *parameter ServerName* *atau ConnectionContext,* cmdlet akan mendapatkan semua operasi database untuk server.
Jika Anda juga menentukan database dengan menggunakan *parameter Database* atau *DatabaseName,* cmdlet ini akan mendapatkan semua operasi untuk database yang ditentukan.
Jika Anda menentukan GUID operasi, dan *ServerName* atau *ConnectionContext,* cmdlet akan mendapatkan satu operasi database.

## EXAMPLES

### Contoh 1: Mendapatkan status dari semua operasi database untuk database
```
PS C:\> $Operations = Get-AzureSqlDatabaseOperation -ConnectionContext $Context -DatabaseName "Database17"
```

Perintah ini mendapatkan status semua operasi database pada database bernama Database17 di server yang ditentukan oleh konteks koneksi $Context tentukan.

### Contoh 2: Mendapatkan status semua operasi database untuk server
```
PS C:\> $Operations = Get-AzureSqlDatabaseOperation -ConnectionContext $Context
```

Perintah ini mendapatkan status dari semua operasi database pada server yang ditentukan oleh konteks koneksi $Context tentukan.

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
Menentukan objek yang mewakili objek Azure SQL Database.
Jika Anda menentukan parameter ini, Anda harus menentukan parameter *ServerName* atau parameter *ConnectionContext.*

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
Jika Anda menentukan parameter ini, Anda harus menentukan parameter *ServerName* atau parameter *ConnectionContext.*

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
Menentukan ID operasi yang mewakili operasi database tertentu di mana cmdlet ini mendapatkan status.
You can obtain operation IDs by requesting all the database operations for a Azure SQL Database or server.
Jika Anda menentukan parameter ini, Anda harus menentukan parameter *ServerName* atau parameter *ConnectionContext.*

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

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

[Operasi untuk Database SQL Azure](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabase](./Get-AzureSqlDatabase.md)

[New-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)


