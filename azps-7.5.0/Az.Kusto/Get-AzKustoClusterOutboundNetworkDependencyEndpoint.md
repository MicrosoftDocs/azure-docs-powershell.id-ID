---
external help file: ''
Module Name: Az.Kusto
online version: https://docs.microsoft.com/powershell/module/az.kusto/get-azkustoclusteroutboundnetworkdependencyendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Kusto/help/Get-AzKustoClusterOutboundNetworkDependencyEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Kusto/help/Get-AzKustoClusterOutboundNetworkDependencyEndpoint.md
ms.openlocfilehash: 0ebc3f89280f42d92ebff76ee2647828b3cb58a8
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144216230"
---
# Get-AzKustoClusterOutboundNetworkDependencyEndpoint

## SYNOPSIS
Mendapatkan titik akhir jaringan dari semua dependensi keluar dari kluster Kusto

## SYNTAX

```
Get-AzKustoClusterOutboundNetworkDependencyEndpoint -ClusterName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan titik akhir jaringan dari semua dependensi keluar dari kluster Kusto

## EXAMPLES

### Contoh 1: Mencantumkan semua Kusto ManagedPrivateEndpoint dalam kluster
```powershell
Get-AzKustoClusterOutboundNetworkDependencyEndpoint -ClusterName "mycluster" -ResourceGroupName "testrg"
```

```output
Name                                     Type                                                          Etag
----                                     ----                                                          ----
mycluster/AzureActiveDirectory           Microsoft.Kusto/Clusters/OutboundNetworkDependenciesEndpoints
mycluster/AzureMonitor                   Microsoft.Kusto/Clusters/OutboundNetworkDependenciesEndpoints
mycluster/CertificateAuthority           Microsoft.Kusto/Clusters/OutboundNetworkDependenciesEndpoints
mycluster/AzureStorage                   Microsoft.Kusto/Clusters/OutboundNetworkDependenciesEndpoints
```

Perintah di atas mengembalikan semua Kusto OutboundNetworkDependenciesEndpoints di kluster "mycluster" yang ditemukan di grup sumber daya "testrg".

## PARAMETERS

### -ClusterName
Nama kluster Kusto.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Nama grup sumber daya yang berisi kluster Kusto.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Mendapatkan kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Kusto. Models.Api20220201.IOutboundNetworkDependenciesEndpoint

## NOTES

ALIAS

## RELATED LINKS

