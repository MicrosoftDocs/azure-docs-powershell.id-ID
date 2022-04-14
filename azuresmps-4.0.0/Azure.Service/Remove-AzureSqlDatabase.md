---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: B3813F54-E5B7-4605-BB1C-67417FDDB076
online version: ''
schema: 2.0.0
ms.openlocfilehash: e54b9af06b56f3e9010136b8aff704cf5e8d5d4c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141772053"
---
# Remove-AzureSqlDatabase

## SYNOPSIS
Menghapus Azure SQL Database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByNameWithConnectionContext
```
Remove-AzureSqlDatabase -ConnectionContext <IServerDataServiceContext> -DatabaseName <String> [-Force]
 [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectWithConnectionContext
```
Remove-AzureSqlDatabase -ConnectionContext <IServerDataServiceContext> -Database <Database> [-Force]
 [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNameWithServerName
```
Remove-AzureSqlDatabase -ServerName <String> -DatabaseName <String> [-Force] [-Profile <AzureSMProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectWithServerName
```
Remove-AzureSqlDatabase -ServerName <String> -Database <Database> [-Force] [-Profile <AzureSMProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureSqlDatabase** menghapus Azure SQL Database menurut konteks koneksi server atau nama server.
Anda dapat membuat konteks koneksi server Azure SQL Database menggunakan cmdlet **New-AzureSqlDatabaseServerContext**, lalu menggunakannya dengan cmdlet ini.

Saat Anda menghapus database dengan menentukan nama server Azure SQL Database, cmdlet **Remove-AzureSqlDatabase** menggunakan nama dan informasi langganan Azure saat ini untuk melakukan operasi.

## EXAMPLES

### Contoh 1: Menghapus database
```
PS C:\> Remove-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database01"
```

Perintah ini menghapus database bernama Database01 dari konteks koneksi server Azure SQL Database $Context.

### Contoh 2: Menghapus database menggunakan nama server
```
PS C:\> Remove-AzureSqlDatabase -ServerName "lpqd0zbr8y" -DatabaseName "Database01"
```

Perintah ini menghapus database bernama Database01 dari server Azure SQL Database bernama lpqd0zbr8y.

### Contoh 3: Menghapus database menggunakan saluran
```
PS C:\> $Database01 | Remove-AzureSqlDatabase -ConnectionContext $Context
PS C:\> $Database01 | Remove-AzureSqlDatabase -ServerName "lpqd0zbr8y"
```

Contoh ini menunjukkan metode alternatif untuk melewati objek database melalui pipeline.

## PARAMETERS

### -ConnectionContext
Menentukan konteks koneksi server tempat cmdlet ini menghapus database.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByNameWithConnectionContext, ByObjectWithConnectionContext
Aliases: Context

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Database
Menentukan objek yang mewakili database yang dihapus cmdlet ini.

```yaml
Type: Database
Parameter Sets: ByObjectWithConnectionContext, ByObjectWithServerName
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseName
Menentukan nama database yang dihapus cmdlet ini.

```yaml
Type: String
Parameter Sets: ByNameWithConnectionContext, ByNameWithServerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paksa
Memperbolehkan tindakan untuk diselesaikan tanpa meminta konfirmasi kepada pengguna.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
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
Menentukan nama server tempat cmdlet ini menghapus database.

```yaml
Type: String
Parameter Sets: ByNameWithServerName, ByObjectWithServerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.Database

## OUTPUTS

## CATATAN
* Karena tingkat keparahan operasi, secara default, cmdlet ini meminta Anda untuk konfirmasi. Untuk melewati konfirmasi, tentukan parameter *Paksa* .

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Hapus Database](https://msdn.microsoft.com/en-us/library/azure/dn505705.aspx)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabase](./Get-AzureSqlDatabase.md)

[AzureSqlDatabase baru](./New-AzureSqlDatabase.md)

[Baru-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)

[Set-AzureSqlDatabase](./Set-AzureSqlDatabase.md)


