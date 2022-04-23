---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azresourcemanagementprivatelink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzResourceManagementPrivateLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzResourceManagementPrivateLink.md
ms.openlocfilehash: f87518a9d0389710a7c7e2133eb3cfefbf09bfa8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143275373"
---
# New-AzResourceManagementPrivateLink

## SYNOPSIS
Membuat Private Link Manajemen Sumber Daya Azure

## SYNTAX

```
New-AzResourceManagementPrivateLink [[-ResourceGroupName] <String>] [-Name] <String> [-Location] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzResourceManagementPrivateLink membuat tautan pribadi manajemen sumber daya tertentu.

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

Buat tautan privat manajemen sumber daya.

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
Lokasi tautan pribadi.

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

### -Nama
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

### Microsoft.Azure.Commands.Resources.Models.PrivateLinks.PSResourceManagementPrivateLink

## NOTES

## RELATED LINKS

[Remove-AzResourceManagementPrivateLink](./Remove-AzResourceManagementPrivateLink.md)
 [Get-AzResourceManagementPrivateLink](./Get-AzResourceManagementPrivateLink.md)
