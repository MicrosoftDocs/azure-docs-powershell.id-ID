---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
Module Name: AzureRM.Sql
ms.assetid: D64FB139-04E2-47BC-86FB-EEEA23839F2F
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.sql/get-azurermsqldatabaseupgradehint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Get-AzureRmSqlDatabaseUpgradeHint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Get-AzureRmSqlDatabaseUpgradeHint.md
ms.openlocfilehash: d279dffcb7eda54d03af0d391c8d118236072942a734370be5e850ad6e18332a
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418525"
---
# Get-AzureRmSqlDatabaseUpgradeHint

## SYNOPSIS
Mendapatkan petunjuk tingkatan harga untuk database.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmSqlDatabaseUpgradeHint [-ServerName] <String> [-DatabaseName <String>]
 [-ExcludeElasticPoolCandidates <Boolean>] [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmSqlDatabaseUpgradeHint** mendapatkan petunjuk tingkatan harga untuk pemutakhiran Azure SQL Database.
Database yang masih berada di tingkatan harga Web dan Bisnis mendapatkan petunjuk untuk memutakhirkan ke tingkat Dasar, Standar, atau Premium harga yang baru.
Cmdlet ini juga didukung oleh layanan SQL Server Stretch Database di Azure.

## EXAMPLES

### Contoh 1: Mendapatkan rekomendasi untuk semua database di server
```
PS C:\>Get-AzureRmSqlDatabaseUpgradeHint -ResourceGroupName "ResourceGroup01" -ServerName "Server01"
```

Perintah ini mengembalikan petunjuk pemutakhiran untuk semua database di server bernama Server01.

### Contoh 2: Mendapatkan rekomendasi untuk database tertentu
```
PS C:\>Get-AzureRmSqlDatabaseUpgradeHint -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01"
```

Perintah ini mengembalikan petunjuk pemutakhiran untuk database tertentu.

### Contoh 3: Mendapatkan rekomendasi untuk semua database yang tidak dalam kolam database elastis
```
PS C:\>Get-AzureRmSqlDatabaseUpgradeHint -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -ExcludeElasticPoolCandidates $True
```

Perintah ini mengembalikan petunjuk pemutakhiran untuk semua database yang tidak dalam kolam database elastis.

## PARAMETERS

### -DatabaseName
Menentukan nama database SQL di mana cmdlet ini mendapatkan petunjuk pemutakhiran.
Jika Anda tidak menentukan database, cmdlet ini akan mendapatkan petunjuk untuk semua database pada server logika.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeElasticPoolCandidates
Menunjukkan apakah database dalam kolam renang database elastis dikecualikan dari rekomendasi yang dikembalikan.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat database ditetapkan.

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
Menentukan nama server yang menjadi host database di mana cmdlet ini mendapatkan petunjuk pemutakhiran.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### System.Boolean

## OUTPUTS

### Microsoft.Azure.Management.Sql.LegacySdk.Models.RecommendedDatabaseProperties

## CATATAN

## RELATED LINKS

[Get-AzureRmSqlDatabaseExpanded](./Get-AzureRmSqlDatabaseExpanded.md)

[Get-AzureRmSqlElasticPoolRecommendation](./Get-AzureRmSqlElasticPoolRecommendation.md)


