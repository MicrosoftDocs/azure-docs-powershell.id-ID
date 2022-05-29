---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azprivatelinkassociation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzPrivateLinkAssociation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzPrivateLinkAssociation.md
ms.openlocfilehash: 4cacfd7163fc4f1c01c04c78865d12301f1d1654
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145639898"
---
# Remove-AzPrivateLinkAssociation

## SYNOPSIS
Menghapus asosiasi tautan privat azure tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/remove-azprivatelinkassociation) untuk informasi terbaru.

## SYNTAX

### DeletePLAOperation (Default)
```
Remove-AzPrivateLinkAssociation [-ManagementGroupId] <String> [-Name] <String> [-PassThru] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PrivateLinkAssociationObject
```
Remove-AzPrivateLinkAssociation [-PassThru] [-Force] -InputObject <PSResourceManagementPrivateLinkAssociation>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Remove-AzPrivateLinkAssociation menghapus asosiasi tautan privat manajemen sumber daya tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Remove-AzPrivateLinkAssociation -ManagementGroupId 24f15700-370c-45bc-86a7-aee1b0c4eb8a -Name 1d7942d1-288b-48de-8d0f-2d2aa8e03ad4


True
```

Menghapus asosiasi tautan privat tertentu.

### Contoh 2
```powershell
PS C:\> Get-AzPrivateLinkAssociation -ManagementGroupId 24f15700-370c-45bc-86a7-aee1b0c4eb8a -Name 1d7942d1-288b-48de-8d0f-2d2aa8e03ad4 | Remove-AzPrivateLinkAssociation -Force
```

Menghapus asosiasi tautan privat tertentu.

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

### -Force
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
Type: Microsoft.Azure.Commands.Resources.Models.PrivateLinks.PSResourceManagementPrivateLinkAssociation
Parameter Sets: PrivateLinkAssociationObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementGroupId
Id grup manajemen.

```yaml
Type: System.String
Parameter Sets: DeletePLAOperation
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Id asosiasi tautan privat.

```yaml
Type: System.String
Parameter Sets: DeletePLAOperation
Aliases: PrivateLinkAssociationId

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

### Tidak ada

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Get-AzPrivateLinkAssociation](./Get-AzPrivateLinkAssociation.md)
 [New-AzPrivateLinkAssociation](./New-AzPrivateLinkAssociation.md)
