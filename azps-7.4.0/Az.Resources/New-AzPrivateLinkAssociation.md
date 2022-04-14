---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azprivatelinkassociation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPrivateLinkAssociation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPrivateLinkAssociation.md
ms.openlocfilehash: 88f3d96230622e566f59c2bddaf033c2e8a491a1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141990450"
---
# New-AzPrivateLinkAssociation

## SYNOPSIS
Membuat Asosiasi Private Link Manajemen Sumber Daya Azure.

## SYNTAX

```
New-AzPrivateLinkAssociation [-ManagementGroupId] <String> [-Name] <String> [-PrivateLink] <String>
 [-PublicNetworkAccess] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzPrivateLinkAssociation membuat assokaisi tautan privat pada lingkup.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzPrivateLinkAssociation -ManagementGroupId fc096d27-0434-4460-a3ea-110df0422a2d -Name 1d7942d1-288b-48de-8d0f-2d2aa8e03ad4 | fl


Id         : /providers/Microsoft.Management/managementGroups/fc096d27-0434-4460-a3ea-110df0422a2d/providers/Microsoft.
             Authorization/privateLinkAssociations/1d7942d1-288b-48de-8d0f-2d2aa8e03ad4
Type       : Microsoft.Authorization/privateLinkAssociations
Name       : 1d7942d1-288b-48de-8d0f-2d2aa8e03ad4
Properties : {"privateLink":"/subscriptions/aeb49941-36c3-4e7c-9ffd-16ba89d33ec4/resourceGroups/nrp-validate/providers/
             Microsoft.Authorization/resourceManagementPrivateLinks/DeepDiveRMPL","publicNetworkAc
             cess":"Enabled","tenantID":"fc096d27-0434-4460-a3ea-110df0422a2d","scope":"/providers/Microsoft.Management
             /managementGroups/fc096d27-0434-4460-a3ea-110df0422a2d"}
```

Membuat kaitan link privat tertentu di lingkup grup manajemen.

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

### -Nama
Id asosiasi tautan privat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PrivateLinkAssociationId

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateLink
Nama tautan privat.

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

### -PublicNetworkAccess
Akses jaringan publik diaktifkan/dinonaktifkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
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

### Microsoft.Azure.Commands.Resources.Models.PrivateLinks.PSResourceManagementPrivateLinkAssociation

## CATATAN

## RELATED LINKS

[Remove-AzPrivateLinkAssociation](./Remove-AzPrivateLinkAssociation.md)
 [Get-AzPrivateLinkAssociation](./Get-AzPrivateLinkAssociation.md)