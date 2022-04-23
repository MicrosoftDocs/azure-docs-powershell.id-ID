---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/update-azsqlinstancelink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Update-AzSqlInstanceLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Update-AzSqlInstanceLink.md
ms.openlocfilehash: d757dc82770f7d4d855f59e8adf0896da4ea005c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143271449"
---
# Update-AzSqlInstanceLink

## SYNOPSIS
Memperbarui properti tautan instans.

## SYNTAX

### UpdateByNameParameterSet (Default)
```
Update-AzSqlInstanceLink [-ResourceGroupName] <String> [-InstanceName] <String> [-Name] <String>
 [-ReplicationMode] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UpdateByParentObjectParameterSet
```
Update-AzSqlInstanceLink [-Name] <String> [-ReplicationMode] <String>
 [-InstanceObject] <AzureSqlManagedInstanceModel> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### UpdateByInputObjectParameterSet
```
Update-AzSqlInstanceLink [[-ReplicationMode] <String>] [-InputObject] <AzureSqlManagedInstanceLinkModel>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateByResourceIdParameterSet
```
Update-AzSqlInstanceLink [-ReplicationMode] <String> [-ResourceId] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Update-AzSqlInstanceLink** memodifikasi properti tautan instans.

## EXAMPLES

### Contoh 1: Mengatur mode replikasi tautan instans ke Sinkronisasi
```powershell
PS C:\> Update-AzSqlInstanceLink -ResourceGroupName "ResourceGroup1" -InstanceName "ManagedInstance01" -Name "Link01" -ReplicationMode "Sync"
ResourceGroupName              : ResourceGroup01
InstanceName                   : ManagedInstance01
Type                           : Microsoft.Sql/managedInstances/distributedAvailabilityGroups
Id                             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01/distributedAvailabilityGroups/Link01
Name                           : Link01
TargetDatabase                 : Database01
SourceEndpoint                 : TCP://SERVER01:5022
PrimaryAvailabilityGroupName   :
SecondaryAvailabilityGroupName :
ReplicationMode                : Sync
DistributedAvailabilityGroupId : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SourceReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
TargetReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
LinkState                      : Copying
LastHardenedLsn                :
```

Perintah ini mengatur mode replikasi tautan instans ke "Sinkronkan".

### Contoh 2: Mengatur mode replikasi tautan instans ke Async
```powershell
PS C:\> Update-AzSqlInstanceLink -ResourceGroupName "ResourceGroup1" -InstanceName "ManagedInstance01" -Name "Link01" -ReplicationMode "Async"
ResourceGroupName              : ResourceGroup01
InstanceName                   : ManagedInstance01
Type                           : Microsoft.Sql/managedInstances/distributedAvailabilityGroups
Id                             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01/distributedAvailabilityGroups/Link01
Name                           : Link01
TargetDatabase                 : Database01
SourceEndpoint                 : TCP://SERVER01:5022
PrimaryAvailabilityGroupName   :
SecondaryAvailabilityGroupName :
ReplicationMode                : Async
DistributedAvailabilityGroupId : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SourceReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
TargetReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
LinkState                      : Copying
LastHardenedLsn                :
```

Perintah ini mengatur mode replikasi tautan instans ke "Aync".

### Contoh 3: Mengatur mode replikasi tautan instans menurut pengidentifikasi sumber dayanya
```powershell
PS C:\> Update-AzSqlInstanceLink -ResourceId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/resourcegroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01/distributedAvailabilityGroups/Link01" -ReplicationMode "Async"
ResourceGroupName              : ResourceGroup01
InstanceName                   : ManagedInstance01
Type                           : Microsoft.Sql/managedInstances/distributedAvailabilityGroups
Id                             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01/distributedAvailabilityGroups/Link01
Name                           : Link01
TargetDatabase                 : Database01
SourceEndpoint                 : TCP://SERVER01:5022
PrimaryAvailabilityGroupName   :
SecondaryAvailabilityGroupName :
ReplicationMode                : Async
DistributedAvailabilityGroupId : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SourceReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
TargetReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
LinkState                      : Copying
LastHardenedLsn                :
```

Perintah ini mengatur mode replikasi tautan instans ke "Sinkronkan" menurut pengidentifikasi sumber dayanya.

