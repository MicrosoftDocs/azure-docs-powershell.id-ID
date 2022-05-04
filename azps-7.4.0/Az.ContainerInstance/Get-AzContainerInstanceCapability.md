---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/get-azcontainerinstancecapability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerInstanceCapability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerInstanceCapability.md
ms.openlocfilehash: d4aee08227573f27859a47bd14293dc31c32528e
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144565996"
---
# Get-AzContainerInstanceCapability

## SYNOPSIS
Dapatkan daftar kemampuan CPU/memori/GPU suatu wilayah.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/get-azcontainerinstancecapability) untuk informasi terbaru.

## SYNTAX

```
Get-AzContainerInstanceCapability -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar kemampuan CPU/memori/GPU suatu wilayah.

## EXAMPLES

### Contoh 1: Mendapatkan daftar kemampuan lokasi
```powershell
Get-AzContainerInstanceCapability -Location eastus
```

```output
Gpu  IPAddressType Location OSType       ResourceType   
---  ------------- -------- ------       ------------   
None Public        eastus   NotSpecified containerGroups
None Private       eastus   NotSpecified containerGroups
None Public        EASTUS   Linux        containerGroups
None Private       EASTUS   Linux        containerGroups
K80  Public        EASTUS   Linux        containerGroups
P100 Public        EASTUS   Linux        containerGroups
V100 Public        EASTUS   Linux        containerGroups
None Public        EASTUS   Windows      containerGroups
```

Perintah ini mendapatkan daftar kemampuan CPU/memori/GPU wilayah `eastus`.

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
Pengidentifikasi untuk lokasi azure fisik.

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
Kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.ICapabilities

## NOTES

ALIAS

## RELATED LINKS

