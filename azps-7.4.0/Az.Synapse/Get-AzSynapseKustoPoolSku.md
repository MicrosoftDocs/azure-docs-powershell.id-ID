---
external help file: ''
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsekustopoolsku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKustoPoolSku.md
ms.openlocfilehash: edf9c0def297f1867934f641ae31e6f61c5a3fca
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144713200"
---
# Get-AzSynapseKustoPoolSku

## SYNOPSIS
Mencantumkan SKU yang memenuhi syarat untuk sumber daya Kumpulan Kusto.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.synapse/get-azsynapsekustopoolsku) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzSynapseKustoPoolSku [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzSynapseKustoPoolSku -KustoPoolName <String> -ResourceGroupName <String> -WorkspaceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan SKU yang memenuhi syarat untuk sumber daya Kumpulan Kusto.

## EXAMPLES

### Contoh 1: Mencantumkan SKU yang memenuhi syarat
```powershell
Get-AzSynapseKustoPoolSku
```

```output
Location             Name              ResourceType          Size
--------             ----              ------------          ----
{australiacentral}   Compute optimized workspaces/kustoPools Extra small
{australiacentral2}  Compute optimized workspaces/kustoPools Extra small
{australiaeast}      Compute optimized workspaces/kustoPools Extra small
{australiasoutheast} Compute optimized workspaces/kustoPools Extra small
{brazilsouth}        Compute optimized workspaces/kustoPools Extra small
...
```

Perintah di atas mencantumkan SKU yang memenuhi syarat.

### Contoh 2: Mencantumkan SKU yang memenuhi syarat untuk kumpulan kusto tertentu
```powershell
Get-AzSynapseKustoPoolSku -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testnewkustopool
```

```output
ResourceType
------------
Microsoft.Synapse/workspaces/kustoPools
Microsoft.Synapse/workspaces/kustoPools
Microsoft.Synapse/workspaces/kustoPools
Microsoft.Synapse/workspaces/kustoPools
Microsoft.Synapse/workspaces/kustoPools
Microsoft.Synapse/workspaces/kustoPools
```

Perintah di atas mencantumkan SKU yang memenuhi syarat untuk kumpulan kusto tertentu.

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

### -KustoPoolName
Nama kumpulan Kusto.

```yaml
Type: System.String
Parameter Sets: List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: List1
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

### -WorkspaceName
Nama ruang kerja

```yaml
Type: System.String
Parameter Sets: List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.Api20210601Preview.IAzureResourceSku

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.Api20210601Preview.ISkuDescription

## NOTES

ALIAS

## RELATED LINKS

