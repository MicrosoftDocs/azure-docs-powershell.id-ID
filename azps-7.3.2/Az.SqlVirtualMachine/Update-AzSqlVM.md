---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SqlVirtualMachine.dll-Help.xml
Module Name: Az.SqlVirtualMachine
online version: https://docs.microsoft.com/powershell/module/az.sqlvirtualmachine/update-azsqlvm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SqlVirtualMachine/SqlVirtualMachine/help/Update-AzSqlVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SqlVirtualMachine/SqlVirtualMachine/help/Update-AzSqlVM.md
ms.openlocfilehash: 7c64b10e2dda7cde54eac62adf0f7fdf18fe3139
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142207081"
---
# Update-AzSqlVM

## SYNOPSIS
Memperbarui mesin virtual sql.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.sqlvirtualmachine/update-azsqlvm) untuk informasi terbaru.

## SYNTAX

### NameParamaterList (Default)
```
Update-AzSqlVM [-ResourceGroupName] <String> [-Name] <String> [-LicenseType <String>] [-Offer <String>]
 [-Sku <String>] [-SqlManagementType <String>] [-Tag <Hashtable>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameInputObject
```
Update-AzSqlVM [-ResourceGroupName] <String> [-Name] <String> [-InputObject] <AzureSqlVMModel> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdParamaterList
```
Update-AzSqlVM [-LicenseType <String>] [-Offer <String>] [-Sku <String>] [-SqlManagementType <String>]
 [-Tag <Hashtable>] [-ResourceId] <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ResourceIdInputObject
```
Update-AzSqlVM [-InputObject] <AzureSqlVMModel> [-ResourceId] <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Update-AzSqlVM memperbarui mesin virtual sql.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $tags = @{'key'='value'}
PS C:\> $vm = Update-AzSqlVM -InputObject $vm -Tags $tags
PS C:\> $group.Tags
Name                           Value
----                           -----
key                            value
```

Memperbarui tag mesin virtual sql.

### Contoh 2

Memperbarui mesin virtual sql. (autogenerasi)

<!-- Aladdin Generated Example -->
```powershell
Update-AzSqlVM -Name AgListener01 -ResourceGroupName myresourcegroup -SqlManagementType <String>
```

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

### -InputObject
SQL objek mesin virtual.

```yaml
Type: Microsoft.Azure.Commands.SqlVirtualMachine.SqlVirtualMachine.Model.AzureSqlVMModel
Parameter Sets: NameInputObject, ResourceIdInputObject
Aliases: SqlVM

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LicenseType
SQL tipe lisensi mesin virtual.

```yaml
Type: System.String
Parameter Sets: NameParamaterList, ResourceIdParamaterList
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
SQL nama mesin virtual.

```yaml
Type: System.String
Parameter Sets: NameParamaterList, NameInputObject
Aliases: SqlVMName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Penawaran
SQL penawaran mesin virtual.

```yaml
Type: System.String
Parameter Sets: NameParamaterList, ResourceIdParamaterList
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
Parameter Sets: NameParamaterList, NameInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
SQL id sumber daya mesin virtual.

```yaml
Type: System.String
Parameter Sets: ResourceIdParamaterList, ResourceIdInputObject
Aliases: SqlVMId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
SQL tipe edisi mesin virtual.

```yaml
Type: System.String
Parameter Sets: NameParamaterList, ResourceIdParamaterList
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlManagementType
SQL tipe manajemen mesin virtual.

```yaml
Type: System.String
Parameter Sets: NameParamaterList, ResourceIdParamaterList
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag yang akan dikaitkan dengan mesin virtual SQL

```yaml
Type: System.Collections.Hashtable
Parameter Sets: NameParamaterList, ResourceIdParamaterList
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

### Microsoft.Azure.Commands.SqlVirtualMachine.SqlVirtualMachine.Model.AzureSqlVMModel

## OUTPUTS

### Microsoft.Azure.Commands.SqlVirtualMachine.SqlVirtualMachine.Model.AzureSqlVMModel

## CATATAN

## RELATED LINKS