### Contoh 4: Atur mode replikasi tautan instans oleh objek PowerShell-nya
```powershell
PS C:\> $managedInstanceLink = Get-AzSqlInstanceLink -ResourceGroupName "ResourceGroup01" -InstanceName "ManagedInstance01" -Name "Link01" 
PS C:\> Update-AzSqlInstanceLink -InputObject $managedInstanceLink -ReplicationMode "Async"
ResourceGroupName              : ResourceGroup01
InstanceName                   : ManagedInstance01
Type                           : Microsoft.Sql/managedInstances/distributedAvailabilityGroups
Id                             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01/distributedAvailabilityGroups/Link01
Name                           : Link01
TargetDatabase                 : Database01
SourceEndpoint                 : TCP://SERVER01:5022
PrimaryAvailabilityGroupName   :
SecondaryAvailabilityGroupName :
ReplicationMode                : Async
DistributedAvailabilityGroupId : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SourceReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
TargetReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
LinkState                      : Copying
LastHardenedLsn                :
```

Perintah ini mengatur mode replikasi tautan instans ke "Async" menggunakan objek input.

### Contoh 5: Atur mode replikasi tautan instans dengan memutasi objeknya
```powershell
PS C:\> $managedInstanceLink = Get-AzSqlInstanceLink -ResourceGroupName "ResourceGroup01" -InstanceName "ManagedInstance01" -Name "Link01" 
PS C:\> $managedInstanceLink.ReplicationMode = "Async"
PS C:\> Update-AzSqlInstanceLink -InputObject $managedInstanceLink
ResourceGroupName              : ResourceGroup01
InstanceName                   : ManagedInstance01
Type                           : Microsoft.Sql/managedInstances/distributedAvailabilityGroups
Id                             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01/distributedAvailabilityGroups/Link01
Name                           : Link01
TargetDatabase                 : Database01
SourceEndpoint                 : TCP://SERVER01:5022
PrimaryAvailabilityGroupName   :
SecondaryAvailabilityGroupName :
ReplicationMode                : Async
DistributedAvailabilityGroupId : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SourceReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
TargetReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
LinkState                      : Copying
LastHardenedLsn                :
```

Perintah ini mengatur tautan instans menggunakan objek input.

### Contoh 6: Mengatur mode replikasi tautan instans oleh objek instans induknya
```powershell
PS C:\> $instance = Get-AzSqlInstance -ResourceGroupName "ResourceGroup01" -Name "ManagedInstance01" 
PS C:\> Update-AzSqlInstanceLink -InstanceObject $instance -Name "Link01" -ReplicationMode "Async"
ResourceGroupName              : ResourceGroup01
InstanceName                   : ManagedInstance01
Type                           : Microsoft.Sql/managedInstances/distributedAvailabilityGroups
Id                             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01/distributedAvailabilityGroups/Link01
Name                           : Link01
TargetDatabase                 : Database01
SourceEndpoint                 : TCP://SERVER01:5022
PrimaryAvailabilityGroupName   :
SecondaryAvailabilityGroupName :
ReplicationMode                : Async
DistributedAvailabilityGroupId : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SourceReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
TargetReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
LinkState                      : Copying
LastHardenedLsn                :
```

Perintah ini mengatur mode replikasi tautan instans ke "Async" menggunakan objek instans induk.

## PARAMETERS

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

### -InputObject
Objek input tautan instans.

```yaml
Type: Microsoft.Azure.Commands.Sql.ManagedInstanceHybridLink.Model.AzureSqlManagedInstanceLinkModel
Parameter Sets: UpdateByInputObjectParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InstanceName
Nama Azure SQL Managed Instance.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceObject
Objek input instans.

```yaml
Type: Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel
Parameter Sets: UpdateByParentObjectParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama tautan instans.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet, UpdateByParentObjectParameterSet
Aliases: LinkName

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationMode
Nilai mode replikasi.
Nilai yang memungkinkan termasuk 'Sinkronkan' dan 'Async'.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet, UpdateByParentObjectParameterSet, UpdateByResourceIdParameterSet
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: UpdateByInputObjectParameterSet
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya tautan instans.

```yaml
Type: System.String
Parameter Sets: UpdateByResourceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String

### Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel

### Microsoft.Azure.Commands.Sql.ManagedInstanceHybridLink.Model.AzureSqlManagedInstanceLinkModel

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ManagedInstanceHybridLink.Model.AzureSqlManagedInstanceLinkModel

## NOTES

## RELATED LINKS

[Get-AzSqlInstanceLink](./Get-AzSqlInstanceLink.md)

[New-AzSqlInstanceLink](./New-AzSqlInstanceLink.md)

[Remove-AzSqlInstanceLink](./Remove-AzSqlInstanceLink.md)
