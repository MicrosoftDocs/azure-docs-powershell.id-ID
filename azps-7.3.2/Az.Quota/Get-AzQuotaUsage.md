---
external help file: ''
Module Name: Az.Quota
online version: https://docs.microsoft.com/powershell/module/az.quota/get-azquotausage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Get-AzQuotaUsage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Get-AzQuotaUsage.md
ms.openlocfilehash: 5fce43d0bf8b7f5233652bb5ea59f13dae56db6c
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140006894"
---
# Get-AzQuotaUsage

## SYNOPSIS
Dapatkan penggunaan sumber daya saat ini.

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
PS C:\> Get-AzQuotaUsage -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus" 

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

### Contoh 2: Dapatkan penggunaan sumber daya saat ini
```powershell
PS C:\> Get-AzQuotaUsage -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus" -Name "MinPublicIpInterNetworkPrefixLength"

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

### -Nama
Nama sumber daya untuk penyedia sumber daya tertentu.
Misalnya:
- Nama SKU untuk Microsoft.Compute
- SKU atau TotalLowPriorityCores untuk Microsoft.MachineLearningServices For Microsoft.Network PublicIPAddresses.

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

### -Lingkup
URI sumber daya Azure target.
Misalnya, `/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/qms-test/providers/Microsoft.Batch/batchAccounts/testAccount/`.
Ini adalah URI sumber daya Azure target untuk operasi GET Daftar.
Jika ditambahkan `{resourceName}` setelah `/quotas`, itu adalah URI sumber daya Azure target dalam operasi DAPATKAN untuk sumber daya tertentu.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.Api20210315Preview.ICurrentUsagesBase

## CATATAN

ALIAS

## RELATED LINKS

