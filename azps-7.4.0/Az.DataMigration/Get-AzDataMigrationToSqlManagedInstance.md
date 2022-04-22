---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationtosqlmanagedinstance
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationToSqlManagedInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationToSqlManagedInstance.md
ms.openlocfilehash: 2ae04e7fb38161927310f19c07b89461970f79e5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143063567"
---
# Get-AzDataMigrationToSqlManagedInstance

## SYNOPSIS
Ambil migrasi database yang ditentukan untuk SQL Managed Instance tertentu.

## SYNTAX

### Dapatkan (Default)
```
Get-AzDataMigrationToSqlManagedInstance -ManagedInstanceName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] -TargetDbName <String> [-Expand <String>] [-MigrationOperationId <String>]
 [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDataMigrationToSqlManagedInstance -InputObject <IDataMigrationIdentity> [-Expand <String>]
 [-MigrationOperationId <String>] [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
Ambil migrasi database yang ditentukan untuk SQL Managed Instance tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan detail Migrasi Database tertentu ke SQL Managed Instance
```powershell
Get-AzDataMigrationToSqlManagedInstance -ResourceGroupName "MyResourceGroup" -ManagedInstanceName "MyManagedInstance" -TargetDbName "MyDatabase"
```

```output
Name               Type                                       Kind  ProvisioningState MigrationStatus
----               ----                                       ----  ----------------- ---------------
MyDatabase         Microsoft.DataMigration/databaseMigrations SqlMi Succeeded         Succeeded
```

Perintah ini mendapatkan detail Migrasi Database tertentu ke SQL Managed Instance.

### Contoh 2: Dapatkan detail yang diperluas dari Migrasi Database tertentu ke SQL Managed Instance
```powershell
$miMigration = Get-AzDataMigrationToSqlManagedInstance -ResourceGroupName "MyResourceGroup" -ManagedInstanceName "MyManagedInstance" -TargetDbName "MyDatabase" -Expand MigrationStatusDetails
$miMigration.MigrationStatusDetail
```

```output
BlobContainerName                    CompleteRestoreErrorMessage CurrentRestoringFilename          FileUploadBlockingError 
-----------------                    --------------------------- ------------------------          ----------------------- 
2673894b-451c-41cv-ae2b-58a8eefe3546                             AdventureWorks.bak
```

Perintah ini mendapatkan detail yang diperluas dari Migrasi Database tertentu ke SQL Managed Instance.

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

### -Perluas
Sumber daya anak yang akan disertakan dalam respons.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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

### -ManagedInstanceName
.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationOperationId
ID operasi migrasi opsional.
Jika ini disediakan, maka detail operasi migrasi untuk ID tersebut diambil.
Jika tidak disediakan (default), maka detail yang terkait dengan operasi terbaru atau saat ini diambil.

```yaml
Type: System.String
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
Parameter Sets: Get
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
Parameter Sets: Get
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
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.IDataMigrationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20211030Preview.IDatabaseMigrationSqlMi

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDataMigrationIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ManagedInstanceName <String>]`: 
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang berisi sumber daya. Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.
  - `[SqlMigrationServiceName <String>]`: Nama SQL Migration Service.
  - `[SqlVirtualMachineName <String>]`: 
  - `[SubscriptionId <String>]`: ID Langganan yang mengidentifikasi langganan Azure.
  - `[TargetDbName <String>]`: Nama database target.

## RELATED LINKS
