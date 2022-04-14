---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/register-azdatamigrationintegrationruntime
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Register-AzDataMigrationIntegrationRuntime.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Register-AzDataMigrationIntegrationRuntime.md
ms.openlocfilehash: 3da64985050a29a9692ff85313559bf4673c6fba
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141838435"
---
# Register-AzDataMigrationIntegrationRuntime

## SYNOPSIS
Mendaftarkan Layanan Migrasi Sql di Integration Runtime

## SYNTAX

```
Register-AzDataMigrationIntegrationRuntime -AuthKey <String> [-IntegrationRuntimePath <String>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mendaftarkan Layanan Migrasi Sql di Integration Runtime

## EXAMPLES

### Contoh 1: Daftarkan Layanan Migrasi Sql di Integration Runtime Yang Dihosting Sendiri
```powershell
$authKeys = Get-AzDataMigrationSqlMigrationServiceAuthKey -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService"
Register-AzDataMigrationIntegrationRuntime -AuthKey $authKeys.AuthKey1
```

```output
Start to register IR with key: IR@abcd1-efgh2-jklmn3-opqr4@mysqlms@eastus@stuv5/wxyz6=
Integration Runtime registration is successful!
```

Perintah ini mendaftarkan Layanan Migrasi Sql di Integration Runtime Yang Dihosting Sendiri.

### Contoh 2: Menginstal Integration Runtime dan mendaftarkan Layanan Migrasi Sql di dalamnya
```powershell
$authKeys = Get-AzDataMigrationSqlMigrationServiceAuthKey -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService"
Register-AzDataMigrationIntegrationRuntime -AuthKey $authKeys.AuthKey1 -IntegrationRuntimePath "C:\Users\user\Downloads\IntegrationRuntime.msi"
```

```output
Start Gateway installation
Succeed to install gateway
Start to register IR with key: IR@abcd1-efgh2-jklmn3-opqr4@mysqlms@eastus@stuv5/wxyz6=
Integration Runtime registration is successful!
```

Perintah ini menginstal Integration Runtime dan mendaftarkan Layanan Migrasi Sql di dalamnya.

## PARAMETERS

### -AuthKey
AuthKey dari Layanan Migrasi Sql

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

### -IntegrationRuntimePath
Jalur msi SHIR

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

### System.Boolean

## CATATAN

ALIAS

## RELATED LINKS
