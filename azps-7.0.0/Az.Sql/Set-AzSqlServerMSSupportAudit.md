---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 14814BF3-51AF-4E51-A8A6-661825BD88D1
online version: https://docs.microsoft.com/powershell/module/az.sql/Set-AzSqlServerMSSupportAudit
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlServerMSSupportAudit.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlServerMSSupportAudit.md
ms.openlocfilehash: 8563703bf54f86ad13e19397d2ad08f77f133d55
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136563094"
---
# Set-AzSqlServerMSSupportAudit

## SYNOPSIS
Mengubah pengaturan pengauditan operasi dukungan Microsoft untuk server Azure SQL.

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
Cmdlet **Set-AzSqlServerMSSupportAudit** mengubah pengaturan pengauditan operasi dukungan Microsoft dari server SQL Azure.
Untuk menggunakan cmdlet, gunakan parameter *ResourceGroupName* *dan ServerName* untuk mengidentifikasi server.
Ketika penyimpanan blob adalah tujuan untuk log audit, tentukan parameter *StorageAccountResourceId* untuk menentukan akun penyimpanan untuk log audit.

## EXAMPLES

### Contoh 1: Mengaktifkan kebijakan audit operasi dukungan microsoft penyimpanan blob dari server SQL Azure
```powershell
PS C:\>Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/7fe3301d-31d3-4668-af5e-211a890ba6e3/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage"
```

### Contoh 2: Menonaktifkan kebijakan audit operasi dukungan blob penyimpanan Microsoft atas server SQL Azure
```powershell
PS C:\>Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -BlobStorageTargetState Disabled
```

### Contoh 3: Mengaktifkan kebijakan pengauditan operasi dukungan Microsoft hub kejadian untuk server SQL Azure
```powershell
PS C:\>Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -EventHubTargetState Enabled -EventHubName "EventHubName" -EventHubAuthorizationRuleResourceId "EventHubAuthorizationRuleResourceId"
```

### Contoh 4: Menonaktifkan kebijakan pengauditan operasi operasi dukungan Microsoft hub kejadian untuk server SQL Azure
```powershell
PS C:\>Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -EventHubTargetState Disabled
```

### Contoh 5: Mengaktifkan analitik log yang mendukung operasi pengauditan kebijakan pengauditan oleh Microsoft SQL server
```powershell
PS C:\>Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -LogAnalyticsTargetState Enabled -WorkspaceResourceId "/subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/viruela2"
```

### Contoh 6: Menonaktifkan analitik log Yang mendukung operasi pengauditan kebijakan pengauditan oleh Microsoft SQL server
```powershell
PS C:\>Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -LogAnalyticsTargetState Disabled
```

### Contoh 7: Menonaktifkan, melalui pipeline, analitik log mendukung operasi pengauditan kebijakan pengauditan oleh Microsoft untuk server SQL Azure
```powershell
PS C:\>Get-AzSqlServer -ResourceGroupName "ResourceGroup01" -ServerName "Server01" | Set-AzSqlServerMSSupportAudit -LogAnalyticsTargetState Disabled
```

### Contoh 8: Menonaktifkan pengiriman catatan audit operasi dukungan Microsoft dari server SQL Azure ke penyimpanan blob, dan memungkinkan pengirimannya untuk membuat log analitik.
```powershell
PS C:\>Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -LogAnalyticsTargetState Enabled -WorkspaceResourceId "/subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/viruela2" -BlobStorageTargetState Disabled
```

### Contoh 9: Mengaktifkan pengiriman catatan audit operasi dukungan Microsoft dari server SQL Azure ke penyimpanan blob, hub kejadian, dan analitik log.
```powershell
PS C:\>Set-AzSqlServerMSSupportAudit -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/7fe3301d-31d3-4668-af5e-211a890ba6e3/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage" -EventHubTargetState Enabled -EventHubName "EventHubName" -EventHubAuthorizationRuleResourceId "EventHubAuthorizationRuleResourceId" -LogAnalyticsTargetState Enabled  -WorkspaceResourceId "/subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/viruela2"
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
Menunjukkan apakah penyimpanan blob adalah tujuan bagi catatan audit operasi dukungan Microsoft.

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
Id sumber daya untuk aturan otorisasi hub acara

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
Nama hub acara. Jika tidak ada yang ditentukan saat menyediakan EventHubAuthorizationRuleResourceId, hub kejadian default akan dipilih.

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
Menunjukkan apakah hub kejadian adalah tujuan bagi catatan audit operasi dukungan Microsoft.

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
Menunjukkan apakah analitik log adalah tujuan bagi catatan audit operasi dukungan Microsoft.

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
Menentukan apakah akan membuat output kebijakan pengauditan operasi dukungan Microsoft pada akhir eksekusi cmdlet

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
SQL server baru.

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
Objek server untuk mengelola kebijakan audit operasi dukungan Microsoft.

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
ID ruang kerja (ID sumber daya dari ruang kerja Analitik Log) untuk ruang kerja Analitik Log yang ingin Anda kirimi Log Audit operasi dukungan Microsoft. Contoh: /subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/vir dropbox2

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Sql.Server.Model.AzureSqlServerModel

### System.Guid

### System.Nullable'1[[System.UInt32, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### Microsoft.Azure.Commands.Sql.Auditing.Model.ServerDevOpsAuditModel

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
