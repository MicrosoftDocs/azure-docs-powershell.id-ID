---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/get-azconnectednetworkfunctionvendor
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkFunctionVendor.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkFunctionVendor.md
ms.openlocfilehash: f55f45ef129c91ea0896d1d306539249a6b51208
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145505926"
---
# Get-AzConnectedNetworkFunctionVendor

## SYNOPSIS
Mencantumkan semua informasi vendor dan sku yang tersedia.

## SYNTAX

```
Get-AzConnectedNetworkFunctionVendor [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua informasi vendor dan sku yang tersedia.

## EXAMPLES

### Contoh 1: Get-AzConnectedNetworkFunctionVendor
```powershell
PS C:\> Get-AzConnectedNetworkFunctionVendor

SkuList                                                                                         VendorName
-------                                                                                         ----------
{vendor-sku, vendor-sku1, vendor-sku2, vendor-sku3, vendor-sku4, vendor-sku4, vendor-sku5...}   myVendor
{vendor1-sku, vendor1-sku2}                                                                     myVendor1
{vendor2-sku1}                                                                                  myVendor2
```

Mendapatkan informasi tentang vendor dan sku mereka

### Contoh 2: Get-AzConnectedNetworkFunctionVendor melalui Id Langganan
```powershell
PS C:\> Get-AzConnectedNetworkFunctionVendor -SubscriptionId "xxxxx-00000-xxxxx-00000"

SkuList                                                                                         VendorName
-------                                                                                         ----------
{vendor1-sku, vendor1-sku2}                                                                     myVendor1
{vendor2-sku1}                                                                                  myVendor2
```

Mendapatkan informasi tentang vendor dan sku mereka dalam langganan tertentu.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.INetworkFunctionVendor

## NOTES

ALIAS

## RELATED LINKS

