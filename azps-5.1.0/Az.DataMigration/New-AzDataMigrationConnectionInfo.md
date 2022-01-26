---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataMigration.dll-Help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/en-us/powershell/module/az.datamigration/New-AzDataMigrationConnectionInfo
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/DataMigration/DataMigration/help/New-AzDataMigrationConnectionInfo.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/DataMigration/DataMigration/help/New-AzDataMigrationConnectionInfo.md
ms.openlocfilehash: e902785745ab22ab9bc1386fc2c6a2f9dd416b79
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136022590"
---
# New-AzDataMigrationConnectionInfo

## SYNOPSIS
Membuat objek Info Koneksi baru yang menentukan tipe server dan nama untuk koneksi.

## SINTAKS

```
New-AzDataMigrationConnectionInfo -ServerType <ServerTypeEnum> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESKRIPSI
Cmdlet New-AzDataMigrationConnectionInfo membuat objek Baru Info Koneksi yang menentukan tipe server untuk koneksi. 

## CONTOH

### Contoh 1
```
PS C:\> New-AzDmsConnInfo -ServerType SQL -DataSource mySourceServer -AuthType SqlAuthentication -TrustServerCertificate:$true
```

Contoh sebelumnya membuat objek Info Koneksi baru yang menyediakan SQL sebagai parameter ServerType.

## PARAMETERS

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

### -ServerType
Enum yang menjelaskan tipe server yang akan disambungkan. Nilai yang didukung saat ini SQL untuk SQL Server, Azure SQL Managed Instance, SandboxoDb, CosmosDb, dan Azure SQL Database. 

```yaml
Type: Microsoft.Azure.Commands.DataMigration.Models.ServerTypeEnum
Parameter Sets: (All)
Aliases:
Accepted values: SQL, MongoDb, SQLMI

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Tidak ada

## OUTPUT

### Microsoft.Azure.Management.DataMigration.Models.ConnectionInfo

## CATATAN

## LINK TERKAIT
