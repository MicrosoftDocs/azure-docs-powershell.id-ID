---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/new-azsqlservertrustgroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/New-AzSqlServerTrustGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/New-AzSqlServerTrustGroup.md
ms.openlocfilehash: 34ed6fc8734318a7120573d1e93c73f729416047
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142738036"
---
# New-AzSqlServerTrustGroup

## SYNOPSIS
Membuat atau memperbarui Grup Kepercayaan Server.

## SYNTAX

### GroupMemberObjectSet (Default)
```
New-AzSqlServerTrustGroup [-ResourceGroupName] <String> [-Location] <String> [-Name] <String>
 [-GroupMember] <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel]>
 [-TrustScope <System.Collections.Generic.List`1[System.String]>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### GroupMemberResourceIdSet
```
New-AzSqlServerTrustGroup [-ResourceGroupName] <String> [-Location] <String> [-Name] <String>
 [-GroupMemberResourceId] <System.Collections.Generic.List`1[System.String]>
 [-TrustScope <System.Collections.Generic.List`1[System.String]>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat Grup Kepercayaan Server baru dengan lokasi, anggota, lingkup kepercayaan, nama, dan grup sumber daya tertentu.

## EXAMPLES

### Contoh 1
```powershell
$managedInstanceList = @()
$mi = Get-AzSqlInstance -Name "ManagedInstance01" -ResourceGroupName "ResourceGroup01"
$managedInstanceList += $mi
$mi = Get-AzSqlInstance -Name "ManagedInstance02" -ResourceGroupName "ResourceGroup02"
$managedInstanceList += $mi
New-AzSqlServerTrustGroup -ResourceGroupName "ResourceGroup03" -Location "West Europe" -Name "ServerTrustGroup01" -GroupMember $managedInstanceList -TrustScope "GlobalTransactions"
```

Membuat Grup Kepercayaan Server baru di lokasi Eropa Barat dengan nama ServerTrustGroup01. Anggotanya adalah AzureSQL Managed Instances ManagedInstance01 dan ManagedInstance02. Lingkup kepercayaannya adalah GlobalTransactions dan grup sumber dayanya adalah ResourceGroup03.

### Contoh 2
```powershell
$mi1 = "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/managedInstances/ManagedInstance01"
$mi2 = "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup02/providers/Microsoft.Sql/managedInstances/ManagedInstance02"
New-AzSqlServerTrustGroup -ResourceGroupName "ResourceGroup03" -Location "West Europe" -Name "ServerTrustGroup01" -GroupMemberResourceId $mi1,$mi2 -TrustScope "GlobalTransactions"
```

Membuat Grup Kepercayaan Server baru di lokasi Eropa Barat dengan nama ServerTrustGroup01. Anggotanya adalah AzureSQL Managed Instances ManagedInstance01 dan ManagedInstance02, yang diberikan oleh id Sumber Dayanya. Lingkup kepercayaannya adalah GlobalTransactions dan grup sumber dayanya adalah ResourceGroup03.

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

### -GroupMember
Anggota grup Grup Kepercayaan Server untuk dibuat.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel]
Parameter Sets: GroupMemberObjectSet
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupMemberResourceId
Anggota grup Grup Kepercayaan Server untuk dibuat.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: GroupMemberResourceIdSet
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi Grup Kepercayaan Server untuk dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Grup Kepercayaan Server untuk dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrustScope
Lingkup kepercayaan Grup Kepercayaan Server untuk dibuat.

```yaml
Type: System.Collections.Generic.List`1[System.String]
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ServerTrustGroup.Model.AzureSqlServerTrustGroupModel

## NOTES

## RELATED LINKS
