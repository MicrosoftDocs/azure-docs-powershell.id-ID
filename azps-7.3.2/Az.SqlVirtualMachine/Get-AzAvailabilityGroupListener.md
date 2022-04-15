---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SqlVirtualMachine.dll-Help.xml
Module Name: Az.SqlVirtualMachine
online version: https://docs.microsoft.com/powershell/module/az.sqlvirtualmachine/get-azavailabilitygrouplistener
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SqlVirtualMachine/SqlVirtualMachine/help/Get-AzAvailabilityGroupListener.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SqlVirtualMachine/SqlVirtualMachine/help/Get-AzAvailabilityGroupListener.md
ms.openlocfilehash: 21f0ef706a68e6653d9c307b0508415c302c4bc9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142399067"
---
# Get-AzAvailabilityGroupListener

## SYNOPSIS
Dapatkan satu atau beberapa Pendengar Grup Ketersediaan dalam grup Mesin Virtual SQL.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.sqlvirtualmachine/get-azavailabilitygrouplistener) untuk informasi terbaru.

## SYNTAX

### Nama (Default)
```
Get-AzAvailabilityGroupListener [[-Name] <String>] [-ResourceGroupName] <String> [-SqlVMGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SqlVmGroupObject
```
Get-AzAvailabilityGroupListener [[-Name] <String>] [-SqlVMGroupObject] <AzureSqlVMGroupModel>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceId
```
Get-AzAvailabilityGroupListener [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Get-AzAvailabilityGroupListener mendapatkan satu atau beberapa Pendengar Grup Ketersediaan dari SQL Grup Mesin Virtual.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzAvailabilityGroupListener -ResourceGroupName ResourceGroup01 -SqlVMGroupName SqlVmGroup01 -Name AgListener01
```

Nama ResourceGroupName GroupName AvailabilityGroupName
----         ----------------- ---------    ---------------------
AgListener01 ResourceGroup01 SqlVmGroup01 AvailabilityGroup01

Perintah ini mendapatkan informasi tentang Availability Group Listener AgListener01 di SQL Virtual Machine Group SqlVmGroup01 dan Resource Group ResourceGroup01.

### Contoh 2
```powershell
PS C:\> Get-AzAvailabilityGroupListener -ResourceGroupName ResourceGroup01 -SqlVMGroupName SqlVmGroup01
```

Nama ResourceGroupName GroupName AvailabilityGroupName
----         ----------------- ---------    ---------------------
AgListener01 ResourceGroup01 SqlVmGroup01 AvailabilityGroup01 AgListener02 ResourceGroup01 SqlVmGroup01 AvailabilityGroup01

Perintah ini mendapatkan informasi tentang semua Pendengar Grup Ketersediaan di SQL Grup Mesin Virtual SqlVmGroup01 dan Resource Group ResourceGroup01.

### Contoh 3
```powershell
PS C:\> $SqlVmGroupObject = Get-AzSqlVMGroup -ResourceGroupName ResourceGroup01 -SqlVMGroupName SqlVmGroup01
PS C:\> Get-AzAvailabilityGroupListener -Name AgListener01 -SqlVMGroupObject $SqlVmGroupObject
```

Nama ResourceGroupName GroupName AvailabilityGroupName
----         ----------------- ---------    ---------------------
AgListener01 ResourceGroup01 SqlVmGroup01 AvailabilityGroup01

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

### -Nama
Nama Pendengar Grup Ketersediaan.

```yaml
Type: System.String
Parameter Sets: Name, SqlVmGroupObject
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya Pendengar Grup Ketersediaan

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SqlVMGroupName
SQL nama grup mesin virtual.

```yaml
Type: System.String
Parameter Sets: Name
Aliases: GroupName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlVMGroupObject
SQL objek Grup mesin virtual.

```yaml
Type: Microsoft.Azure.Commands.SqlVirtualMachine.SqlVirtualMachine.Model.AzureSqlVMGroupModel
Parameter Sets: SqlVmGroupObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.SqlVirtualMachine.SqlVirtualMachine.Model.AzureSqlVMGroupModel

## OUTPUTS

### Microsoft.Azure.Commands.SqlVirtualMachine.SqlVirtualMachine.Model.AzureAvailabilityGroupListenerModel

## CATATAN

## RELATED LINKS
