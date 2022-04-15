---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: F63769D6-9A31-4A67-972A-1E0428853C86
online version: ''
schema: 2.0.0
ms.openlocfilehash: 00ce7cd468b8325cf51327ded69fcd13b4d49378
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142311701"
---
# Start-AzureSqlDatabaseRecovery

## SYNOPSIS
Memulai permintaan pemulihan untuk database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### BySourceDatabaseName
```
Start-AzureSqlDatabaseRecovery -SourceServerName <String> -SourceDatabaseName <String>
 [-TargetServerName <String>] [-TargetDatabaseName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### BySourceDatabaseObject
```
Start-AzureSqlDatabaseRecovery -SourceDatabase <RecoverableDatabase> [-TargetServerName <String>]
 [-TargetDatabaseName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureSqlDatabaseRecovery** memulai permintaan pemulihan untuk database langsung atau yang dihapus.
Cmdlet ini mendukung pemulihan dasar yang menggunakan cadangan terakhir yang tersedia untuk database.
Operasi pemulihan membuat database baru.
Jika Memulihkan database langsung di server yang sama, Anda harus menentukan nama yang berbeda untuk database baru.

Untuk melakukan pemulihan waktu untuk database, gunakan cmdlet **Start-AzureSqlDatabaseRestore** sebagai gantinya.

## EXAMPLES

### Contoh 1: Memulihkan database yang ditentukan sebagai objek
```
PS C:\> $Database = Get-AzureSqlRecoverableDatabase -ServerName "Server01" -DatabaseName "Database17" 
PS C:\> $Operation = Start-AzureSqlDatabaseRecovery -SourceDatabase $Database -TargetDatabaseName "DatabaseRestored"
```

Perintah pertama mendapatkan objek database menggunakan cmdlet **Get-AzureSqlRecoverableDatabase** .
Perintah menyimpan objek tersebut dalam variabel $Database.

Perintah kedua memulihkan database yang disimpan di $Database.

### Contoh 2: Memulihkan database yang ditentukan menurut nama
```
PS C:\> $Operation = Start-AzureSqlDatabaseRecovery -SourceServerName "Server01" -SourceDatabaseName "Database17" -TargetDatabaseName "DatabaseRestored"
```

Perintah ini memulihkan database menggunakan nama database.

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

### -SourceDatabase
Menentukan objek database yang mewakili database yang dipulihkan cmdlet ini.

```yaml
Type: RecoverableDatabase
Parameter Sets: BySourceDatabaseObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SourceDatabaseName
Menentukan nama database yang dipulihkan cmdlet ini.

```yaml
Type: String
Parameter Sets: BySourceDatabaseName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceServerName
Menentukan nama server tempat database sumber dijalankan, atau tempat database sumber dijalankan sebelum database tersebut dihapus.

```yaml
Type: String
Parameter Sets: BySourceDatabaseName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDatabaseName
Menentukan nama database yang dipulihkan.
Jika database sumber masih aktif, untuk memulihkannya ke server yang sama, Anda harus menentukan nama yang berbeda dari nama database sumber.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetServerName
Menentukan nama server yang akan dipulihkan databasenya.
Anda bisa memulihkan database ke server yang sama atau ke server lain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAzure.Management.Sql.Models.RecoverableDatabase

## OUTPUTS

### Microsoft.WindowsAzure.Management.Sql.Models.RecoverDatabaseOperation

## CATATAN
* Anda harus menggunakan autentikasi berbasis sertifikat untuk menjalankan cmdlet ini. Jalankan perintah berikut ini di komputer tempat Anda menjalankan cmdlet ini: 

`PS C:\\\> $subId = \<Subscription ID\>`
`PS C:\\\> $thumbprint = \<Certificate Thumbprint\>`
`PS C:\\\> $myCert = Get-Item Cert:\CurrentUser\My\$thumbprint`
`PS C:\\\> Set-AzureSubscription -SubscriptionName "mySubscription" -SubscriptionId $subId -Certificate $myCert`
`PS C:\\\> Select-AzureSubscription -SubscriptionName "mySubscription"`

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Buat Permintaan Pemulihan Database](https://msdn.microsoft.com/en-us/library/dn800986.aspx)

[Geo-Replikasi di Azure SQL Database](https://azure.microsoft.com/en-us/documentation/articles/sql-database-business-continuity-scenarios/)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlRecoverableDatabase](./Get-AzureSqlRecoverableDatabase.md)

[Start-AzureSqlDatabaseRestore](./Start-AzureSqlDatabaseRestore.md)


