---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/update-azgalleryimageversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Update-AzGalleryImageVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Update-AzGalleryImageVersion.md
ms.openlocfilehash: 0fac9ec303a8f13bf0c910efd52d16ec6a9a4ae7
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145506619"
---
# Update-AzGalleryImageVersion

## SYNOPSIS
Memperbarui versi gambar galeri.

## SYNTAX

### DefaultParameter (Default)
```
Update-AzGalleryImageVersion [-ResourceGroupName] <String> [-GalleryName] <String>
 [-GalleryImageDefinitionName] <String> [-Name] <String> [-AsJob] [-PublishingProfileEndOfLifeDate <DateTime>]
 [-PublishingProfileExcludeFromLatest] [-ReplicaCount <Int32>] [-Tag <Hashtable>] [-TargetRegion <Hashtable[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdParameter
```
Update-AzGalleryImageVersion [-ResourceId] <String> [-AsJob] [-PublishingProfileEndOfLifeDate <DateTime>]
 [-PublishingProfileExcludeFromLatest] [-ReplicaCount <Int32>] [-Tag <Hashtable>] [-TargetRegion <Hashtable[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ObjectParameter
```
Update-AzGalleryImageVersion [-InputObject] <PSGalleryImageVersion> [-AsJob]
 [-PublishingProfileEndOfLifeDate <DateTime>] [-PublishingProfileExcludeFromLatest] [-ReplicaCount <Int32>]
 [-Tag <Hashtable>] [-TargetRegion <Hashtable[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui versi gambar galeri.

## EXAMPLES

### Contoh 1: Mengubah wilayah replikasi dan jumlah replika

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$imageName = "myImage"
$versionName = "1.0.0"
$region1 = @{Name='West US';ReplicaCount=1}
$region2 = @{Name='East US';ReplicaCount=2}
$region3 = @{Name='Central US'}
$targetRegions = @($region1,$region2,$region3)
Update-AzGalleryImageVersion -ResourceGroupName $rgname -GalleryName $galleryName -GalleryImageDefinitionName $imageName -Name $versionName -ReplicaCount 2 -TargetRegion $targetRegions
```

Memperbarui wilayah versi gambar galeri.

### Contoh 2: Mengubah apakah versi gambar harus dipertimbangkan untuk yang terbaru.

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$imageName = "myImage"
$versionName = "1.0.0"
Update-AzGalleryImageVersion -ResourceGroupName $rgname -GalleryName $galleryName -GalleryImageDefinitionName $imageName -Name $versionName -PublishingProfileExcludeFromLatest:$false
```

Perbarui pengecualian versi gambar galeri dari status terbaru. Untuk menyertakan versi gambar dalam pertimbangan terbaru, gunakan `-PublishingProfileExcludeFromLatest:$false`. Untuk mengecualikan versi gambar dari pertimbangan untuk yang terbaru, gunakan `-PublishingProfileExcludeFromLatest`.

### Contoh 3: Ubah tanggal akhir masa pakai untuk versi gambar.

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$imageName = "myImage"
$versionName = "1.0.0"
$endOfLifeDate = "2024-08-02T00:00:00+00:00"
Update-AzGalleryImageVersion -ResourceGroupName $rgname -GalleryName $galleryName -GalleryImageDefinitionName $imageName -Name $versionName -PublishingProfileEndOfLifeDate $endOfLifeDate
```

Perbarui tanggal akhir masa pakai versi gambar galeri. Versi gambar masih dapat digunakan untuk membuat komputer virtual setelah tanggal akhir masa pakai.


## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -GalleryImageDefinitionName
Nama definisi gambar galeri.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GalleryName
Nama galeri.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Objek Versi Gambar Galeri PS.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSGalleryImageVersion
Parameter Sets: ObjectParameter
Aliases: GalleryImageVersion

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama versi gambar galeri.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases: GalleryImageVersionName

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublishingProfileEndOfLifeDate
Tanggal akhir masa pakai Versi Gambar galeri.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublishingProfileExcludeFromLatest
Jika diatur, Virtual Machines disebarkan dari versi terbaru Definisi Gambar tidak akan menggunakan Versi Gambar ini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicaCount
Jumlah replika Versi Gambar yang akan dibuat per wilayah.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya untuk versi gambar galeri.

```yaml
Type: System.String
Parameter Sets: ResourceIdParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Tag sumber daya

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetRegion
Wilayah target tempat Versi Gambar akan direplikasi.

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Compute.Automation.Models.PSGalleryImageVersion

### System.Collections.Hashtable

### System.Int32

### System.Management.Automation.SwitchParameter

### System.DateTime

### System.Collections.Hashtable[]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSGalleryImageVersion

## NOTES

## RELATED LINKS
