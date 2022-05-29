---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/stop-azdatamigrationtosqldb
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Stop-AzDataMigrationToSqlDb.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Stop-AzDataMigrationToSqlDb.md
ms.openlocfilehash: b4f455a35f63544e14bfb434bf8c1750754a3f02
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145749592"
---
# Stop-AzDataMigrationToSqlDb

## SYNOPSIS
Hentikan migrasi database yang sedang berlangsung ke SQL Db.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datamigration/stop-azdatamigrationtosqldb) untuk informasi terbaru.

## SYNTAX

```
Stop-AzDataMigrationToSqlDb -ResourceGroupName <String> -SqlDbInstanceName <String> -TargetDbName <String>
 [-SubscriptionId <String>] -MigrationOperationId <String> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Hentikan migrasi database yang sedang berlangsung ke SQL Db.

## EXAMPLES

### Contoh 1: Menghentikan migrasi yang sedang berlangsung ke SQL DB
```powershell
$dbMigration = Get-AzDataMigrationToSqlDb -ResourceGroupName "myRG" -SqlDbInstanceName "mySqlDb" -TargetDbName "mydb1"
Stop-AzDataMigrationToSqlDb -ResourceGroupName "myRG" -SqlDbInstanceName "mySqlDb" -TargetDbName "mydb1" -MigrationOperationId $dbMigration.MigrationOperationId

Get-AzDataMigrationToSqlDb -InputObject $dbMigration
```

```output
Name               Type                                       Kind  ProvisioningState MigrationStatus
----               ----                                       ----  ----------------- ---------------
mydb1         Microsoft.DataMigration/databaseMigrations SqlDb Canceling         Canceling
```

Perintah ini menghentikan migrasi yang sedang berlangsung untuk SQL Managed Instance.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationOperationId
Operasi migrasi pelacakan ID.

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

### -NoWait
Jalankan perintah secara asinkron

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya.
Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.

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

### -SqlDbInstanceName
.

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

### -SubscriptionId
ID langganan yang mengidentifikasi langganan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDbName
Nama database target.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

## RELATED LINKS
