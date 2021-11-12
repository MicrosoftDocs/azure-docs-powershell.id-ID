---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 256AA6F4-D856-4713-A0AC-0DA1A145AA5C
online version: https://docs.microsoft.com/en-us/powershell/module/az.sql/get-azsqldatabasegeobackup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Sql/Sql/help/Get-AzSqlDatabaseGeoBackup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Sql/Sql/help/Get-AzSqlDatabaseGeoBackup.md
ms.openlocfilehash: 0ca3a6c467ab5fd7dd681164d88686a6360394ee
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132410151"
---
# Get-AzSqlDatabaseGeoBackup

## SYNOPSIS
Mendapatkan cadangan database yang berlebihan geo.

## SINTAKS

```
Get-AzSqlDatabaseGeoBackup [-ServerName] <String> [[-DatabaseName] <String>] [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzSqlDatabaseGeoBackup** mendapatkan cadangan geo-redundan tertentu dari database SQL atau semua cadangan geo-redundan yang tersedia pada server tertentu.
Cadangan geo-berlebihan adalah sumber daya yang dapat dikembalikan menggunakan file data dari lokasi geografis yang terpisah.
Anda bisa Geo-Restore untuk memulihkan cadangan geo berulang jika terjadi pemadaman listrik regional untuk memulihkan database ke kawasan baru.
Cmdlet ini juga didukung oleh layanan SQL Server Stretch Database di Azure.

## CONTOH

### Contoh 1: Mendapatkan semua cadangan geo-redundan di server
```
PS C:\>Get-AzSqlDatabaseGeoBackup -ResourceGroupName "ContosoResourceGroup" -ServerName "ContosoServer"
```

Perintah ini mendapatkan semua cadangan geo-redundan yang tersedia pada server tertentu.

### Contoh 2: Mendapatkan cadangan geo-redundan tertentu
```
PS C:\>Get-AzSqlDatabaseGeoBackup -ResourceGroupName "ContosoResourceGroup" -ServerName "ContosoServer" -DatabaseName "ContosoDatabase"
```

Perintah ini mendapatkan cadangan geo-redundan database bernama ContosoDatabase.

### Contoh 3: Mendapatkan semua cadangan geo-redundan di server menggunakan pemfilteran
```
PS C:\>Get-AzSqlDatabaseGeoBackup -ResourceGroupName "ContosoResourceGroup" -ServerName "ContosoServer" -DatabaseName "Contoso*"
```

Perintah ini mendapatkan semua cadangan geo-redundan yang tersedia pada server tertentu yang dimulai dengan "Contoso".

## PARAMETERS

### -DatabaseName
Menentukan nama database yang akan dapatkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Menentukan nama grup sumber daya tempat server database SQL ditetapkan.

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
Menentukan nama server yang menjadi host cadangan untuk dipulihkan.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Sql.Backup.Model.AzureSqlDatabaseGeoBackupModel

## CATATAN

## LINK TERKAIT

[Gambaran umum: Keberlangsungan bisnis awan dan pemulihan bencana database dengan SQL Database](http://go.microsoft.com/fwlink/?LinkId=746881)

[Memulihkan Azure SQL Database dari pemadaman](http://go.microsoft.com/fwlink/?LinkId=746882)

[Restore-AzSqlDatabase](./Restore-AzSqlDatabase.md)

[SQL Database Dokumen](https://docs.microsoft.com/azure/sql-database/)
