---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.diskpool/get-azdiskpoolresourcesku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolResourceSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolResourceSku.md
ms.openlocfilehash: 04845f72b1a292892858ced63bc7cd5bc115cff4
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136532012"
---
# Get-AzDiskPoolResourceSku

## SYNOPSIS
Mencantumkan sumber daya dan skus StoragePool yang tersedia di lokasi Azure.

## SYNTAX

```
Get-AzDiskPoolResourceSku -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan sumber daya dan skus StoragePool yang tersedia di lokasi Azure.

## EXAMPLES

### Contoh 1: Mencantumkan semua sumber daya dan sku di lokasi
```powershell
PS C:\> Get-AzDiskPoolResourceSku -Location AustraliaEast

ApiVersion Name        ResourceType Tier
---------- ----        ------------ ----
2021-08-01 Standard_S1 diskPools    Standard
2021-08-01 Premium_P1  diskPools    Premium
2021-08-01 Basic_B1    diskPools    Basic
```

Perintah mencantumkan semua sumber daya dan sku di suatu lokasi.

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

### -Lokasi
Lokasi sumber daya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IResourceSkuInfo

## CATATAN

ALIAS

## RELATED LINKS

