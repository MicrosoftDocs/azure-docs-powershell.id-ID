---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 14814BF3-51AF-4E51-A8A6-661825BD88D1
online version: https://docs.microsoft.com/powershell/module/az.sql/Set-AzSqlServerMSSupportAudit
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlServerMSSupportAudit.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlServerMSSupportAudit.md
ms.openlocfilehash: 27f630d5de9e698b26385f89ddc8d4b2e2e96e00
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145502607"
---
# Set-AzSqlServerMSSupportAudit

## SYNOPSIS
Mengubah pengaturan audit operasi dukungan Microsoft dari server Azure SQL.

## SYNTAX

### ServerParameterSet (Default)
```
Set-AzSqlServerMSSupportAudit [-BlobStorageTargetState <String>] [-StorageAccountResourceId <String>]
 [-EventHubTargetState <String>] [-EventHubName <String>] [-EventHubAuthorizationRuleResourceId <String>]
 [-LogAnalyticsTargetState <String>] [-WorkspaceResourceId <String>] [-PassThru] [-ResourceGroupName] <String>
 [-ServerName] <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ServerObjectParameterSet
```
Set-AzSqlServerMSSupportAudit [-BlobStorageTargetState <String>] [-StorageAccountResourceId <String>]
 [-EventHubTargetState <String>] [-EventHubName <String>] [-EventHubAuthorizationRuleResourceId <String>]
 [-LogAnalyticsTargetState <String>] [-WorkspaceResourceId <String>] [-PassThru]
 -ServerObject <AzureSqlServerModel> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSqlServerMSSupportAudit** mengubah pengaturan audit operasi dukungan Microsoft dari server Azure SQL.
Untuk menggunakan cmdlet , gunakan parameter *ResourceGroupName* dan *ServerName* untuk mengidentifikasi server.
Saat penyimpanan blob adalah tujuan untuk log audit, tentukan parameter *StorageAccountResourceId* untuk menentukan akun penyimpanan untuk log audit.

## EXAMPLES

### Contoh 1: Aktifkan penyimpanan blob Microsoft mendukung kebijakan audit operasi server Azure SQL
```powershell
Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/7fe3301d-31d3-4668-af5e-211a890ba6e3/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage"
```

### Contoh 2: Menonaktifkan penyimpanan blob Microsoft mendukung kebijakan audit operasi server Azure SQL
```powershell
Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -BlobStorageTargetState Disabled
```

### Contoh 3: Mengaktifkan hub peristiwa Microsoft mendukung kebijakan audit operasi server Azure SQL
```powershell
Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -EventHubTargetState Enabled -EventHubName "EventHubName" -EventHubAuthorizationRuleResourceId "EventHubAuthorizationRuleResourceId"
```

### Contoh 4: Menonaktifkan kebijakan audit operasi dukungan Microsoft hub peristiwa dari server Azure SQL
```powershell
Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -EventHubTargetState Disabled
```

### Contoh 5: Mengaktifkan analitik log Microsoft mendukung kebijakan audit operasi server Azure SQL
```powershell
Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -LogAnalyticsTargetState Enabled -WorkspaceResourceId "/subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/viruela2"
```

### Contoh 6: Menonaktifkan kebijakan audit operasi dukungan Microsoft analitik log dari server Azure SQL
```powershell
Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -LogAnalyticsTargetState Disabled
```

### Contoh 7: Nonaktifkan, melalui alur, analitik log Microsoft mendukung kebijakan audit operasi dari server Azure SQL
```powershell
Get-AzSqlServer -ResourceGroupName "ResourceGroup01" -ServerName "Server01" | Set-AzSqlServerMSSupportAudit -LogAnalyticsTargetState Disabled
```

### Contoh 8: Nonaktifkan pengiriman catatan audit operasi dukungan Microsoft dari server Azure SQL ke penyimpanan blob, dan aktifkan mengirimnya ke analitik log.
```powershell
Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -LogAnalyticsTargetState Enabled -WorkspaceResourceId "/subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/viruela2" -BlobStorageTargetState Disabled
```

### Contoh 9: Aktifkan pengiriman catatan audit operasi dukungan Microsoft dari server Azure SQL ke penyimpanan blob, pusat aktivitas, dan analitik log.
```powershell
Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/7fe3301d-31d3-4668-af5e-211a890ba6e3/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage" -EventHubTargetState Enabled -EventHubName "EventHubName" -EventHubAuthorizationRuleResourceId "EventHubAuthorizationRuleResourceId" -LogAnalyticsTargetState Enabled  -WorkspaceResourceId "/subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/viruela2"
```

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -BlobStorageTargetState
Menunjukkan apakah penyimpanan blob adalah tujuan untuk catatan audit operasi dukungan Microsoft.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventHubAuthorizationRuleResourceId
Id sumber daya untuk aturan otorisasi hub peristiwa

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

### -EventHubName
Nama event hub. Jika tidak ada yang ditentukan saat menyediakan EventHubAuthorizationRuleResourceId, hub peristiwa default akan dipilih.

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

### -EventHubTargetState
Menunjukkan apakah hub peristiwa adalah tujuan untuk catatan audit operasi dukungan Microsoft.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogAnalyticsTargetState
Menunjukkan apakah analitik log adalah tujuan untuk catatan audit operasi dukungan Microsoft.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Menentukan apakah akan menghasilkan kebijakan audit operasi dukungan Microsoft pada akhir eksekusi cmdlet

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
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ServerParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
SQL nama server.

```yaml
Type: System.String
Parameter Sets: ServerParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerObject
Objek server untuk mengelola kebijakan audit operasi dukungan Microsoft-nya.

```yaml
Type: Microsoft.Azure.Commands.Sql.Server.Model.AzureSqlServerModel
Parameter Sets: ServerObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageAccountResourceId
Id sumber daya akun penyimpanan

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

### -WorkspaceResourceId
ID ruang kerja (ID sumber daya ruang kerja Analitik Log) untuk ruang kerja Analitik Log tempat Anda ingin mengirim Log Audit operasi dukungan Microsoft. Contoh: /subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/viruela2

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### System.String

### Microsoft.Azure.Commands.Sql.Server.Model.AzureSqlServerModel

### System.Guid

### System.Nullable'1[[System.UInt32, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### Microsoft.Azure.Commands.Sql.Auditing.Model.ServerDevOpsAuditModel

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
