---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SqlVirtualMachine.dll-Help.xml
Module Name: Az.SqlVirtualMachine
online version: https://docs.microsoft.com/en-us/powershell/module/az.sqlvirtualmachine/get-azsqlvmgroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/SqlVirtualMachine/SqlVirtualMachine/help/Get-AzSqlVMGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/SqlVirtualMachine/SqlVirtualMachine/help/Get-AzSqlVMGroup.md
ms.openlocfilehash: fc4a0624b6e5702c0ef0c836f0b6ac593c25dafe
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136010638"
---
# Get-AzSqlVMGroup

## SYNOPSIS
Mendapatkan satu atau beberapa grup mesin virtual sql.

## SINTAKS

### ResourceGroupOnly (Default)
```
Get-AzSqlVMGroup [[-ResourceGroupName] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### Nama
```
Get-AzSqlVMGroup [-ResourceGroupName] <String> [-Name] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceId
```
Get-AzSqlVMGroup [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet Get-AzSqlVMGroup mendapatkan satu atau beberapa grup mesin virtual sql.

## CONTOH

### Contoh 1
```powershell
PS C:\> Get-AzSqlVMGroup

Name       ResourceGroupName  Sku       Offer
----       -----------------  ---       -----
test-group ResourceGroup01    Developer SQL2017-WS2016
group1     ResourceGroup02    Developer SQL2017-WS2016
```

Perintah ini mendapatkan informasi tentang semua grup SQL virtual Azure di langganan saat ini.

### Contoh 2
```powershell
PS C:\> Get-AzSqlVMGroup -ResourceGroupName "ResourceGroup01"
Name       ResourceGroupName  Sku       Offer
----       -----------------  ---       -----
test-group ResourceGroup01    Developer SQL2017-WS2016
```

Perintah ini mendapatkan informasi tentang semua grup komputer virtual Azure SQL dalam langganan saat ini yang ditetapkan ke grup sumber daya ResourceGroup01.

### Contoh 3
```powershell
PS C:\> Get-AzSqlVMGroup -ResourceGroupName "ResourceGroup01" -Name "test-group"
Name       ResourceGroupName  Sku       Offer
----       -----------------  ---       -----
test-group ResourceGroup01    Developer SQL2017-WS2016
```

Perintah ini mendapatkan informasi tentang SQL mesin virtual "test-group" yang ditetapkan ke grup sumber daya ResourceGroup01.

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
SQL grup mesin virtual.

```yaml
Type: System.String
Parameter Sets: Name
Aliases: SqlVMGroupName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ResourceGroupOnly
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
SQL sumber daya grup mesin virtual.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases: SqlVMGroupId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.SqlVirtualMachine.SqlVirtualMachine.Model.AzureSqlVMGroupModel

## CATATAN

## LINK TERKAIT
