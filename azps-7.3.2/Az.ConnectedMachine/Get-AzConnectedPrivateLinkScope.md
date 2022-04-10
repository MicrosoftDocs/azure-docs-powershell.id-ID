---
external help file: ''
Module Name: Az.ConnectedMachine
online version: https://docs.microsoft.com/powershell/module/az.connectedmachine/get-azconnectedprivatelinkscope
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Get-AzConnectedPrivateLinkScope.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Get-AzConnectedPrivateLinkScope.md
ms.openlocfilehash: c82dd3d901a3c3564dc3d6d06f6d200f7b72035a
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140557292"
---
# Get-AzConnectedPrivateLinkScope

## SYNOPSIS
Mengembalikan Azure Arc PrivateLinkScope.

## SYNTAX

### Daftar (Default)
```
Get-AzConnectedPrivateLinkScope [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzConnectedPrivateLinkScope -ResourceGroupName <String> -ScopeName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzConnectedPrivateLinkScope -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan Azure Arc PrivateLinkScope.

## EXAMPLES

### Contoh 1:  List all private link scopes in a resource group
```powershell
Get-AzConnectedPrivateLinkScope -ResourceGroupName $resourceGroupName
```

```output
Name              Location    PublicNetworkAccess ProvisioningState Tag
----              --------    ------------------- ----------------- ---
name1       eastus2euap Enabled             Succeeded     Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.PrivateLinkScopesResourceTags
name2       eastus2euap Disabled            Succeeded         Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.PrivateLinkScopesResourceTags
name3       eastus2euap Enabled             Succeeded         Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.PrivateLinkScopesResourceTags
```

Mencantumkan semua lingkup link privat dalam grup sumber daya tertentu

### Contoh 2: Dapatkan lingkup tautan privat dalam grup sumber daya menurut nama
```powershell
Get-AzConnectedPrivateLinkScope -ResourceGroupName $resourceGroupName -ScopeName $scopeName
```

```output
Name         Location    PublicNetworkAccess ProvisioningState Tag
----         --------    ------------------- ----------------- ---
name1        eastus2euap Enabled             Succeeded         Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.PrivateLinkScopesRes…
```

Mendapatkan lingkup link privat dalam grup sumber daya tertentu menurut nama

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScopeName
Nama sumber daya Azure Arc PrivateLinkScope.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IHybridComputePrivateLinkScope

## CATATAN

ALIAS

## RELATED LINKS

