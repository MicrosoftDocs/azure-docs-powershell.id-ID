---
external help file: ''
Module Name: Az.CustomLocation
online version: https://docs.microsoft.com/powershell/module/az.customlocation/get-azcustomlocationenabledresourcetype
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomLocation/help/Get-AzCustomLocationEnabledResourceType.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomLocation/help/Get-AzCustomLocationEnabledResourceType.md
ms.openlocfilehash: fa66cc8ab3bd630664ca5ff216602acb44c0ea9e
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140009904"
---
# Get-AzCustomLocationEnabledResourceType

## SYNOPSIS
Mendapatkan daftar Tipe Sumber Daya yang Diaktifkan.

## SYNTAX

```
Get-AzCustomLocationEnabledResourceType -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar Tipe Sumber Daya yang Diaktifkan.

## EXAMPLES

### Contoh 1: Mendapatkan daftar Tipe Sumber Daya yang Diaktifkan.
```powershell
PS C:\>  Get-AzCustomLocationEnabledResourceType -ResourceGroupName azps_test_group -Name azps_test_cluster

Name                                                             Type
----                                                             ----
017e563408cfcbaad0604875fef1f0e5a36d5fefa5e81a4c1c212c5a77fbcbde Microsoft.ExtendedLocation/customLocations/enabledResourceTypes
```

Mendapatkan daftar Tipe Sumber Daya yang Diaktifkan.

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
Namanya peka huruf besar/huruf.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CustomLocation.Models.Api20210815.IEnabledResourceType

## CATATAN

ALIAS

## RELATED LINKS

