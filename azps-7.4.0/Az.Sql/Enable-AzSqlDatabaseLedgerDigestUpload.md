---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/enable-azsqldatabaseledgerdigestupload
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Enable-AzSqlDatabaseLedgerDigestUpload.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Enable-AzSqlDatabaseLedgerDigestUpload.md
ms.openlocfilehash: 4031e43428234f66e18998da550efb39b2c1081c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142165369"
---
# Enable-AzSqlDatabaseLedgerDigestUpload

## SYNOPSIS
Memungkinkan pengunggahan pencernaan buku besar ke akun Azure Storage atau ke Azure Confidential Ledger.

## SYNTAX

### DatabaseParameterSet (Default)
```
Enable-AzSqlDatabaseLedgerDigestUpload [-Endpoint] <String> [-ResourceGroupName] <String>
 [-ServerName] <String> [-DatabaseName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObjectParameterSet
```
Enable-AzSqlDatabaseLedgerDigestUpload [-Endpoint] <String> -InputObject <AzureSqlDatabaseModel>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Enable-AzSqlDatabaseLedgerDigestUpload [-Endpoint] <String> [-ResourceId] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Enable-AzSqlDatabaseLedgerDigestUpload memungkinkan pengunggahan pencernaan buku besar ke penyimpanan Azure Blob atau Azure Confidential Ledger. Untuk menggunakan cmdlet, tentukan titik akhir akun penyimpanan Blob Azure atau buku besar di Azure Confidential Ledger, dan identifikasi database. Jika pengunggahan pencernaan ledger sudah diaktifkan, cmdlet akan mengatur ulang titik akhir penyimpanan digest ke nilai baru.

## EXAMPLES

### Contoh 1
```powershell
Enable-AzSqlDatabaseLedgerDigestUpload -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01" -Endpoint "https://mystorage.blob.core.windows.net" 
```

```output
ResourceGroupName ServerName DatabaseName State   Endpoint
----------------- ---------- ------------ -----   --------
ResourceGroup01   Server01   Database01   Enabled https://mystorage.blob.core.windows.net 
```
## PARAMETERS

### -DatabaseName
SQL Database nama.

```yaml
Type: System.String
Parameter Sets: DatabaseParameterSet
Aliases:

Required: True
Position: 2
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

### -Titik akhir
Titik akhir Unggahan Azure Sql Database Ledger Digest.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek database untuk menonaktifkan unggahan digest.

```yaml
Type: Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel
Parameter Sets: InputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: DatabaseParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya database untuk menonaktifkan unggahan digest.

```yaml
Type: System.String
Parameter Sets: ResourceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
SQL nama server.

```yaml
Type: System.String
Parameter Sets: DatabaseParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.LedgerDigestUploads.Model.AzureSqlDatabaseLedgerDigestLocationModel

## CATATAN

## RELATED LINKS
