---
external help file: Azs.Compute.Admin-help.xml
Module Name: Azs.Compute.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1acb246ae646fe9a63a8631f2ec08dfb731a373f18f9f3f8b52b6e751fb48ae7
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415604"
---
# Get-AzsDisk

## SYNOPSIS
Mengembalikan daftar disk terkelola yang dapat dimigrasikan dalam berbagi yang ditentukan.

## SYNTAX

### Daftar (Default)
```
Get-AzsDisk [-Location <String>] [-Start <Int32>] [-SharePath <String>] [-Count <Int32>]
 [-UserSubscriptionId <String>] [-Status <String>] [<CommonParameters>]
```

### ResourceId
```
Get-AzsDisk -ResourceId <String> [<CommonParameters>]
```

### Dapatkan
```
Get-AzsDisk [-Location <String>] -Name <String> [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan daftar disk.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
$disks = Get-AzsDisk -location local
```

Mengembalikan daftar disk yang dikelola di lokasi lokal.
Secara default, ini akan menjadi 100 disk pertama

### -------------------------- CONTOH 2 --------------------------
```
$disk = Get-AzsDisk -location local -name $DiskId
```

Mendapatkan disk terkelola tertentu.

## PARAMETERS

### -Count
Jumlah maksimum disk untuk dikembalikan.

```yaml
Type: Int32
Parameter Sets: List
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya.

```yaml
Type: String
Parameter Sets: List, Get
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Disk guid sebagai identitas.

```yaml
Type: String
Parameter Sets: Get
Aliases: DiskId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya.

```yaml
Type: String
Parameter Sets: ResourceId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SharePath
Sumber berbagi sumber daya tempat sumber daya tersebut berada.

```yaml
Type: String
Parameter Sets: List
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mulai
The start index of disks in query.

```yaml
Type: Int32
Parameter Sets: List
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Parameter status disk.

```yaml
Type: String
Parameter Sets: List
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserSubscriptionId
Id Langganan Penyewa yang menjadi sumber dayanya.

```yaml
Type: String
Parameter Sets: List
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Compute.Admin.Models.Disk

## CATATAN

## RELATED LINKS

