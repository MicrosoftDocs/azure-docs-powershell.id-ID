---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azresourcemanagementprivatelink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzResourceManagementPrivateLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzResourceManagementPrivateLink.md
ms.openlocfilehash: f87518a9d0389710a7c7e2133eb3cfefbf09bfa8
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145549929"
---
# New-AzResourceManagementPrivateLink

## SYNOPSIS
Membuat Private Link Azure Resource Management

## SYNTAX

```
New-AzResourceManagementPrivateLink [[-ResourceGroupName] <String>] [-Name] <String> [-Location] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzResourceManagementPrivateLink membuat tautan privat manajemen sumber daya tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzResourceManagementPrivateLink -ResourceGroupName PrivateLinkTestRG -Name NewPL


Id                         : /subscriptions/aeb49941-36c3-4e7c-9ffd-16ba89d33ec4/resourceGroups/PrivateLinkTestRG/provi
                             ders/Microsoft.Authorization/resourceManagementPrivateLinks/NewPL
Type                       : Microsoft.Authorization/resourceManagementPrivateLinks
Name                       : NewPL
Location                   : centralus
PrivateEndpointConnections : {}
```

Buat tautan privat pengelolaan sumber daya.

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

### -Lokasi
Lokasi tautan privat.

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

### -Name
Nama tautan privat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PrivateLinkName

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
Parameter Sets: (All)
Aliases:

Required: False
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

### Microsoft.Azure.Commands.Resources.Models.PrivateLinks.PSResourceManagementPrivateLink

## NOTES

## RELATED LINKS

[Remove-AzResourceManagementPrivateLink](./Remove-AzResourceManagementPrivateLink.md)
 [Get-AzResourceManagementPrivateLink](./Get-AzResourceManagementPrivateLink.md)
