---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.edgeorder/get-azedgeorderproductfamilymetadata
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrderProductFamilyMetadata.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrderProductFamilyMetadata.md
ms.openlocfilehash: 1f5dec849ee02157c406b902c28bf699ee93748c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143001971"
---
# Get-AzEdgeOrderProductFamilyMetadata

## SYNOPSIS
Metode ini menyediakan daftar metadata keluarga produk untuk langganan tertentu.

## SYNTAX

```
Get-AzEdgeOrderProductFamilyMetadata [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Metode ini menyediakan daftar metadata keluarga produk untuk langganan tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan keluarga produk yang tersedia untuk pengadaan langganan
```powershell
$productFamilyMeta = Get-AzEdgeOrderProductFamilyMetadata -SubscriptionId SubscriptionId
$productFamilyMeta.HierarchyInformation
```

```output
ConfigurationName ProductFamilyName ProductLineName ProductName
----------------- ----------------- --------------- -----------
                  azurestackedge
                  azurestackhub
```

Perintah ini akan menyediakan keluarga produk pada langganan yang dituntut.

Pastikan registerProvider di Microsoft.EdgeOrder sudah selesai sebelum menjalankan perintah ini.

Untuk mendapatkan detail tentang perintah Get-AzEdgeOrderProductFamily penggunaan keluarga

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IProductFamiliesMetadataDetails

## NOTES

ALIAS

## RELATED LINKS

