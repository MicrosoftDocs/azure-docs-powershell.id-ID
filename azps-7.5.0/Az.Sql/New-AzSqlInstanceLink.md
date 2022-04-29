---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/new-azsqlinstancelink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/New-AzSqlInstanceLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/New-AzSqlInstanceLink.md
ms.openlocfilehash: 7ace1ccc77ea7b1e14eeccf6da90fb52eb24277b
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144223751"
---
# New-AzSqlInstanceLink

## SYNOPSIS
Membuat tautan instans baru.

## SYNTAX

### CreateByNameParameterSet (Default)
```
New-AzSqlInstanceLink [-ResourceGroupName] <String> [-InstanceName] <String> [-Name] <String>
 -PrimaryAvailabilityGroupName <String> -SecondaryAvailabilityGroupName <String> -TargetDatabase <String>
 -SourceEndpoint <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CreateByParentObjectParameterSet
```
New-AzSqlInstanceLink [-Name] <String> -PrimaryAvailabilityGroupName <String>
 -SecondaryAvailabilityGroupName <String> -TargetDatabase <String> -SourceEndpoint <String>
 [-InstanceObject] <AzureSqlManagedInstanceModel> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzSqlInstanceLink** membuat tautan Azure SQL Managed Instance dengan bergabung dengan grup ketersediaan terdistribusi pada SQL Server berdasarkan parameter yang dilewatkan.

## EXAMPLES

### Contoh 1: Membuat tautan instans baru
```powershell
PS C:\> New-AzSqlInstanceLink -ResourceGroupName "ResourceGroup01" -InstanceName "ManagedInstance01" -Name "Link01" -PrimaryAvailabilityGroupName "Link01PrimaryAG" -SecondaryAvailabilityGroupName "Link01SecondaryAG" -TargetDatabase "Database01" -SourceEndpoint "TCP://SERVER01:5022"      
ResourceGroupName              : ResourceGroup01
InstanceName                   : ManagedInstance01
Type                           : Microsoft.Sql/managedInstances/distributedAvailabilityGroups
Id                             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01/distributedAvailabilityGroups/Link01
Name                           : Link01
TargetDatabase                 : Database01
SourceEndpoint                 : TCP://SERVER01:5022
PrimaryAvailabilityGroupName   : Link01PrimaryAG
SecondaryAvailabilityGroupName : Link01SecondaryAG
ReplicationMode                : Async
DistributedAvailabilityGroupId : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SourceReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
TargetReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
LinkState                      : Copying
LastHardenedLsn                :
```

Perintah ini membuat tautan instans baru dengan nama "Link01".

### Contoh 2: Membuat tautan instans baru menggunakan objek instans
```powershell
PS C:\> $instance = Get-AzSqlInstance -ResourceGroupName "ResourceGroup01" -Name "ManagedInstance01"
PS C:\> New-AzSqlInstanceLink -InstanceObject $instance -Name "Link01" -PrimaryAvailabilityGroupName "Link01PrimaryAG" -SecondaryAvailabilityGroupName "Link01SecondaryAG" -TargetDatabase "Database01" -SourceEndpoint "TCP://SERVER01:5022"       
ResourceGroupName              : ResourceGroup01
InstanceName                   : ManagedInstance01
Type                           : Microsoft.Sql/managedInstances/distributedAvailabilityGroups
Id                             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01/distributedAvailabilityGroups/Link01
Name                           : Link01
TargetDatabase                 : Database01
SourceEndpoint                 : TCP://SERVER01:5022
PrimaryAvailabilityGroupName   : Link01PrimaryAG
SecondaryAvailabilityGroupName : Link01SecondaryAG
ReplicationMode                : Async
DistributedAvailabilityGroupId : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SourceReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
TargetReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
LinkState                      : Copying
LastHardenedLsn                :
```

Perintah ini membuat tautan instans baru menggunakan objek instans terkelola sebagai parameter.

### Contoh 3: Membuat tautan instans baru dengan mempipa objek instans
```powershell
PS C:\> $instance = Get-AzSqlInstance -ResourceGroupName "ResourceGroup01" -Name "ManagedInstance01"
PS C:\> $instance | New-AzSqlInstanceLink -Name "Link01" -PrimaryAvailabilityGroupName "Link01PrimaryAG" -SecondaryAvailabilityGroupName "Link01SecondaryAG" -TargetDatabase "Database01" -SourceEndpoint "TCP://SERVER01:5022"     
ResourceGroupName              : ResourceGroup01
InstanceName                   : ManagedInstance01
Type                           : Microsoft.Sql/managedInstances/distributedAvailabilityGroups
Id                             : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01/distributedAvailabilityGroups/Link01
Name                           : Link01
TargetDatabase                 : Database01
SourceEndpoint                 : TCP://SERVER01:5022
PrimaryAvailabilityGroupName   : Link01PrimaryAG
SecondaryAvailabilityGroupName : Link01SecondaryAG
ReplicationMode                : Async
DistributedAvailabilityGroupId : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SourceReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
TargetReplicaId                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
LinkState                      : Copying
LastHardenedLsn                :
```

Perintah ini membuat tautan instans baru dengan mempipa objek instans.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceName
Nama Azure SQL Managed Instance.

```yaml
Type: System.String
Parameter Sets: CreateByNameParameterSet
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
Parameter Sets: CreateByParentObjectParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama tautan instans.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LinkName

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryAvailabilityGroupName
Nama grup ketersediaan utama.

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: CreateByNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondaryAvailabilityGroupName
Nama grup ketersediaan sekunder.

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

### -SourceEndpoint
Adress IP titik akhir sumber.

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

### -TargetDatabase
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

### Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ManagedInstanceHybridLink.Model.AzureSqlManagedInstanceLinkModel

## NOTES

## RELATED LINKS

[Get-AzSqlInstanceLink](./Get-AzSqlInstanceLink.md)

[Update-AzSqlInstanceLink](./Update-AzSqlInstanceLink.md)

[Remove-AzSqlInstanceLink](./Remove-AzSqlInstanceLink.md)
