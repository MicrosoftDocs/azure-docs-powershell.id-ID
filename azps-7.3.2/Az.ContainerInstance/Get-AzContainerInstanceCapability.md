---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/get-azcontainerinstancecapability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerInstanceCapability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerInstanceCapability.md
ms.openlocfilehash: 780db02d5eeadd1f999b421c24d0914df56e0f62
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140180090"
---
# Get-AzContainerInstanceCapability

## SYNOPSIS
Dapatkan daftar kapabilitas CPU/memori/GPU di suatu wilayah.

## SYNTAX

```
Get-AzContainerInstanceCapability -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar kapabilitas CPU/memori/GPU di suatu wilayah.

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

Perintah ini berisi daftar kapabilitas CPU/memori/GPU di kawasan.`eastus`

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
Pengidentifikasi untuk lokasi fisik Azure.

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
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.ICapabilities

## CATATAN

ALIAS

## RELATED LINKS

