---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/set-azsynapsesqlauditsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseSqlAuditSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseSqlAuditSetting.md
ms.openlocfilehash: 90ff283337dccf2e27cd3510857293ed4d4b74ff
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136550165"
---
# Set-AzSynapseSqlAuditSetting

## SYNOPSIS
Mengubah pengaturan audit Ruang Kerja Analitik Azure Synapse.

## SYNTAX

### WorkspaceParameterSet (Default)
```
Set-AzSynapseSqlAuditSetting [-AuditActionGroup <AuditActionGroups[]>] [-PredicateExpression <String>]
 [-StorageKeyType <String>] [-RetentionInDays <UInt32>] [-BlobStorageTargetState <String>]
 [-StorageAccountResourceId <String>] [-EventHubTargetState <String>] [-EventHubName <String>]
 [-EventHubAuthorizationRuleResourceId <String>] [-LogAnalyticsTargetState <String>]
 [-WorkspaceResourceId <String>] [-PassThru] [[-ResourceGroupName] <String>] [-WorkspaceName] <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WorkspaceObjectParameterSet
```
Set-AzSynapseSqlAuditSetting [-AuditActionGroup <AuditActionGroups[]>] [-PredicateExpression <String>]
 [-StorageKeyType <String>] [-RetentionInDays <UInt32>] [-BlobStorageTargetState <String>]
 [-StorageAccountResourceId <String>] [-EventHubTargetState <String>] [-EventHubName <String>]
 [-EventHubAuthorizationRuleResourceId <String>] [-LogAnalyticsTargetState <String>]
 [-WorkspaceResourceId <String>] [-PassThru] -WorkspaceObject <PSSynapseWorkspace> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WorkspaceResourceIdParameterSetName
```
Set-AzSynapseSqlAuditSetting [-AuditActionGroup <AuditActionGroups[]>] [-PredicateExpression <String>]
 [-StorageKeyType <String>] [-RetentionInDays <UInt32>] [-BlobStorageTargetState <String>]
 [-StorageAccountResourceId <String>] [-EventHubTargetState <String>] [-EventHubName <String>]
 [-EventHubAuthorizationRuleResourceId <String>] [-LogAnalyticsTargetState <String>]
 [-WorkspaceResourceId <String>] [-PassThru] -ResourceId <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSynapseSqlAuditSetting** mengubah pengaturan audit Ruang Kerja Analitik Azure Synapse.
Ketika penyimpanan blob adalah tujuan untuk log audit, tentukan parameter *StorageAccountResourceId* untuk menentukan akun penyimpanan bagi log audit dan parameter *StorageKeyType* untuk menentukan kunci penyimpanan. Anda juga bisa menentukan penyimpanan untuk log audit dengan mengatur nilai parameter *RetentionInDays* untuk menentukan periode untuk log audit.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Set-AzSynapseSqlAuditSetting -WorkspaceName ContosoWorkspace -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage" -StorageKeyType Primary
```

