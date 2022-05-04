---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataLakeAnalytics.dll-Help.xml
Module Name: Az.DataLakeAnalytics
ms.assetid: A6899341-1E5E-4F8B-8D5D-5923B1223628
online version: https://docs.microsoft.com/powershell/module/az.datalakeanalytics/get-azdatalakeanalyticscatalogitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeAnalytics/DataLakeAnalytics/help/Get-AzDataLakeAnalyticsCatalogItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeAnalytics/DataLakeAnalytics/help/Get-AzDataLakeAnalyticsCatalogItem.md
ms.openlocfilehash: fc2b2b48e8a2fc285e1c8f361928b64b81e73ada
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144631126"
---
# Get-AzDataLakeAnalyticsCatalogItem

## SYNOPSIS
Mendapatkan item katalog Data Lake Analytics atau jenis item.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datalakeanalytics/get-azdatalakeanalyticscatalogitem) untuk informasi terbaru.

## SYNTAX

```
Get-AzDataLakeAnalyticsCatalogItem [-Account] <String> [-ItemType] <CatalogItemType>
 [[-Path] <CatalogPathInstance>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Get-AzDataLakeAnalyticsCatalogItem** mendapatkan item katalog Azure Data Lake Analytics tertentu, atau mendapatkan item katalog dari jenis tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan database tertentu
```powershell
Get-AzDataLakeAnalyticsCatalogItem -Account "contosoadla" -ItemType Database -Path "databaseName"
```

Perintah ini mendapatkan database yang ditentukan.

### Contoh 2: Mendapatkan tabel dalam database dan skema tertentu
```powershell
Get-AzDataLakeAnalyticsCatalogItem -AccountName "contosoadla" -ItemType Table -Path "databaseName.schemaName"
```

Perintah ini mendapatkan daftar tabel dalam database yang ditentukan.

## PARAMETERS

### -Akun
Menentukan nama akun Data Lake Analytics.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
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

### -ItemType
Menentukan tipe item katalog dari item yang diambil atau dicantumkan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Database
- Skema
- Rakitan
- Tabel
- TableValuedFunction
- TableStatistics
- ExternalDataSource
- Tampilan
- Prosedur
- Rahasia
- Informasi masuk
- Jenis
- TablePartition

```yaml
Type: Microsoft.Azure.Commands.DataLakeAnalytics.Models.DataLakeAnalyticsEnums+CatalogItemType
Parameter Sets: (All)
Aliases:
Accepted values: Database, Schema, Assembly, Table, TablePartition, TableValuedFunction, TableStatistics, ExternalDataSource, View, Procedure, Secret, Credential, Types, Package

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Jalur
Menentukan jalur multi-bagian ke item yang akan diambil, atau ke item induk item yang akan dicantumkan.
Bagian-bagian jalur harus dipisahkan oleh titik (.).

```yaml
Type: Microsoft.Azure.Commands.DataLakeAnalytics.Models.CatalogPathInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.DataLakeAnalytics.Models.DataLakeAnalyticsEnums+CatalogItemType

### Microsoft.Azure.Commands.DataLakeAnalytics.Models.CatalogPathInstance

## OUTPUTS

### Microsoft.Azure.Management.DataLake.Analytics.Models.CatalogItem

## NOTES

## RELATED LINKS

[Test-AzDataLakeAnalyticsCatalogItem](./Test-AzDataLakeAnalyticsCatalogItem.md)


