---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azprivatelinkassociation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzPrivateLinkAssociation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzPrivateLinkAssociation.md
ms.openlocfilehash: 7719cc611e47f46afbbcb1142832bfb71493f768
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144670948"
---
# Get-AzPrivateLinkAssociation

## SYNOPSIS
Mendapatkan semua Asosiasi Private Link Azure Resource Management.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azprivatelinkassociation) untuk informasi terbaru.

## SYNTAX

```
Get-AzPrivateLinkAssociation [-ManagementGroupId] <String> [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzPrivateLinkAssociation mendapatkan semua tautan privat manajemen sumber daya di cakupan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\>  Get-AzPrivateLinkAssociation -ManagementGroupId fc096d27-0434-4460-a3ea-110df0422a2d | fl



Id         : /providers/Microsoft.Management/managementGroups/fc096d27-0434-4460-a3ea-110df0422a2d/providers/Microsoft.
             Authorization/privateLinkAssociations/7afcb623-ff23-591c-8cdd-57f5357711f4
Type       : Microsoft.Authorization/privateLinkAssociations
Name       : 7afcb623-ff23-591c-8cdd-57f5357711f4
Properties : {"privateLink":"/subscriptions/aeb49941-36c3-4e7c-9ffd-16ba89d33ec4/resourceGroups/nrp-validate/providers/
             Microsoft.Authorization/resourceManagementPrivateLinks/DeepDiveRMPL","publicNetworkAccess":"Enabled","tena
             ntID":"fc096d27-0434-4460-a3ea-110df0422a2d","scope":"/providers/Microsoft.Management/managementGroups/24f
             15700-370c-45bc-86a7-aee1b0c4eb8a"}

Id         : /providers/Microsoft.Management/managementGroups/fc096d27-0434-4460-a3ea-110df0422a2d/providers/Microsoft.
             Authorization/privateLinkAssociations/1d7942d1-288b-48de-8d0f-2d2aa8e03ad4
Type       : Microsoft.Authorization/privateLinkAssociations
Name       : 1d7942d1-288b-48de-8d0f-2d2aa8e03ad4
Properties : {"privateLink":"/subscriptions/aeb49941-36c3-4e7c-9ffd-16ba89d33ec4/resourceGroups/nrp-validate/providers/
             Microsoft.Authorization/resourceManagementPrivateLinks/DeepDiveRMPL","publicNetworkAc
             cess":"Enabled","tenantID":"fc096d27-0434-4460-a3ea-110df0422a2d","scope":"/providers/Microsoft.Management
             /managementGroups/fc096d27-0434-4460-a3ea-110df0422a2d"}
```

Dapatkan semua asosiasi tautan privat di cakupan grup manajemen.

### Contoh 2
```powershell
PS C:\>  Get-AzPrivateLinkAssociation -ManagementGroupId fc096d27-0434-4460-a3ea-110df0422a2d -Name 1d7942d1-288b-48de-8d0f-2d2aa8e03ad4 | fl



Id         : /providers/Microsoft.Management/managementGroups/fc096d27-0434-4460-a3ea-110df0422a2d/providers/Microsoft.
             Authorization/privateLinkAssociations/1d7942d1-288b-48de-8d0f-2d2aa8e03ad4
Type       : Microsoft.Authorization/privateLinkAssociations
Name       : 1d7942d1-288b-48de-8d0f-2d2aa8e03ad4
Properties : {"privateLink":"/subscriptions/aeb49941-36c3-4e7c-9ffd-16ba89d33ec4/resourceGroups/nrp-validate/providers/
             Microsoft.Authorization/resourceManagementPrivateLinks/DeepDiveRMPL","publicNetworkAc
             cess":"Enabled","tenantID":"fc096d27-0434-4460-a3ea-110df0422a2d","scope":"/providers/Microsoft.Management
             /managementGroups/fc096d27-0434-4460-a3ea-110df0422a2d"}
```

Dapatkan asosiasi tautan privat tertentu di cakupan grup manajemen.

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

### -ManagementGroupId
Id grup manajemen.

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

### -Name
Id asosiasi tautan privat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PrivateLinkAssociationId

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.PrivateLinks.PSResourceManagementPrivateLinkAssociation

## NOTES

## RELATED LINKS

[Remove-AzPrivateLinkAssociation](./Remove-AzPrivateLinkAssociation.md)
 [New-AzPrivateLinkAssociation](./New-AzPrivateLinkAssociation.md)
