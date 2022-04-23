---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/remove-azsqlinstancelink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Remove-AzSqlInstanceLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Remove-AzSqlInstanceLink.md
ms.openlocfilehash: eddeef848b51d9cd2860ecc2a83ff28c7b287cb4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143306927"
---
# Remove-AzSqlInstanceLink

## SYNOPSIS
Menghapus tautan instans.

## SYNTAX

### DeleteByNameParameterSet (Default)
```
Remove-AzSqlInstanceLink [-ResourceGroupName] <String> [-InstanceName] <String> [-Name] <String> [-Force]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DeleteByParentObjectParameterSet
```
Remove-AzSqlInstanceLink [-Name] <String> [-InstanceObject] <AzureSqlManagedInstanceModel> [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DeleteByInputObjectParameterSet
```
Remove-AzSqlInstanceLink [-InputObject] <AzureSqlManagedInstanceLinkModel> [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DeleteByResourceIdParameterSet
```
Remove-AzSqlInstanceLink [-ResourceId] <String> [-Force] [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzSqlInstanceLink** menjatuhkan tautan instans. Perintah ini dapat menyebabkan hilangnya data jika tautan dihilangkan dan LSN replika tidak disinkronkan dengan yang utama, sehingga pengguna harus mengonfirmasi perintah secara eksplisit ketika diminta, atau menggunakan parameter -Force.

## EXAMPLES

### Contoh 1: Hapus tautan instans
```powershell
PS C:\> Remove-AzSqlInstanceLink -ResourceGroupName "ResourceGroup01" -InstanceName "ManagedInstance01" -Name "Link01"
This operation may cause data loss if replica's last hardened LSN is not in sync with the primary. Are you sure you want to proceed?
[Y] Yes  [N] No  [?] Help (default is "Y"): Y
```

Perintah ini menghapus tautan instans "Link01" dari instans terkelola "ManagedInstance01".

### Contoh 2: Hapus tautan instans dengan bendera eksplisit -Force
```powershell
PS C:\> Remove-AzSqlInstanceLink -ResourceGroupName "ResourceGroup01" -InstanceName "ManagedInstance01" -Name "Link01" -Force
```

Perintah ini secara paksa menghapus tautan instans "Link01" dari instans terkelola "ManagedInstance01", mengabaikan peringatan kehilangan data.

### Contoh 3: Hapus tautan instans menurut pengidentifikasi sumber dayanya
```powershell
PS C:\> Remove-AzSqlInstanceLink -ResourceId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/resourcegroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01/distributedAvailabilityGroups/Link01"
This operation may cause data loss if replica's last hardened LSN is not in sync with the primary. Are you sure you want to proceed?
[Y] Yes  [N] No  [?] Help (default is "Y"): Y
```

Perintah ini menghapus tautan instans dengan ID sumber daya tertentu.

### Contoh 4: Hapus tautan instans menurut objek PowerShell-nya
```powershell
PS C:\> $managedInstanceLink = Get-AzSqlInstanceLink -ResourceGroupName "ResourceGroup01" -InstanceName "ManagedInstance01" -Name "Link01" 
PS C:\> Remove-AzSqlInstanceLink -InputObject $managedInstanceLink
This operation may cause data loss if replica's last hardened LSN is not in sync with the primary. Are you sure you want to proceed?
[Y] Yes  [N] No  [?] Help (default is "Y"): Y
```

Perintah ini menghapus tautan instans yang ditentukan oleh objek tautan instans.

### Contoh 5: Hapus tautan instans menurut objek instans induknya
```powershell
PS C:\> $instance = Get-AzSqlInstance -ResourceGroupName "ResourceGroup01" -Name "ManagedInstance01" 
PS C:\> Remove-AzSqlInstanceLink -InstanceObject $instance -Name "Link01"
This operation may cause data loss if replica's last hardened LSN is not in sync with the primary. Are you sure you want to proceed?
[Y] Yes  [N] No  [?] Help (default is "Y"): Y
```

Perintah ini menghapus tautan instans "Link01" dari instans terkelola yang ditentukan oleh objek instans.

### Contoh 6: Hapus tautan instans menggunakan parameter posisi
```powershell
PS C:\> Remove-AzSqlInstanceLink "ResourceGroup01" "ManagedInstance01" "Link01"
This operation may cause data loss if replica's last hardened LSN is not in sync with the primary. Are you sure you want to proceed?
[Y] Yes  [N] No  [?] Help (default is "Y"): Y
```

Perintah ini menghapus tautan instans "Link01" dari instans terkelola "ManagedInstance01" menggunakan parameter posisi.

### Contoh 7: Hapus semua tautan instans dari instans induknya dengan mempipa objek tautan
```powershell
PS C:\> $instance = Get-AzSqlInstance -ResourceGroupName "ResourceGroup01" -Name "ManagedInstance01" 
PS C:\> $instance | Get-AzSqlInstanceLink | Remove-AzSqlInstanceLink -Force
```

Perintah ini menghapus semua tautan instans dari instans terkelola "ManagedInstance01" .

### Contoh 8: Hapus tautan instans dengan bendera eksplisit -Force dan output objek tautan instans yang dihapus
```powershell
PS C:\> Remove-AzSqlInstanceLink -ResourceGroupName "ResourceGroup01" -InstanceName "ManagedInstance01" -Name "Link01" -Force -PassThru
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

Perintah ini menghapus tautan instans dari instans terkelola "ManagedInstance01" dan membuat output objek tautan instans yang dihapus.

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

### -Paksa
Lewati pesan konfirmasi untuk melakukan tindakan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: AllowDataLoss

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
Parameter Sets: DeleteByInputObjectParameterSet
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
Parameter Sets: DeleteByNameParameterSet
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
Parameter Sets: DeleteByParentObjectParameterSet
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
Parameter Sets: DeleteByNameParameterSet, DeleteByParentObjectParameterSet
Aliases: LinkName

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Menentukan apakah akan mengembalikan tautan instans yang dihapus.

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
Parameter Sets: DeleteByNameParameterSet
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
Parameter Sets: DeleteByResourceIdParameterSet
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

### Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel

### Microsoft.Azure.Commands.Sql.ManagedInstanceHybridLink.Model.AzureSqlManagedInstanceLinkModel

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ManagedInstanceHybridLink.Model.AzureSqlManagedInstanceLinkModel

## NOTES

## RELATED LINKS

[Get-AzSqlInstanceLink](./Get-AzSqlInstanceLink.md)

[New-AzSqlInstanceLink](./New-AzSqlInstanceLink.md)

[Update-AzSqlInstanceLink](./Update-AzSqlInstanceLink.md)
