---
external help file: ''
Module Name: Az.CustomLocation
online version: https://docs.microsoft.com/powershell/module/az.customlocation/get-azcustomlocationenabledresourcetype
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomLocation/help/Get-AzCustomLocationEnabledResourceType.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomLocation/help/Get-AzCustomLocationEnabledResourceType.md
ms.openlocfilehash: 2a01d571358b93798a129ef4f1ed54e625a7e75d
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145754938"
---
# Get-AzCustomLocationEnabledResourceType

## SYNOPSIS
Mendapatkan daftar Jenis Sumber Daya yang Diaktifkan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.customlocation/get-azcustomlocationenabledresourcetype) untuk informasi terbaru.

## SYNTAX

```
Get-AzCustomLocationEnabledResourceType -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar Jenis Sumber Daya yang Diaktifkan.

## EXAMPLES

### Contoh 1: Mendapatkan daftar Jenis Sumber Daya yang Diaktifkan.
```powershell
Get-AzCustomLocationEnabledResourceType -ResourceGroupName azps_test_group -Name azps_test_cluster
```

```output
Name                                                             Type
----                                                             ----
017e563408cfcbaad0604875fef1f0e5a36d5fefa5e81a4c1c212c5a77fbcbde Microsoft.ExtendedLocation/customLocations/enabledResourceTypes
```

Mendapatkan daftar Jenis Sumber Daya yang Diaktifkan.

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
Nama Lokasi Kustom.

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

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

### Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Models.Api20210815.IEnabledResourceType

## NOTES

ALIAS

## RELATED LINKS

