---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationsqlserviceauthkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlServiceAuthKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlServiceAuthKey.md
ms.openlocfilehash: c4d5d377b30ca17fd7613f611fa29910d9655701
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145500650"
---
# Get-AzDataMigrationSqlServiceAuthKey

## SYNOPSIS
Ambil Daftar Kunci Autentikasi untuk Integration Runtime yang Dihost sendiri.

## SYNTAX

```
Get-AzDataMigrationSqlServiceAuthKey -ResourceGroupName <String> -SqlMigrationServiceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Ambil Daftar Kunci Autentikasi untuk Integration Runtime yang Dihost sendiri.

## EXAMPLES

### Contoh 1: Dapatkan AuthKeys untuk Sql Migration Service tertentu
```powershell
Get-AzDataMigrationSqlServiceAuthKey -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService"
```

```output
AuthKey1                                                 AuthKey2
--------                                                 --------
IR@abcd1-efgh2-jklmn3-opqr4@mysqlms@eastus@stuv5/wxyz6=  IR@abcd6-efgh5-jklmn4-opqr3@mysqlms@eastus@stuv2/wxyz1=
```

Perintah ini mendapatkan AuthKeys untuk Sql Migration Service tertentu.

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

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20220330Preview.IAuthenticationKeys

## NOTES

ALIAS

## RELATED LINKS
