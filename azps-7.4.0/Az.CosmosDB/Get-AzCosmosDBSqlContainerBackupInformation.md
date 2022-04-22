---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdbsqlcontainerbackupinformation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBSqlContainerBackupInformation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBSqlContainerBackupInformation.md
ms.openlocfilehash: b82740d9dcee712c61d96bcf39d776e7cc59a1a5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143004329"
---
# Get-AzCosmosDBSqlContainerBackupInformation

## SYNOPSIS
Mengambil stempel waktu terbaru yang dapat disembuhkan untuk wadah sql.

## SYNTAX

```
Get-AzCosmosDBSqlContainerBackupInformation -ResourceGroupName <String> -AccountName <String>
 -DatabaseName <String> -Name <String> -Location <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengambil stempel waktu terbaru yang dapat disembuhkan untuk wadah sql. Ini adalah upto stempel waktu terbaru yang dapat berhasil dipulihkan oleh pengguna dalam wadah ini.

## EXAMPLES

### Contoh 1
```powershell
Get-AzCosmosDBSqlContainerBackupInformation -ResourceGroupName CosmosDBResourceGroup3668 -AccountName pitr-sql-stage-source -DatabaseName TestDB1 -Name TestCollectionInDB1 -Location "EAST US 2"
```

```output
LatestRestorableTimestamp
-------------------------
1623042210
```

Mengambil stempel waktu terbaru yang dapat disembuhkan untuk wadah sql. Ini adalah upto stempel waktu terbaru yang dapat berhasil dipulihkan oleh pengguna dalam wadah ini.

## PARAMETERS

### -AccountName
Nama akun database Cosmos DB.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Nama database.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Lokasi
-Nama Lokasi dalam string.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kontainer.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

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

### Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.Models.Restore.Sql.PSSqlBackupInformation

## NOTES

## RELATED LINKS
