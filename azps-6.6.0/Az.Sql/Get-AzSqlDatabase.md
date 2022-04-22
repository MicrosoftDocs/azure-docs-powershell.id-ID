---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 0C8AC52C-4E70-493C-A299-79CE32EC5EF1
online version: https://docs.microsoft.com/powershell/module/az.sql/get-azsqldatabase
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlDatabase.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlDatabase.md
ms.openlocfilehash: 1d59754522e465a905bf13f68f5723d7a6ecba74
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143084123"
---
# Get-AzSqlDatabase

## SYNOPSIS
Mendapatkan satu atau beberapa database.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.sql/get-azsqldatabase) untuk informasi terbaru.

## SYNTAX

```
Get-AzSqlDatabase [[-DatabaseName] <String>] [-ServerName] <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSqlDatabase** mendapatkan satu atau beberapa database Azure SQL dari Server Azure SQL Database.
Cmdlet ini juga didukung oleh layanan SQL Server Stretch Database di Azure.

## EXAMPLES

### Contoh 1: Mendapatkan semua database di server
```
PS C:\>Get-AzSqlDatabase -ResourceGroupName "resourcegroup01" -ServerName "server01"
ResourceGroupName                        : resourcegroup01
ServerName                                 : server01
DatabaseName                               : master
Location                                     : Central US
DatabaseId                                 : a2a7f2db-7526-4d86-a7b2-36276ee10dc6
Edition                                      : None
CollationName                              : SQL_Latin1_General_CP1_CI_AS
CatalogCollation                         : 
MaxSizeBytes                               : 5368709120
Status                                       : Online
CreationDate                               : 7/3/2015 7:32:44 AM
CurrentServiceObjectiveId            : c99ac918-dbea-463f-a475-16ec020fdc12
CurrentServiceObjectiveName        : System1
RequestedServiceObjectiveId        : c99ac918-dbea-463f-a475-16ec020fdc12
RequestedServiceObjectiveName      : 
ElasticPoolName                          : 
EarliestRestoreDate                    : 
Tags                                           :
CurrentBackupStorageRedundancy   : Geo
RequestedBackupStorageRedundancy : Geo

ResourceGroupName                        : resourcegroup01
ServerName                                 : server01
DatabaseName                     : database01
Location                                     : Central US
DatabaseId                                 : a1e6bd1a-735a-4d48-8b98-afead5ef1218
Edition                                      : Standard
CollationName                              : SQL_Latin1_General_CP1_CI_AS
CatalogCollation                         : 
MaxSizeBytes                               : 268435456000
Status                                       : Online
CreationDate                               : 7/3/2015 7:33:37 AM
CurrentServiceObjectiveId            : f1173c43-91bd-4aaa-973c-54e79e15235b
CurrentServiceObjectiveName        : S0
RequestedServiceObjectiveId        : f1173c43-91bd-4aaa-973c-54e79e15235b
RequestedServiceObjectiveName      : 
ElasticPoolName                          : 
EarliestRestoreDate                    : 
Tags                                           :
CurrentBackupStorageRedundancy   : Geo
RequestedBackupStorageRedundancy : Geo
```

Perintah ini mendapatkan semua database di server bernama server01.

### Contoh 2: Mendapatkan database berdasarkan nama di server
```
PS C:\>Get-AzSqlDatabase -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database02"
ResourceGroupName                        : resourcegroup01
ServerName                                 : server01
DatabaseName                               : database02
Location                                     : Central US
DatabaseId                                 : a1e6bd1a-735a-4d48-8b98-afead5ef1218
Edition                                      : Standard
CollationName                              : SQL_Latin1_General_CP1_CI_AS
CatalogCollation                         : 
MaxSizeBytes                               : 268435456000
Status                                       : Online
CreationDate                               : 7/3/2015 7:33:37 AM
CurrentServiceObjectiveId            : f1173c43-91bd-4aaa-973c-54e79e15235b
CurrentServiceObjectiveName        : S0
RequestedServiceObjectiveId        : f1173c43-91bd-4aaa-973c-54e79e15235b
RequestedServiceObjectiveName      : 
ElasticPoolName                  : 
EarliestRestoreDate                    : 
Tags                                           :
CurrentBackupStorageRedundancy   : Geo
RequestedBackupStorageRedundancy : Geo
```

Perintah ini mendapatkan database bernama Database02 dari server bernama Server01.

### Contoh 3: Mendapatkan semua database di server menggunakan pemfilteran
```
PS C:\> Get-AzSqlDatabase -ResourceGroupName "resourcegroup01" -ServerName "server01" -DatabaseName "database*"
ResourceGroupName                        : resourcegroup01
ServerName                                 : server01
DatabaseName                               : database01
Location                                     : Central US
DatabaseId                                 : a2a7f2db-7526-4d86-a7b2-36276ee10dc6
Edition                                      : None
CollationName                            : SQL_Latin1_General_CP1_CI_AS
CatalogCollation                         : 
MaxSizeBytes                               : 5368709120
Status                                       : Online
CreationDate                               : 7/3/2015 7:32:44 AM
CurrentServiceObjectiveId            : c99ac918-dbea-463f-a475-16ec020fdc12
CurrentServiceObjectiveName        : System1
RequestedServiceObjectiveId        : c99ac918-dbea-463f-a475-16ec020fdc12
RequestedServiceObjectiveName      : 
ElasticPoolName                          : 
EarliestRestoreDate                    : 
Tags                                           : 
CurrentBackupStorageRedundancy   : Geo
RequestedBackupStorageRedundancy : Geo

ResourceGroupName                        : resourcegroup01
ServerName                                 : server01
DatabaseName                               : database02
Location                         : Central US
DatabaseId                               : a1e6bd1a-735a-4d48-8b98-afead5ef1218
Edition                                    : Standard
CollationName                              : SQL_Latin1_General_CP1_CI_AS
CatalogCollation                         : 
MaxSizeBytes                               : 268435456000
Status                                       : Online
CreationDate                               : 7/3/2015 7:33:37 AM
CurrentServiceObjectiveId            : f1173c43-91bd-4aaa-973c-54e79e15235b
CurrentServiceObjectiveName        : S0
RequestedServiceObjectiveId        : f1173c43-91bd-4aaa-973c-54e79e15235b
RequestedServiceObjectiveName      : 
ElasticPoolName                          : 
EarliestRestoreDate                    : 
Tags                             :
CurrentBackupStorageRedundancy   : Geo
RequestedBackupStorageRedundancy : Geo
```

Perintah ini mendapatkan semua database di server bernama server01 yang dimulai dengan "database".

## PARAMETERS

### -DatabaseName
Menentukan nama database yang akan diambil.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat server database ditetapkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Menentukan nama server tempat database ditetapkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel

## NOTES

## RELATED LINKS

[New-AzSqlDatabase](./New-AzSqlDatabase.md)

[Remove-AzSqlDatabase](./Remove-AzSqlDatabase.md)

[Resume-AzSqlDatabase](./Resume-AzSqlDatabase.md)

[Set-AzSqlDatabase](./Set-AzSqlDatabase.md)

[Suspend-AzSqlDatabase](./Suspend-AzSqlDatabase.md)


