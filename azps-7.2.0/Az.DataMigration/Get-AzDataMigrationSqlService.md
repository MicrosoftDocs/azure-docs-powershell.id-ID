---
external help file: ''
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationsqlservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlService.md
ms.openlocfilehash: 5dd30014a36bc829b727fd16881e37d4970a2a22
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138275244"
---
# Get-AzDataMigrationSqlService

## SYNOPSIS
Ambil Layanan Migrasi Database.

## SYNTAX

### Daftar1 (Default)
```
Get-AzDataMigrationSqlService [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzDataMigrationSqlService -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDataMigrationSqlService -InputObject <IDataMigrationIdentity> [-DefaultProfile <PSObject>] [-PassThru]
 [<CommonParameters>]
```

### Daftar
```
Get-AzDataMigrationSqlService -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
Ambil Layanan Migrasi Database.

## EXAMPLES

### Contoh 1: Mendapatkan detail tentang Sql Migration Service
```powershell
PS C:\> Get-AzDataMigrationSqlService  -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService"

Location  Name                   Type                                         ProvisioningState IntegrationRuntimeState
--------  ----                   ----                                         ----------------- -----------------------
eastus2   MySqlMigrationService  Microsoft.DataMigration/sqlMigrationServices Succeeded         Online
```

Perintah ini mendapatkan detail dari Layanan Migrasi Sql yang diberikan.

### Contoh 2: Dapatkan semua Layanan Migrasi Sql dalam Grup Sumber Daya yang diberikan
```powershell
PS C:\> Get-AzDataMigrationSqlService  -ResourceGroupName "MyResourceGroup"

Location  Name                   Type                                         ProvisioningState IntegrationRuntimeState
--------  ----                   ----                                         ----------------- -----------------------
eastus    MySqlMigrationService1 Microsoft.DataMigration/sqlMigrationServices Succeeded
eastus2   MySqlMigrationService  Microsoft.DataMigration/sqlMigrationServices Succeeded                  
```

Perintah ini mendapatkan semua Layanan Migrasi Sql dalam Grup Sumber Daya yang diberikan.

### Contoh 3: Mendapatkan semua Layanan Migrasi Sql dalam Langganan tertentu
```powershell
PS C:\> Get-AzDataMigrationSqlService 

Location  Name                      Type                                         ProvisioningState IntegrationRuntimeState
--------  ----                      ----                                         ----------------- -----------------------
eastus    MySqlMigrationService1    Microsoft.DataMigration/sqlMigrationServices Succeeded
eastus2   MySqlMigrationService     Microsoft.DataMigration/sqlMigrationServices Succeeded
uksouth   MySqlMigrationService-UK  Microsoft.DataMigration/sqlMigrationServices Succeeded                   
```

Perintah ini akan mendapatkan semua Layanan Migrasi Sql dalam Langganan tertentu.

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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
Nama layanan SQL migrasi.

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
Nama grup sumber daya yang berisi sumber daya tersebut.
Anda dapat memperoleh nilai ini dari API Azure Resource Manager atau portal.

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
Parameter Sets: Get, List, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang berisi sumber daya tersebut. Anda dapat memperoleh nilai ini dari API Azure Resource Manager atau portal.
  - `[SqlMigrationServiceName <String>]`: Nama SQL Migrasi.
  - `[SqlVirtualMachineName <String>]`: 
  - `[SubscriptionId <String>]`: ID langganan yang mengidentifikasi langganan Azure.
  - `[TargetDbName <String>]`: Nama database target.

## RELATED LINKS

