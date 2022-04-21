---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataMigration.dll-Help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/New-AzDataMigrationDatabaseInfo
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationDatabaseInfo.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationDatabaseInfo.md
ms.openlocfilehash: 3de34c50a97e5ca899622e204c4884470b41250b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142765648"
---
# New-AzDataMigrationDatabaseInfo

## SYNOPSIS
Membuat objek DatabaseInfo untuk Azure Database Migration Service, yang menentukan sumber database untuk migrasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datamigration/new-azdatamigrationdatabaseinfo) untuk informasi terbaru.

## SYNTAX

```
New-AzDataMigrationDatabaseInfo -SourceDatabaseName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzDataMigrationDatabaseInfo membuat objek DatabaseInfo yang menentukan instans database sumber yang akan dimigrasikan. Nama database diambil sebagai parameter input.

## EXAMPLES

### Contoh 1
```
PS C:\> New-AzDataMigrationDatabaseInfo -SourceDatabaseName 'AdventureWorks2016'
```

Contoh sebelumnya membuat objek DatabaseInfo baru untuk database sumber **AdventureWorks2016**.
Skrip ini mengasumsikan bahwa Anda sudah masuk ke akun Azure Anda. Anda dapat mengonfirmasi status masuk menggunakan cmdlet Get-AzSubscription.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -SourceDatabaseName
Nama Database Sumber.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SourceDBName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Management.DataMigration.Models.DatabaseInfo

## NOTES

## RELATED LINKS
