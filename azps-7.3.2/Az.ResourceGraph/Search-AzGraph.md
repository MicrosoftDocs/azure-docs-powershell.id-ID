---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceGraph.dll-Help.xml
Module Name: Az.ResourceGraph
online version: https://docs.microsoft.com/powershell/module/az.resourcegraph/search-azgraph
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceGraph/ResourceGraph/help/Search-AzGraph.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceGraph/ResourceGraph/help/Search-AzGraph.md
ms.openlocfilehash: f92e086d898d406660cdc00f021a22202e2366ab
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142885798"
---
# Search-AzGraph

## SYNOPSIS
Kueri sumber daya yang dikelola oleh Azure Resource Manager.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resourcegraph/search-azgraph) untuk informasi terbaru.

## SYNTAX

### SubscriptionScopedQuery (Default)
```
Search-AzGraph [-Query] <String> [-Subscription <String[]>] [-First <Int32>] [-Skip <Int32>]
 [-SkipToken <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### TenantScopedQuery
```
Search-AzGraph [-Query] <String> [-ManagementGroup <String[]>] [-AllowPartialScope] [-First <Int32>]
 [-Skip <Int32>] [-SkipToken <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Pelajari selengkapnya tentang sintaks kueri di sini: https://aka.ms/resource-graph/learntoquery

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Search-AzGraph "project id, name, type, location, tags" -First 3


id         : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/Service-INT-a/providers/Microsoft.Compute/virtualMachineScaleSets/nt
name       : nt
type       : microsoft.compute/virtualmachinescalesets
location   : eastus
tags       : @{resourceType=Service Fabric; clusterName=gov-art-int-nt-a}
ResourceId : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/Service-INT-a/providers/Microsoft.Compute/virtualMachineScaleSets/nt

id         : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/Service-INT-a/providers/Microsoft.EventGrid/topics/egtopic-1
name       : egtopic-1
type       : microsoft.eventgrid/topics
location   : westus2
tags       :
ResourceId : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/Service-INT-a/providers/Microsoft.EventGrid/topics/egtopic-1
```

Kueri sumber daya sederhana yang meminta subset bidang sumber daya.

### Contoh 2
```powershell
PS C:\> Search-AzGraph "project id, name, type, location | where type =~ 'Microsoft.Compute/virtualMachines' | summarize count() by location | top 3 by count_"

location      count_
--------      ------
eastus            66
westcentralus     32
westus            26
```

Kueri kompleks tentang sumber daya yang menampilkan pemilihan bidang, pemfilteran dan ringkasan.

### Contoh 3
```powershell
PS C:\> $response = Search-AzGraph -Query "project id, name, type, location" -First 2
PS C:\> Search-AzGraph -Query "project id, name, type, location" -SkipToken $response.SkipToken


id         : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/test/providers/Microsoft.Network/networkInterfaces/17ni
name       : 17ni
type       : microsoft.network/networkinterfaces
location   : westeurope
ResourceId : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/test/providers/Microsoft.Network/networkInterfaces/17ni

id         : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/test/providers/Microsoft.Network/networkSecurityGroups/17nsg
name       : 17nsg
type       : microsoft.network/networksecuritygroups
location   : westeurope
ResourceId : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/test/providers/Microsoft.Network/networkSecurityGroups/17nsg
```

Kueri dengan token lompat yang lolos dari hasil kueri sebelumnya. Harap dicatat bahwa menyimpan id dalam hasil wajib untuk mendapatkan kembali token skip.

### Contoh 4
```powershell
PS C:\> Search-AzGraph -Query "project id, name, type, location, tags" -First 2 -ManagementGroup MyManagementGroupId -AllowPartialScope


id         : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/Service-INT-a/providers/Microsoft.Compute/virtualMachineScaleSets/nt
name       : nt
type       : microsoft.compute/virtualmachinescalesets
location   : eastus
tags       : @{resourceType=Service Fabric; clusterName=gov-art-int-nt-a}
ResourceId : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/Service-INT-a/providers/Microsoft.Compute/virtualMachineScaleSets/nt

id         : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/Service-INT-a/providers/Microsoft.EventGrid/topics/egtopic-1
name       : egtopic-1
type       : microsoft.eventgrid/topics
location   : westus2
tags       :
ResourceId : /subscriptions/1ef51df4-f8a9-4b69-9919-1ef51df4eff6/resourceGroups/Service-INT-a/providers/Microsoft.EventGrid/topics/egtopic-1
```

Kueri yang dicakup ke grup manajemen yang memungkinkan kueri berhasil dengan hasil lingkup parsial jika MyManagementGroupId memiliki lebih dari N langganan di bawahnya.
N adalah jumlah maksimum langganan yang dapat diproses oleh server.

## PARAMETERS

### -AllowPartialScope
Menunjukkan apakah kueri harus berhasil ketika hanya sebagian jumlah langganan di bawahnya yang dapat diproses oleh server

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TenantScopedQuery
Aliases:

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

### -ManagementGroup
Grup manajemen untuk menjalankan kueri terhadap.

```yaml
Type: System.String[]
Parameter Sets: TenantScopedQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query
kueri Resource Graph.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipToken
Token lompat untuk digunakan untuk mendapatkan halaman hasil berikutnya jika ada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Langganan
Langganan untuk menjalankan kueri.

```yaml
Type: System.String[]
Parameter Sets: SubscriptionScopedQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lewati
Mengabaikan objek N pertama lalu mendapatkan objek yang tersisa.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pertama
Jumlah maksimum objek yang akan dikembalikan. Nilai yang diperbolehkan: 1-1000.
Nilai defaultnya adalah 100.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

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

### Microsoft.Azure.Commands.ResourceGraph.Models.PSResourceGraphResponse'1[[System.Management.Automation.PSObject]]

## NOTES

## RELATED LINKS
