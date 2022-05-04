---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.diskpool/get-azdiskpoolresourcesku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolResourceSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolResourceSku.md
ms.openlocfilehash: dfc508c52a4cf9704331f229946c523303e0e61d
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144619269"
---
# Get-AzDiskPoolResourceSku

## SYNOPSIS
Mencantumkan sumber daya dan sku StoragePool yang tersedia di lokasi Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.diskpool/get-azdiskpoolresourcesku) untuk informasi terbaru.

## SYNTAX

```
Get-AzDiskPoolResourceSku -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan sumber daya dan sku StoragePool yang tersedia di lokasi Azure.

## EXAMPLES

### Contoh 1: Mencantumkan semua sumber daya dan sku di lokasi
```powershell
Get-AzDiskPoolResourceSku -Location AustraliaEast
```

```output
ApiVersion Name        ResourceType Tier
---------- ----        ------------ ----
2021-08-01 Standard_S1 diskPools    Standard
2021-08-01 Premium_P1  diskPools    Premium
2021-08-01 Basic_B1    diskPools    Basic
```

Perintah mencantumkan semua sumber daya dan sku di lokasi.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IResourceSkuInfo

## NOTES

ALIAS

## RELATED LINKS

