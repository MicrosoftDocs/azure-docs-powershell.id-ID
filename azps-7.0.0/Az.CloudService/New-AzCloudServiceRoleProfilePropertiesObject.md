---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/new-azcloudserviceroleprofilepropertiesobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceRoleProfilePropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceRoleProfilePropertiesObject.md
ms.openlocfilehash: b766f86051b519f314983d04cf5a6784fd5f1f34
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136545305"
---
# New-AzCloudServiceRoleProfilePropertiesObject

## SYNOPSIS
Membuat objek dalam memori untuk CloudServiceRoleProfileProperties

## SYNTAX

```
New-AzCloudServiceRoleProfilePropertiesObject [-Name <String>] [-SkuCapacity <Int64>] [-SkuName <String>]
 [-SkuTier <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk CloudServiceRoleProfileProperties

## EXAMPLES

### Contoh 1: Membuat objek properti profil peran
```powershell
$role = New-AzCloudServiceRoleProfilePropertiesObject -Name 'WebRole' -SkuName 'Standard_D1_v2' -SkuTier 'Standard' -SkuCapacity 2
```

Perintah ini membuat objek properti profil peran yang digunakan untuk membuat atau memperbarui layanan awan.
Untuk detail selengkapnya, lihat New-AzCloudService.

## PARAMETERS

### -Nama
Nama profil peran.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuCapacity
Menentukan jumlah instans peran di layanan awan.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuName
Nama sku.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuTier
SkuTier.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.CloudServiceRoleProfileProperties

## CATATAN

ALIAS

## RELATED LINKS

