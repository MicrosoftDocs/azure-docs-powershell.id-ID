---
external help file: ''
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/register-azdatamigrationintegrationruntime
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Register-AzDataMigrationIntegrationRuntime.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Register-AzDataMigrationIntegrationRuntime.md
ms.openlocfilehash: 2a1947a0e047b3b1b38bd4204020ea7c6642959c
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140124585"
---
# Register-AzDataMigrationIntegrationRuntime

## SYNOPSIS
Mendaftarkan Layanan Migrasi Sql pada Integration Runtime

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.datamigration/register-azdatamigrationintegrationruntime) untuk informasi terkini.

## SYNTAX

```
Register-AzDataMigrationIntegrationRuntime -AuthKey <String> [-IntegrationRuntimePath <String>] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mendaftarkan Layanan Migrasi Sql pada Integration Runtime

## EXAMPLES

### Contoh 1: Mendaftarkan Sql Migration Service pada Self Hosted Integration Runtime
```powershell
PS C:\> $authKeys = Get-AzDataMigrationSqlMigrationServiceAuthKey -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService"
PS C:\> Register-AzDataMigrationIntegrationRuntime -AuthKey $authKeys.AuthKey1

Start to register IR with key: IR@abcd1-efgh2-jklmn3-opqr4@mysqlms@eastus@stuv5/wxyz6=
Integration Runtime registration is successful!
```

Perintah ini mendaftarkan Sql Migration Service pada Self Hosted Integration Runtime.

### Contoh 2: Menginstal Integration Runtime dan mendaftarkan Sql Migration Service di dalamnya
```powershell
PS C:\> $authKeys = Get-AzDataMigrationSqlMigrationServiceAuthKey -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService"
PS C:\> Register-AzDataMigrationIntegrationRuntime -AuthKey $authKeys.AuthKey1 -IntegrationRuntimePath "C:\Users\user\Downloads\IntegrationRuntime.msi"

Start Gateway installation
Succeed to install gateway
Start to register IR with key: IR@abcd1-efgh2-jklmn3-opqr4@mysqlms@eastus@stuv5/wxyz6=
Integration Runtime registration is successful!
```

Perintah ini akan menginstal Integration Runtime dan mendaftarkan Sql Migration Service di dalamnya.

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
Jalur SHIR msi

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

