---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azmanagementgroup/
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzManagementGroupHierarchySetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzManagementGroupHierarchySetting.md
ms.openlocfilehash: 325984998e6856f7d0c437856c8c0beea52f88bf
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145557856"
---
# Update-AzManagementGroupHierarchySetting

## SYNOPSIS
Memperbarui Pengaturan Hierarki di bawah penyewa saat ini

## SYNTAX

### GroupOperations (Default)
```
Update-AzManagementGroupHierarchySetting [-GroupName] <String> [-Authorization <Boolean>]
 [-DefaultManagementGroup <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ParentGroupObject
```
Update-AzManagementGroupHierarchySetting [-GroupName] <String> [-Authorization <Boolean>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Update-AzManagementGroupHierarchySetting memperbarui pengaturan hierarki di bawah penyewa saat ini. Memerlukan **Otorisasi** dan mengatur **DefaultManagementGroup** tempat grup baru dibuat dapat diperbarui.

## EXAMPLES

### Contoh 1: Memperbarui Pengaturan Hierarki untuk Persyaratan Otorisasi untuk Pembuatan Grup
```powershell
Update-AzManagementGroupHierarchySetting -GroupName c7a87cda-9a66-4920-b0f8-869baa04efe0 -Authorization True
```

```output
Id          : /providers/Microsoft.Management/managementGroups/c7a87cda-9a66-4920-b0f8-869baa04efe0/settings/default
Type        : Microsoft.Management/managementGroups/settings
Name        : default
TenantId    : 6b2064b9-34bd-46e6-9092-52f2dd5f7fc0
RequireAuthorizationForGroupCreation : true
DefaultManagementGroup :
```

### Contoh 2: Perbarui Pengaturan Hierarki tempat Grup Manajemen default grup baru ditempatkan di bawah
```powershell
Update-AzManagementGroupHierarchySetting -GroupName c7a87cda-9a66-4920-b0f8-869baa04efe0 -DefaultManagementGroup TestGroup
```

```output
Id          : /providers/Microsoft.Management/managementGroups/c7a87cda-9a66-4920-b0f8-869baa04efe0/settings/default
Type        : Microsoft.Management/managementGroups/settings
Name        : default
TenantId    : 6b2064b9-34bd-46e6-9092-52f2dd5f7fc0
RequireAuthorizationForGroupCreation : false
DefaultManagementGroup : TestGroup
```

### Contoh 3: Membuat hierarki Pengaturan
```powershell
Update-AzManagementGroupHierarchySetting -GroupName c7a87cda-9a66-4920-b0f8-869baa04efe0 -Authorization True -DefaultManagementGroup TestGroup
```

```output
Id          : /providers/Microsoft.Management/managementGroups/c7a87cda-9a66-4920-b0f8-869baa04efe0/settings/default
Type        : Microsoft.Management/managementGroups/settings
Name        : default
TenantId    : 6b2064b9-34bd-46e6-9092-52f2dd5f7fc0
RequireAuthorizationForGroupCreation : true
DefaultManagementGroup : TestGroup
```

## PARAMETERS

### -Otorisasi
Menunjukkan apakah akses RBAC diperlukan saat pembuatan grup di bawah Grup Manajemen akar. Benar berarti pengguna akan memerlukan tindakan Microsoft.Management/managementGroups/write pada Grup Manajemen akar. Pengaturan default adalah false.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: RequireAuthorizationForGroupCreation

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultManagementGroup
Perluas output untuk mencantumkan turunan grup manajemen

```yaml
Type: System.String
Parameter Sets: GroupOperations
Aliases: DefaultMG

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

### -GroupName
Id Grup Manajemen

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: GroupId

Required: True
Position: 0
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.ManagementGroups.PSHierarchySettings

### Microsoft.Azure.Commands.Resources.Models.ManagementGroups.PSHierarchySettings

## NOTES

## RELATED LINKS

## RELATED LINKS
