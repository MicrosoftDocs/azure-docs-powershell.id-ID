---
external help file: ''
Module Name: Az.CloudService
online version: https://docs.microsoft.com/powershell/module/az.cloudservice/new-azcloudserviceroleprofilepropertiesobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceRoleProfilePropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/New-AzCloudServiceRoleProfilePropertiesObject.md
ms.openlocfilehash: 28aec5f0e074086db24663ee9df7ff77b4db2bd1
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140110025"
---
# New-AzCloudServiceRoleProfilePropertiesObject

## SYNOPSIS
Membuat objek dalam memori untuk CloudServiceRoleProfileProperties

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.cloudservice/new-azcloudserviceroleprofilepropertiesobject) untuk informasi terkini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.CloudServiceRoleProfileProperties

## CATATAN

ALIAS

## RELATED LINKS

