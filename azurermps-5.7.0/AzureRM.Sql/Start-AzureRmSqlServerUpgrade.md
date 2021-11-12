---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
Module Name: AzureRM.Sql
ms.assetid: 69A26BF3-7FE7-41ED-8C21-C8DC72D09615
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.sql/start-azurermsqlserverupgrade
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Start-AzureRmSqlServerUpgrade.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Start-AzureRmSqlServerUpgrade.md
ms.openlocfilehash: d33635cd3876a3426c3db96489d623d0a61f1d03
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420739"
---
# Start-AzureRmSqlServerUpgrade

## SYNOPSIS
Memulai pemutakhiran server SQL Database.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Start-AzureRmSqlServerUpgrade -ServerVersion <String> [-ScheduleUpgradeAfterUtcDateTime <DateTime>]
 [-DatabaseCollection <RecommendedDatabaseProperties[]>]
 [-ElasticPoolCollection <UpgradeRecommendedElasticPoolProperties[]>] -ServerName <String>
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureRmSqlServerUpgrade** memulai pemutakhiran server Azure SQL Database versi 11 ke versi 12.
Anda dapat memantau kemajuan pemutakhiran menggunakan cmdlet Get-AzureRmSqlServerUpgrade baru.

## EXAMPLES

### Contoh 1: Memutakhirkan server
```
PS C:\>Start-AzureRmSqlServerUpgrade -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ServerVersion 12.0
ResourceGroupName               : ResourceGroup01
ServerName                      : Server01
ServerVersion                   : 12.0
ScheduleUpgradeAfterUtcDateTime : 
DatabaseCollection              :
```

Perintah ini memutakhirkan server bernama server01 yang ditetapkan ke grup sumber daya TesourceGroup01.

### Contoh 2: Memutakhirkan server dengan menggunakan rekomendasi jadwal dan waktu database
```
PS C:\>$ScheduleTime = (Get-Date).AddMinutes(5).ToUniversalTime()
PS C:\> $DatabaseMap = New-Object -TypeName Microsoft.Azure.Management.Sql.Models.RecommendedDatabaseProperties
PS C:\> $DatabaseMap.Name = "contosodb"
PS C:\> $DatabaseMap.TargetEdition = "Standard"
PS C:\> $DatabaseMap.TargetServiceLevelObjective = "S0"
PS C:\> Start-AzureRmSqlServerUpgrade -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ServerVersion 12.0 -ScheduleUpgradeAfterUtcDateTime $ScheduleTime -DatabaseCollection ($DatabaseMap)
```

Perintah pertama membuat waktu lima menit di masa mendatang dengan menggunakan cmdlet Get-Date baru.
Perintah menyimpan tanggal dalam variabel $ScheduleTime.
Untuk informasi selengkapnya, ketik `Get-Help Get-Date` .

Perintah kedua membuat objek **RecommendedDatabaseProperties,** lalu menyimpan objek tersebut dalam $DatabaseMap.

Tiga perintah berikutnya menetapkan nilai ke properti objek yang disimpan di $DatabaseMap.

Perintah terakhir memutakhirkan server yang sudah ada bernama Server01 ke versi 12.0.
Waktu paling awal untuk memutakhirkan adalah lima menit setelah Anda menjalankan perintah, seperti yang ditentukan oleh $ScheduleTime variabel.
Setelah pemutakhiran, database contosodb akan menjalankan edisi Standar dan memiliki S0 Tujuan Tingkat Layanan.

## PARAMETERS

### -DatabaseCollection
Menentukan array objek **RecommendedDatabaseProperties** yang digunakan cmdlet ini untuk pemutakhiran server.

```yaml
Type: RecommendedDatabaseProperties[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ElastisPoolCollection
Menentukan array objek **UpgradeRecommendedElasticPoolProperties** yang akan digunakan untuk pemutakhiran server.

```yaml
Type: UpgradeRecommendedElasticPoolProperties[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat server ditetapkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScheduleUpgradeAfterUtcDateTime
Menentukan waktu paling awal, sebagai objek **DateTime,** untuk memutakhirkan server.
Tentukan nilai dalam format ISO8601, dalam Waktu Universal Terkoordinasi (UTC).
Untuk informasi selengkapnya, ketik `Get-Help Get-Date` .

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Menentukan nama server yang dimutakhirkan cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerVersion
Menentukan versi cmdlet ini memutakhirkan server.
Satu-satunya nilai yang valid adalah 12,0.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ServerUpgrade.Model.AzureSqlServerUpgradeModel

## CATATAN

## RELATED LINKS

[Get-AzureRmSqlServerUpgrade](./Get-AzureRmSqlServerUpgrade.md)

[Stop-AzureRmSqlServerUpgrade](./Stop-AzureRmSqlServerUpgrade.md)

[SQL Database Dokumen](https://docs.microsoft.com/azure/sql-database/)


