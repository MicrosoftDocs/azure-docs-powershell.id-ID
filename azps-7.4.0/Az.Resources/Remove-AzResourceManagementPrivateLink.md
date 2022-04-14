---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azresourcemanagementprivatelink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzResourceManagementPrivateLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzResourceManagementPrivateLink.md
ms.openlocfilehash: 9a7abac29a1d344fdb4d5019dc45f989432580ac
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141990426"
---
# Remove-AzResourceManagementPrivateLink

## SYNOPSIS
Menghapus Private Link Resource Manangement.

## SYNTAX

### DeleteOperation (Default)
```
Remove-AzResourceManagementPrivateLink [-ResourceGroupName] <String> [-Name] <String> [-PassThru] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PrivateLinkObject
```
Remove-AzResourceManagementPrivateLink [-PassThru] [-Force] -InputObject <PSResourceManagementPrivateLink>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Remove-AzResourceManagementPrivateLink menghapus tautan pribadi manajemen sumber daya tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Remove-AzResourceManagementPrivateLink -ResourceGroupName PrivateLinkTestRG -Name NewPL
True
```

Hapus Private Link Manajemen Sumber Daya tertentu.

### Contoh 2
```powershell
PS C:\> Get-AzResourceManagementPrivateLink -ResourceGroupName PrivateLinkTestRG -Name NewPL | Remove-AzResourceManagementPrivateLink -Force
```

Hapus Private Link Manajemen Sumber Daya tertentu.

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
Jangan meminta konfirmasi.

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

### -InputObject
Objek asosiasi tautan privat.

```yaml
Type: Microsoft.Azure.Commands.Resources.Models.PrivateLinks.PSResourceManagementPrivateLink
Parameter Sets: PrivateLinkObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama tautan privat.

```yaml
Type: System.String
Parameter Sets: DeleteOperation
Aliases: PrivateLinkName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Jangan meminta konfirmasi.

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
Parameter Sets: DeleteOperation
Aliases:

Required: True
Position: 0
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

### Tidak

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[Get-AzResourceManagementPrivateLink](./Get-AzResourceManagementPrivateLink.md)
 [New-AzResourceManagementPrivateLink](./New-AzResourceManagementPrivateLink.md)
