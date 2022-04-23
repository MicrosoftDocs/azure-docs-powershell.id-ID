---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 4661C479-6E3B-425D-B9D2-B36D7A83130C
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1435fe734074cee3c44adee735fc347651c05d97
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143211419"
---
# Get-AzureSqlDatabaseImportExportStatus

## SYNOPSIS
Mendapatkan status permintaan impor atau ekspor.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByConnectionInfo
```
Get-AzureSqlDatabaseImportExportStatus -Username <String> -Password <String> -ServerName <String>
 -RequestId <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByRequestObject
```
Get-AzureSqlDatabaseImportExportStatus -Request <ImportExportRequest> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSqlDatabaseImportExportStatus** mendapatkan status permintaan impor atau ekspor.
Cmdlet Start-AzureSqlDatabaseImport atau Start-AzureSqlDatabaseExport memulai permintaan.
Anda bisa menentukan objek permintaan dengan menggunakan parameter *Permintaan* , atau Anda bisa mengidentifikasi permintaan dengan menggunakan parameter *RequestId* dan parameter *NamaPengguna*, *Kata Sandi*, dan *ServerName* .

## EXAMPLES

### Contoh 1: Mendapatkan status permintaan ekspor
```
PS C:\> $ExportRequest = Start-AzureSqlDatabaseExport -SqlConnectionContext $SqlContext -StorageContainer $Container -DatabaseName $DatabaseName -BlobName $BlobName
PS C:\> Get-AzureSqlDatabaseImportExportStatus -Request $ExportRequest
```

Perintah pertama membuat permintaan ekspor, lalu menyimpannya dalam variabel $ExportRequest.

Perintah kedua mendapatkan status permintaan ekspor yang disimpan di $ExportRequest.

## PARAMETERS

### -Password
Menentukan kata sandi yang diperlukan untuk tersambung ke server Azure SQL Database.
Anda harus menentukan parameter ini jika Anda menentukan parameter *RequestId* .

```yaml
Type: String
Parameter Sets: ByConnectionInfo
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

### -Request
Menentukan objek **ImportExportRequest** .
Untuk mendapatkan objek permintaan impor atau ekspor, gunakan cmdlet Start-AzureSqlDatabaseImport atau Start-AzureSqlDatabaseExport.

```yaml
Type: ImportExportRequest
Parameter Sets: ByRequestObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestId
Menentukan GUID operasi impor atau ekspor tempat cmdlet ini mendapatkan status.
Jika Anda menentukan parameter ini, Anda harus menentukan parameter *UserName*, *Password*, dan *ServerName* .

```yaml
Type: String
Parameter Sets: ByConnectionInfo
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Menentukan nama server Azure SQL Database.
Anda harus menentukan parameter ini jika Anda menentukan parameter *RequestId* .

```yaml
Type: String
Parameter Sets: ByConnectionInfo
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama pengguna
Menentukan nama pengguna yang diperlukan untuk tersambung ke server Azure SQL Database.
Anda harus menentukan parameter ini jika Anda menentukan parameter *RequestId* .

```yaml
Type: String
Parameter Sets: ByConnectionInfo
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

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.ImportExport.StatusInfo

## NOTES

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Dapatkan Status Ekspor Database Impor](https://msdn.microsoft.com/en-us/library/azure/dn781289.aspx)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Start-AzureSqlDatabaseExport](./Start-AzureSqlDatabaseExport.md)

[Start-AzureSqlDatabaseImport](./Start-AzureSqlDatabaseImport.md)


