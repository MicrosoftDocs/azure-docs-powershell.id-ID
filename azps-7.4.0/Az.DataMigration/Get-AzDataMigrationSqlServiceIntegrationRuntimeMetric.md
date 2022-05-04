---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationsqlserviceintegrationruntimemetric
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric.md
ms.openlocfilehash: fa73df32c5ffe80341ddb5d2a4f06a375bad64b4
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144691262"
---
# Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric

## SYNOPSIS
Mengambil simpul Integration Runtime terdaftar dan data pemantauannya untuk Database Migration Service tertentu

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datamigration/get-azdatamigrationsqlserviceintegrationruntimemetric) untuk informasi terbaru.

## SYNTAX

```
Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric -ResourceGroupName <String>
 -SqlMigrationServiceName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mengambil simpul Integration Runtime terdaftar dan data pemantauannya untuk Database Migration Service tertentu

## EXAMPLES

### Contoh 1: Dapatkan simpul Integration Runtime terdaftar dan data pemantauannya untuk Sql Migration Service tertentu
```powershell
Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService" | Select *
```

```output
Name       Node
----       ----
default-ir {WIN-AKLAB}
```

Perintah ini mendapatkan simpul Integration Runtime terdaftar dan data pemantauannya untuk Sql Migration Service tertentu.

### Contoh 2: Mencetak data pemantauan untuk setiap simpul Integration Runtime
```powershell
$item = Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric -ResourceGroupName "MyResourceGroup" -SqlMigrationService "MySqlMigrationService"
$item.Node[0] 
```

```output
AvailableMemoryInMb ConcurrentJobsLimit ConcurrentJobsRunning CpuUtilization MaxConcurrentJob NodeName     ReceivedByte     SentByte
------------------- ------------------- --------------------- -------------- ---------------- --------     ------------     --------
200138              20                  0                     8                               WIN-AKLAB    9.33309006690979 5.433871746063232
```

Perintah pertama mendapatkan data pemantauan simpul dari Sql Migration Service.
Perintah kedua kemudian digunakan untuk mencetak data pemantauan untuk setiap simpul.

## PARAMETERS

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

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -SqlMigrationServiceName
Nama SQL Migration Service.

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
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20211030Preview.IIntegrationRuntimeMonitoringData

## NOTES

ALIAS

## RELATED LINKS
