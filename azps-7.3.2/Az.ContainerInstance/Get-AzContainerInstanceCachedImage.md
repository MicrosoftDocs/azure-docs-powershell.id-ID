---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/get-azcontainerinstancecachedimage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerInstanceCachedImage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerInstanceCachedImage.md
ms.openlocfilehash: d41ea67c7a4b79cbd5c94fb58740ffc8ee119c71
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140560209"
---
# Get-AzContainerInstanceCachedImage

## SYNOPSIS
Dapatkan daftar gambar singgahan di tipe OS tertentu untuk langganan di suatu kawasan.

## SYNTAX

```
Get-AzContainerInstanceCachedImage -Location <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar gambar singgahan di tipe OS tertentu untuk langganan di suatu kawasan.

## EXAMPLES

### Contoh 1: Dapatkan daftar gambar singgahan untuk langganan saat ini di kawasan.
```powershell
Get-AzContainerInstanceCachedImage -Location eastus
```

```output
Image                                                                                OSType
-----                                                                                ------
microsoft/dotnet-framework:4.7.2-runtime-20181211-windowsservercore-ltsc2016         Windows
microsoft/dotnet-framework:4.7.2-runtime-20190108-windowsservercore-ltsc2016         Windows
microsoft/dotnet-framework:4.7.2-runtime-20190212-windowsservercore-ltsc2016         Windows
...
```

Perintah ini berisi daftar gambar singgahan untuk langganan saat ini di kawasan tersebut `eastus`.

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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.ICachedImages

## CATATAN

ALIAS

## RELATED LINKS

