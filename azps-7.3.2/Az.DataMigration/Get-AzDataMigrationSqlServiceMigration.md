---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationsqlservicemigration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlServiceMigration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlServiceMigration.md
ms.openlocfilehash: cf065cfd5a062c175aa28ac5a12461cf476ebc27
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143185175"
---
# Get-AzDataMigrationSqlServiceMigration

## SYNOPSIS
Ambil Daftar migrasi database yang dilampirkan ke layanan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datamigration/get-azdatamigrationsqlservicemigration) untuk informasi terbaru.

## SYNTAX

```
Get-AzDataMigrationSqlServiceMigration -ResourceGroupName <String> -SqlMigrationServiceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
Ambil Daftar migrasi database yang dilampirkan ke layanan.

## EXAMPLES

### Contoh 1: Dapatkan daftar migrasi database yang dilampirkan ke Layanan Migrasi Sql tertentu
```powershell
PS C:\> Get-AzDataMigrationSqlServiceMigration -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService"

Name                                   Type                                       Kind  ProvisioningState MigrationStatus
----                                   ----                                       ----  ----------------- ---------------
MyDatabase                             Microsoft.DataMigration/databaseMigrations SqlMi Succeeded         InProgress
MyDatabaseSqlMi                        Microsoft.DataMigration/databaseMigrations SqlMi Succeeded         Succeeded
MyDatabaseSqlVM                        Microsoft.DataMigration/databaseMigrations SqlVm Succeeded         Succeeded
```

Perintah ini mendapatkan daftar migrasi database yang dilampirkan ke layanan Migrasi Sql tertentu.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20211030Preview.IDatabaseMigration

## NOTES

ALIAS

## RELATED LINKS
