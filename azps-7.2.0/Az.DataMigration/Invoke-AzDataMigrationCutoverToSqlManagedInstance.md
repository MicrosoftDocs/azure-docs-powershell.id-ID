---
external help file: ''
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/invoke-azdatamigrationcutovertosqlmanagedinstance
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Invoke-AzDataMigrationCutoverToSqlManagedInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Invoke-AzDataMigrationCutoverToSqlManagedInstance.md
ms.openlocfilehash: 8bdd922f07a362cf4117e011ab3127a5f24316f5
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140090567"
---
# Invoke-AzDataMigrationCutoverToSqlManagedInstance

## SYNOPSIS
Memulai langsung migrasi database online yang sedang berlangsung SQL Contoh Terkelola.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.datamigration/invoke-azdatamigrationcutovertosqlmanagedinstance) untuk informasi terkini.

## SYNTAX

```
Invoke-AzDataMigrationCutoverToSqlManagedInstance -ManagedInstanceName <String> -ResourceGroupName <String>
 -TargetDbName <String> [-SubscriptionId <String>] [-MigrationOperationId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memulai langsung migrasi database online yang sedang berlangsung SQL Contoh Terkelola.

## EXAMPLES

### Contoh 1: Memulai langsung migrasi online yang ditentukan saat ini ke SQL Terkelola
```powershell
PS C:\> $miMigration = Get-AzDataMigrationToSqlManagedInstance -ResourceGroupName "MyResourceGroup" -ManagedInstanceName "MyManagedInstance" -TargetDbName "MyDatabase"
PS C:\> Invoke-AzDataMigrationCutoverToSqlManagedInstance -ResourceGroupName "MyResourceGroup" -ManagedInstanceName "MyManagedInstance" -TargetDbName "MyDatabase" -MigrationOperationId $miMigration.MigrationOperationId
PS C:\> Get-AzDataMigrationToSqlManagedInstance -InputObject $miMigration 

Name               Type                                       Kind  ProvisioningState MigrationStatus
----               ----                                       ----  ----------------- ---------------
MyDatabase         Microsoft.DataMigration/databaseMigrations SqlMi Completing        Completing
```

Perintah ini memulai langsung migrasi online dalam proses tertentu untuk mengelola SQL Terkelola.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -ManagedInstanceName
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

### -MigrationOperationId
Operasi pelacakan ID migrasi.

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

### -NoWait
Menjalankan perintah secara asinkron

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
Nama grup sumber daya yang berisi sumber daya tersebut.
Anda dapat memperoleh nilai ini dari API Azure Resource Manager atau portal.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

## RELATED LINKS

