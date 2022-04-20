---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azresourcemanagementprivatelink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzResourceManagementPrivateLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzResourceManagementPrivateLink.md
ms.openlocfilehash: 8dd4ec0944562cee2530a7060c6f807007e6d5ad
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142674208"
---
# Get-AzResourceManagementPrivateLink

## SYNOPSIS
Mendapatkan Private Link Azure Resource Management

## SYNTAX

```
Get-AzResourceManagementPrivateLink [[-ResourceGroupName] <String>] [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzResourceManagementPrivateLink mendapatkan tautan pribadi manajemen sumber daya tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzResourceManagementPrivateLink -ResourceGroupName PrivateLinkTestRG -Name NewPL


Id                         : /subscriptions/aeb49941-36c3-4e7c-9ffd-16ba89d33ec4/resourceGroups/PrivateLinkTestRG/provi
                             ders/Microsoft.Authorization/resourceManagementPrivateLinks/NewPL
Type                       : Microsoft.Authorization/resourceManagementPrivateLinks
Name                       : NewPL
Location                   : centralus
PrivateEndpointConnections : {}
```

Dapatkan tautan privat manajemen sumber daya dengan koneksi titik akhir privat yang terkait dengannya.

### Contoh 2
```powershell
PS C:\> Get-AzResourceManagementPrivateLink


Id                         : /subscriptions/aeb49941-36c3-4e7c-9ffd-16ba89d33ec4/resourceGroups/PrivateLinkTestRG/provi
                             ders/Microsoft.Authorization/resourceManagementPrivateLinks/NewPL
Type                       : Microsoft.Authorization/resourceManagementPrivateLinks
Name                       : NewPL
Location                   : centralus
PrivateEndpointConnections : {}

Id                         : /subscriptions/aeb49941-36c3-4e7c-9ffd-16ba89d33ec4/resourceGroups/PrivateLinkTestRG/provi
                             ders/Microsoft.Authorization/resourceManagementPrivateLinks/NewPL2
Type                       : Microsoft.Authorization/resourceManagementPrivateLinks
Name                       : NewPL2
Location                   : centralus
PrivateEndpointConnections : {}
```

Mendapatkan semua tautan privat manajemen resoure di lingkup langganan.

### Contoh 3
```powershell
PS C:\> Get-AzResourceManagementPrivateLink -ResourceGroupName PrivateLinkTestRG


Id                         : /subscriptions/aeb49941-36c3-4e7c-9ffd-16ba89d33ec4/resourceGroups/PrivateLinkTestRG/provi
                             ders/Microsoft.Authorization/resourceManagementPrivateLinks/NewPL
Type                       : Microsoft.Authorization/resourceManagementPrivateLinks
Name                       : NewPL
Location                   : centralus
PrivateEndpointConnections : {}

Id                         : /subscriptions/aeb49941-36c3-4e7c-9ffd-16ba89d33ec4/resourceGroups/PrivateLinkTestRG/provi
                             ders/Microsoft.Authorization/resourceManagementPrivateLinks/NewPL2
Type                       : Microsoft.Authorization/resourceManagementPrivateLinks
Name                       : NewPL2
Location                   : centralus
PrivateEndpointConnections : {}
```

Mendapatkan semua tautan privat manajemen resoure di lingkup grup sumber daya.

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
Nama tautan privat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PrivateLinkName

Required: False
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.PrivateLinks.PSResourceManagementPrivateLink

## NOTES

## RELATED LINKS

[Remove-AzResourceManagementPrivateLink](./Remove-AzResourceManagementPrivateLink.md)
 [New-AzResourceManagementPrivateLink](./New-AzResourceManagementPrivateLink.md)
