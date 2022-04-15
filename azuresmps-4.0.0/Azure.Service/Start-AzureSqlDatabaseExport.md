---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 3005E411-9466-4602-8E07-F4EF8804AB2A
online version: ''
schema: 2.0.0
ms.openlocfilehash: a66d85b8586693a416c8e522c046c1ce8f2ce894
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142311812"
---
# Start-AzureSqlDatabaseExport

## SYNOPSIS
Memulai operasi ekspor dari Azure SQL Database ke penyimpanan Blob.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByContainerObject
```
Start-AzureSqlDatabaseExport -SqlConnectionContext <ISqlServerConnectionInformation>
 -StorageContainer <AzureStorageContainer> -DatabaseName <String> -BlobName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByContainerName
```
Start-AzureSqlDatabaseExport -SqlConnectionContext <ISqlServerConnectionInformation>
 -StorageContext <IStorageContext> -StorageContainerName <String> -DatabaseName <String> -BlobName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureSqlDatabaseExport** memulai operasi ekspor dari Azure SQL Database ke penyimpanan Blob.
Operasi ini memerlukan konteks koneksi server database.
Gunakan cmdlet Get-AzureSqlDatabaseImportExportStatus untuk mendapatkan status operasi ekspor.

## EXAMPLES

### Contoh 1: Mengekspor database
```
PS C:\>$Credential = Get-Credential
PS C:\> $SqlContext = New-AzureSqlDatabaseServerContext -ServerName $ServerName -Credential $Credential
PS C:\> $StorageContext = New-AzureStorageContext -StorageAccountName $StorageName -StorageAccountKey $StorageKey
PS C:\> $Container = Get-AzureStorageContainer -Name $ContainerName -Context $StorageContext
PS C:\> $exportRequest = Start-AzureSqlDatabaseExport -SqlConnectionContext $SqlContext -StorageContainer $Container -DatabaseName $DatabaseName -BlobName $BlobName
```

Contoh ini memulai proses ekspor dari Azure SQL Database yang memiliki nama yang disimpan dalam variabel $DatabaseName ke penyimpanan Blob yang disimpan dalam variabel $BlobName.

## PARAMETERS

### -BlobName
Menentukan nama penyimpanan Azure Blob tempat cmdlet ini mengekspor database.

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

### -DatabaseName
Menentukan nama database tempat cmdlet ini mengekspor data.

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

### -SqlConnectionContext
Menentukan konteks koneksi server yang berisi database.

```yaml
Type: ISqlServerConnectionInformation
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageContainer
Menentukan wadah penyimpanan yang berisi Blob tempat cmdlet ini mengekspor database.

```yaml
Type: AzureStorageContainer
Parameter Sets: ByContainerObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageContainerName
Menentukan nama wadah penyimpanan yang berisi Blob tempat cmdlet ini mengekspor database.

```yaml
Type: String
Parameter Sets: ByContainerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageContext
Menentukan konteks wadah penyimpanan Blob.

```yaml
Type: IStorageContext
Parameter Sets: ByContainerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.ImportExportRequest

## CATATAN

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Mengekspor Database](https://msdn.microsoft.com/en-us/library/azure/dn781282.aspx)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabaseImportExportStatus](./Get-AzureSqlDatabaseImportExportStatus.md)

[Start-AzureSqlDatabaseImport](./Start-AzureSqlDatabaseImport.md)


