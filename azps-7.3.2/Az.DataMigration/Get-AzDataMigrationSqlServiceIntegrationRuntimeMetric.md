---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationsqlserviceintegrationruntimemetric
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric.md
ms.openlocfilehash: 664aae7bac7c0ab02619879144d9823857ecc0d4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141852242"
---
# Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric

## SYNOPSIS
Mengambil node Integration Runtime yang terdaftar dan data pemantauannya untuk Database Migration Service

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datamigration/get-azdatamigrationsqlserviceintegrationruntimemetric) untuk informasi terbaru.

## SYNTAX

```
Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric -ResourceGroupName <String>
 -SqlMigrationServiceName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mengambil node Integration Runtime yang terdaftar dan data pemantauannya untuk Database Migration Service

## EXAMPLES

### Contoh 1: Dapatkan node Integration Runtime terdaftar dan data pemantauannya untuk Layanan Migrasi Sql tertentu
```powershell
PS C:\> Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService" | Select *

Name       Node
----       ----
default-ir {WIN-AKLAB}
```

Perintah ini mendapatkan simpul Integration Runtime terdaftar dan data pemantauannya untuk Layanan Migrasi Sql tertentu.

### Contoh 2: Cetak data pemantauan untuk setiap simpul Integration Runtime
```powershell
PS C:\> $item = Get-AzDataMigrationSqlServiceIntegrationRuntimeMetric -ResourceGroupName "MyResourceGroup" -SqlMigrationService "MySqlMigrationService"
PS C:\> $item.Node[0] 

AvailableMemoryInMb ConcurrentJobsLimit ConcurrentJobsRunning CpuUtilization MaxConcurrentJob NodeName     ReceivedByte     SentByte
------------------- ------------------- --------------------- -------------- ---------------- --------     ------------     --------
200138              20                  0                     8                               WIN-AKLAB    9.33309006690979 5.433871746063232
```

Perintah pertama mendapatkan data pemantauan simpul dari Layanan Migrasi Sql.
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
Anda dapat memperoleh nilai ini dari API azure Resource Manager atau portal.

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
Nama Layanan Migrasi SQL.

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
ID Langganan yang mengidentifikasi langganan Azure.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20211030Preview.IIntegrationRuntimeMonitoringData

## CATATAN

ALIAS

## RELATED LINKS
