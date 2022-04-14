---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationsqlservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlService.md
ms.openlocfilehash: fb81fdc31a61c0a915d6d17d57f368e5741efb87
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141894734"
---
# Get-AzDataMigrationSqlService

## SYNOPSIS
Ambil Database Migration Service.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datamigration/get-azdatamigrationsqlservice) untuk informasi terbaru.

## SYNTAX

### List1 (Default)
```
Get-AzDataMigrationSqlService [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru]
 [<CommonParameters>]
```

### Mendapatkan
```
Get-AzDataMigrationSqlService -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

### Daftar
```
Get-AzDataMigrationSqlService -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDataMigrationSqlService -InputObject <IDataMigrationIdentity> [-DefaultProfile <PSObject>] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
Ambil Database Migration Service.

## EXAMPLES

### Contoh 1: Dapatkan detail Layanan Migrasi Sql tertentu
```powershell
PS C:\> Get-AzDataMigrationSqlService  -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService"

Location  Name                   Type                                         ProvisioningState IntegrationRuntimeState
--------  ----                   ----                                         ----------------- -----------------------
eastus2   MySqlMigrationService  Microsoft.DataMigration/sqlMigrationServices Succeeded         Online
```

Perintah ini mendapatkan detail Layanan Migrasi Sql tertentu.

### Contoh 2: Dapatkan semua Layanan Migrasi Sql dalam Grup Sumber Daya tertentu
```powershell
PS C:\> Get-AzDataMigrationSqlService  -ResourceGroupName "MyResourceGroup"

Location  Name                   Type                                         ProvisioningState IntegrationRuntimeState
--------  ----                   ----                                         ----------------- -----------------------
eastus    MySqlMigrationService1 Microsoft.DataMigration/sqlMigrationServices Succeeded
eastus2   MySqlMigrationService  Microsoft.DataMigration/sqlMigrationServices Succeeded
```

Perintah ini mendapatkan semua Layanan Migrasi Sql dalam Grup Sumber Daya tertentu.

### Contoh 3: Dapatkan semua Layanan Migrasi Sql dalam Langganan tertentu
```powershell
PS C:\> Get-AzDataMigrationSqlService 

Location  Name                      Type                                         ProvisioningState IntegrationRuntimeState
--------  ----                      ----                                         ----------------- -----------------------
eastus    MySqlMigrationService1    Microsoft.DataMigration/sqlMigrationServices Succeeded
eastus2   MySqlMigrationService     Microsoft.DataMigration/sqlMigrationServices Succeeded
uksouth   MySqlMigrationService-UK  Microsoft.DataMigration/sqlMigrationServices Succeeded
```

Perintah ini mendapatkan semua Layanan Migrasi Sql dalam Langganan tertentu.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.IDataMigrationIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Layanan Migrasi SQL.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: SqlMigrationServiceName

Required: True
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
Parameter Sets: Get, List
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
Parameter Sets: List1, Get, List
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

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.IDataMigrationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20211030Preview.ISqlMigrationService

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDataMigrationIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ManagedInstanceName <String>]`: 
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang berisi sumber daya. Anda dapat memperoleh nilai ini dari API azure Resource Manager atau portal.
  - `[SqlMigrationServiceName <String>]`: Nama Layanan Migrasi SQL.
  - `[SqlVirtualMachineName <String>]`: 
  - `[SubscriptionId <String>]`: ID Langganan yang mengidentifikasi langganan Azure.
  - `[TargetDbName <String>]`: Nama database target.

## RELATED LINKS
