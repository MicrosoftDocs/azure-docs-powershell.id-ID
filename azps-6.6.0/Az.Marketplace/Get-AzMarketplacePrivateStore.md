---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Marketplace.dll-Help.xml
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/get-azmarketplaceprivatestore
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplacePrivateStore.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplacePrivateStore.md
ms.openlocfilehash: a257c80e7906c4afff85fd9ed1c1e9434657d356
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143090109"
---
# Get-AzMarketplacePrivateStore

## SYNOPSIS
Dapatkan daftar bursa pribadi

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.marketplace/get-azmarketplaceprivatestore) untuk informasi terbaru.

## SYNTAX

```
Get-AzMarketplacePrivateStore [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar bursa pribadi yang dibuat di bawah lingkup penyewa

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzMarketplacePrivateStore


Availability   : enabled
PrivateStoreId : 7gh67884-1r56-44fb-a93d-030d4ae08b2d
ETag           : "47006253-0000-0100-0000-5ecb6df90000"
Id             : /providers/Microsoft.Marketplace/privateStores/7gh67884-1r56-44fb-a93d-030d4ae08b2d
Name           : 7gh67884-1r56-44fb-a93d-030d4ae08b2d
Type           : Microsoft.Marketplace/privateStores
```

daftar bursa pribadi yang dibuat di bawah lingkup penyewa

## PARAMETERS

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Marketplace.Models.PrivateStore.PSPrivateStore

## NOTES

## RELATED LINKS