Mengaktifkan kebijakan pengauditan penyimpanan blob dari Ruang Kerja Analitik Azure Synapse yang bernama ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> Set-AzSynapseSqlAuditSetting -WorkspaceName ContosoWorkspace -BlobStorageTargetState Disabled
```

Menonaktifkan kebijakan pengauditan penyimpanan blob dari Azure Synapse Analytics Workspace bernama ContosoWorkspace.

### Contoh 3
```powershell
PS C:\> Set-AzSynapseSqlAuditSetting -WorkspaceName ContosoWorkspace -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage" -StorageKeyType Primary -PredicateExpression "statement <> 'select 1'"
```

Mengaktifkan kebijakan pengauditan penyimpanan blob dari Ruang Kerja Analitik Azure Synapse yang bernama ContosoWorkspace dengan pemfilteran tingkat lanjut menggunakan predikat SQL T.

### Contoh 4
```powershell
PS C:\> Set-AzSynapseSqlAuditSetting -WorkspaceName ContosoWorkspace -PredicateExpression ""
```

Hapus pengaturan pemfilteran tingkat lanjut dari kebijakan audit Ruang Kerja Analitik Azure Synapse yang bernama ContosoWorkspace.

### Contoh 5
```powershell
PS C:\>Set-AzSynapseSqlAuditSetting -WorkspaceName ContosoWorkspace -EventHubTargetState Enabled -EventHubName "EventHubName" -EventHubAuthorizationRuleResourceId "EventHubAuthorizationRuleResourceId"
```

Aktifkan kebijakan pengauditan hub kejadian dari Ruang Kerja Analitik Azure Synapse yang bernama ContosoWorkspace.

### Contoh 6
```powershell
PS C:\>Set-AzSynapseSqlAuditSetting -WorkspaceName ContosoWorkspace -EventHubTargetState Disabled
```

Nonaktifkan kebijakan pengauditan hub kejadian ruang kerja Analitik Azure Synapse yang bernama ContosoWorkspace.

### Contoh 7
```powershell
PS C:\>Set-AzSynapseSqlAuditSetting -WorkspaceName ContosoWorkspace -LogAnalyticsTargetState Enabled -WorkspaceResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/myworkspace"
```

Aktifkan kebijakan pengauditan analitik log dari Ruang Kerja Analitik Azure Synapse yang bernama ContosoWorkspace.

### Contoh 8
```powershell
PS C:\>Set-AzSynapseSqlAuditSetting -WorkspaceName ContosoWorkspace -LogAnalyticsTargetState Disabled
```

Menonaktifkan kebijakan pengauditan analitik log dari Ruang Kerja Analitik Azure Synapse yang bernama ContosoWorkspace.

### Contoh 9
```powershell
PS C:\> Get-AzSynapseWorkspace -Name ContosoWorkspace | Set-AzSynapseSqlAuditSetting -BlobStorageTargetState Disabled
```

Menonaktifkan kebijakan pengauditan penyimpanan blob dari Ruang Kerja Analitik Azure Synapse yang bernama ContosoWorkspace melalui pipeline.

### Contoh 10
```powershell
PS C:\>Set-AzSynapseSqlAuditSetting -WorkspaceName ContosoWorkspace -LogAnalyticsTargetState Enabled -WorkspaceResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/myworkspace" -BlobStorageTargetState Disabled
```

 Nonaktifkan pengiriman catatan audit ruang kerja Analitik Azure Synapse ke penyimpanan blob, dan aktifkan pengirimannya ke analitik log.

### Contoh 11
```powershell
PS C:\>Set-AzSynapseSqlAuditSetting -WorkspaceName ContosoWorkspace -BlobStorageTargetState Enabled -StorageAccountResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/resourcegroup01/providers/Microsoft.Storage/storageAccounts/mystorage" -EventHubTargetState Enabled -EventHubName "EventHubName" -EventHubAuthorizationRuleResourceId "EventHubAuthorizationRuleResourceId" -LogAnalyticsTargetState Enabled  -WorkspaceResourceId "/subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/viruela2"
```

Aktifkan pengiriman catatan audit ruang kerja Analitik Azure Synapse ke penyimpanan blob, hub kejadian, dan analitik log.

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

### -AuditActionGroup
Kumpulan grup tindakan yang disarankan untuk digunakan adalah kombinasi berikut ini, tindakan ini akan mengaudit semua kueri dan prosedur tersimpan yang dijalankan terhadap database, serta berhasil dan gagal masuk:



"BATCH_COMPLETED_GROUP",

"SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP",

"FAILED_DATABASE_AUTHENTICATION_GROUP"

Kombinasi di atas juga merupakan kumpulan yang dikonfigurasi secara default.
Grup ini mencakup SQL pernyataan bisnis dan prosedur tersimpan yang dijalankan terhadap database, dan tidak boleh digunakan dalam kombinasi dengan grup lain karena ini akan menghasilkan log audit duplikat.

Untuk informasi selengkapnya, lihat https://docs.microsoft.com/sql/relational-databases/security/auditing/sql-server-audit-action-groups-and-actions#database-level-audit-action-groups .

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.Auditing.AuditActionGroups[]
Parameter Sets: (All)
Aliases:
Accepted values: BATCH_STARTED_GROUP, BATCH_COMPLETED_GROUP, APPLICATION_ROLE_CHANGE_PASSWORD_GROUP, BACKUP_RESTORE_GROUP, DATABASE_LOGOUT_GROUP, DATABASE_OBJECT_CHANGE_GROUP, DATABASE_OBJECT_OWNERSHIP_CHANGE_GROUP, DATABASE_OBJECT_PERMISSION_CHANGE_GROUP, DATABASE_OPERATION_GROUP, DATABASE_PERMISSION_CHANGE_GROUP, DATABASE_PRINCIPAL_CHANGE_GROUP, DATABASE_PRINCIPAL_IMPERSONATION_GROUP, DATABASE_ROLE_MEMBER_CHANGE_GROUP, FAILED_DATABASE_AUTHENTICATION_GROUP, SCHEMA_OBJECT_ACCESS_GROUP, SCHEMA_OBJECT_CHANGE_GROUP, SCHEMA_OBJECT_OWNERSHIP_CHANGE_GROUP, SCHEMA_OBJECT_PERMISSION_CHANGE_GROUP, SUCCESSFUL_DATABASE_AUTHENTICATION_GROUP, USER_CHANGE_PASSWORD_GROUP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlobStorageTargetState
Menunjukkan apakah penyimpanan blob adalah tujuan untuk catatan audit.

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
Menunjukkan apakah hub kejadian adalah tujuan untuk catatan audit.

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
Menunjukkan apakah analitik log adalah tujuan untuk catatan audit.

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
Cmdlet ini tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, maka true akan dikembalikan jika berhasil.

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

### -PredicateExpression
Predikat T-SQL (klausa WHERE) yang digunakan untuk memfilter log audit.

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: WorkspaceParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: WorkspaceResourceIdParameterSetName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionInDays
Jumlah hari penyimpanan untuk log audit.

```yaml
Type: System.Nullable`1[System.UInt32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -StorageKeyType
Menentukan kunci akses penyimpanan mana yang akan digunakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Primary, Secondary

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: WorkspaceParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
objek input ruang kerja, biasanya melewati saluran.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: WorkspaceObjectParameterSet
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorkspaceResourceId
ID ruang kerja (ID sumber daya dari ruang kerja Analitik Log) untuk ruang kerja Analitik Log yang ingin Anda kirimi Log Audit. Contoh: /subscriptions/4b9e8510-67ab-4e9a-95a9-e2f1e570ea9c/resourceGroups/insights-integration/providers/Microsoft.OperationalInsights/workspaces/vir dropbox2

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.WorkspaceAuditModel

## CATATAN

## RELATED LINKS
