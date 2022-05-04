---
external help file: ''
Module Name: Az.Quota
online version: https://docs.microsoft.com/powershell/module/az.quota/get-azquotausage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Get-AzQuotaUsage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Get-AzQuotaUsage.md
ms.openlocfilehash: 33252836969cc13277ca0d5a62acfa76d9fb3d45
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144606704"
---
# Get-AzQuotaUsage

## SYNOPSIS
Dapatkan penggunaan sumber daya saat ini.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.quota/get-azquotausage) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzQuotaUsage -Scope <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzQuotaUsage -Name <String> -Scope <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan penggunaan sumber daya saat ini.

## EXAMPLES

### Contoh 1: Mencantumkan penggunaan sumber daya saat ini
```powershell
Get-AzQuotaUsage -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus" 
```

```output
Name                                                ResourceGroupName UsageUsagesType UsageValue ETag
----                                                ----------------- --------------- ---------- ----
VirtualNetworks                                                                       0
StaticPublicIPAddresses                                                               0
NetworkSecurityGroups                                                                 0
PublicIPAddresses                                                                     0
CustomIpPrefixes                                                                      0
PublicIpPrefixes                                                                      0
NatGateways                                                                           0
NetworkInterfaces                                                                     0
PrivateEndpoints                                                                      0
PrivateEndpointRedirectMaps                                                           0
LoadBalancers                                                                         0
PrivateLinkServices                                                                   0
ApplicationGateways                                                                   0
RouteTables                                                                           0
RouteFilters                                                                          0
```

Perintah ini mencantumkan penggunaan sumber daya saat ini

### Contoh 2: Mendapatkan penggunaan sumber daya saat ini
```powershell
Get-AzQuotaUsage -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus" -Name "MinPublicIpInterNetworkPrefixLength"
```

```output
Name                                NameLocalizedValue        UsageUsagesType UsageValue ETag
----                                ------------------        --------------- ---------- ----
MinPublicIpInterNetworkPrefixLength Public IPv4 Prefix Length                 0
```

Perintah ini mencantumkan penggunaan sumber daya saat ini.

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

### -Name
Nama sumber daya untuk penyedia sumber daya tertentu.
Contohnya:
- Nama SKU untuk Microsoft.Compute
- SKU atau TotalLowPriorityCores untuk Microsoft.MachineLearningServices Untuk Microsoft.Network PublicIPAddresses.

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

### -Cakupan
URI sumber daya Azure target.
Contohnya:`/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/qms-test/providers/Microsoft.Batch/batchAccounts/testAccount/`
Ini adalah URI sumber daya Azure target untuk operasi Daftar GET.
`{resourceName}` Jika ditambahkan setelah `/quotas`, maka itu adalah URI sumber daya Azure target dalam operasi GET untuk sumber daya tertentu.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.Api20210315Preview.ICurrentUsagesBase

## NOTES

ALIAS

## RELATED LINKS

