---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceGraph.dll-Help.xml
Module Name: Az.ResourceGraph
online version: https://docs.microsoft.com/powershell/module/az.resourcegraph/search-azgraph
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceGraph/ResourceGraph/help/Search-AzGraph.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceGraph/ResourceGraph/help/Search-AzGraph.md
ms.openlocfilehash: 21e56a52b44ed3655c3ba40bca56d32f3562feb8
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145532194"
---
# Search-AzGraph

## SYNOPSIS
Mengkueri sumber daya yang dikelola oleh Azure Resource Manager.

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
Search-AzGraph "project id, name, type, location, tags" -First 3
```

```output
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
Search-AzGraph "project id, name, type, location | where type =~ 'Microsoft.Compute/virtualMachines' | summarize count() by location | top 3 by count_"
```

```output
location      count_
--------      ------
eastus            66
westcentralus     32
westus            26
```

Kueri kompleks tentang sumber daya yang menampilkan pemilihan bidang, pemfilteran, dan ringkasan.

### Contoh: 3
```powershell
$response = Search-AzGraph -Query "project id, name, type, location" -First 2
Search-AzGraph -Query "project id, name, type, location" -SkipToken $response.SkipToken
```

```output
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

Kueri dengan token lewati yang diteruskan dari hasil kueri sebelumnya. Harap dicatat bahwa menyimpan id dalam hasil adalah wajib untuk mendapatkan kembali token lompati.

### Contoh 4
```powershell
Search-AzGraph -Query "project id, name, type, location, tags" -First 2 -ManagementGroup MyManagementGroupId -AllowPartialScope
```

```output
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

Kueri yang dilingkup ke grup manajemen yang memungkinkan kueri berhasil dengan hasil cakupan parsial jika MyManagementGroupId memiliki lebih dari langganan N di bawahnya.
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
Grup manajemen untuk menjalankan kueri.

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

### -Kueri
Resource Graph kueri.

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
Token lewati yang digunakan untuk mendapatkan halaman hasil berikutnya jika berlaku.

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

### -First
Jumlah maksimum objek yang akan dikembalikan. Nilai yang diizinkan: 1-1000.
Nilai default adalah 100.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ResourceGraph.Models.PSResourceGraphResponse'1[[System.Management.Automation.PSObject]]

## NOTES

## RELATED LINKS
