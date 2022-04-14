---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azgalleryimageversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryImageVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryImageVersion.md
ms.openlocfilehash: f8d13af8b409375d14d20ee49b8c299bfb9e2f9b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141870908"
---
# New-AzGalleryImageVersion

## SYNOPSIS

Membuat versi gambar galeri.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/new-azgalleryimageversion) untuk informasi terbaru.

## SYNTAX

```
New-AzGalleryImageVersion [-ResourceGroupName] <String> [-GalleryName] <String>
 [-GalleryImageDefinitionName] <String> [-Name] <String> [-AsJob] -Location <String>
 [-DataDiskImage <GalleryDataDiskImage[]>] [-OSDiskImage <GalleryOSDiskImage>]
 [-PublishingProfileEndOfLifeDate <DateTime>] [-PublishingProfileExcludeFromLatest] [-ReplicaCount <Int32>]
 [-SourceImageId <String>] [-StorageAccountType <String>] [-Tag <Hashtable>] [-TargetRegion <Hashtable[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Membuat versi gambar galeri.

## EXAMPLES

### Contoh 1: Membuat versi gambar dari mesin virtual

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
$sourceImageId = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myVMRG/providers/Microsoft.Compute/virtualMachines/myVM"
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -SourceImageId $sourceImageId
```

Tambahkan versi gambar baru dari mesin virtual ke dalam definisi gambar.

### Contoh 2: Membuat versi gambar dari gambar terkelola

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
$sourceImageId = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myImageRG/providers/Microsoft.Compute/images/myImage"
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -SourceImageId $sourceImageId
```

Tambahkan versi gambar baru dari gambar terkelola ke dalam definisi gambar.

### Contoh 3: Membuat versi gambar dari versi gambar lain

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
$sourceImageId = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myImageRG/providers/Microsoft.Compute/galleries/myOtherGallery/images/myImageDefinition/versions/1.0.0"
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -SourceImageId $sourceImageId
```

Menyalin versi gambar ke versi gambar lain

### Contoh 4: Menambahkan versi gambar baru dari disk terkelola

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
$osDisk = @{Source = @{Id = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myDiskRG/providers/Microsoft.Compute/disks/myOSDisk" }}
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -OSDiskImage $osDisk
```

Membuat versi gambar dari disk yang dikelola

### Contoh 5: Menambahkan versi gambar baru dari disk terkelola dan menambahkan disk data tambahan

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
$osDisk = @{Source = @{Id = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myDiskRG/providers/Microsoft.Compute/disks/myOSDisk" }}
$dataDisk0 = @{Source = @{Id = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myDiskRG/providers/Microsoft.Compute/disks/myDataDisk" }; Lun = 0; }
$dataDisks = @($dataDisk0)
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -OSDiskImage $osDisk  -DataDiskImage $dataDisks
```

Membuat versi gambar dengan menentukan OS dan disk data

### Contoh 6: Menambahkan versi gambar baru dari snapshot disk OS

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
$osSnapshot = @{Source = @{Id = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/mySnapshotRG/providers/Microsoft.Compute/snapshots/myOSSnapshot" }}
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -OSDiskImage $osDisk
```

Membuat versi gambar dari snapshot disk

### Contoh 7: Menambahkan versi gambar baru dari snapshot disk OS dan menambahkan disk data tambahan

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
$osSnapshot = @{Source = @{Id = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/mySnapshotRG/providers/Microsoft.Compute/snapshots/myOSSnapshot" }}
$dataSnapshot0 = @{Source = @{Id = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/mySnapshotRG/providers/Microsoft.Compute/snapshots/myDataSnapshot" }; Lun = 0; }
$dataDisks = @($dataSnapshot0)
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -OSDiskImage $osSnapshot  -DataDiskImage $dataDisks
```

Buat versi gambar dengan menentukan snapshot untuk OS dan disk data.

### Contoh 8: Menambahkan versi gambar baru dari kombinasi disk dan snapshot

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
$osSnapshot = @{Source = @{Id = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/mySnapshotRG/providers/Microsoft.Compute/snapshots/myOSSnapshot" }}
$dataDisk0 = @{Source = @{Id = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myDiskRG/providers/Microsoft.Compute/disks/myDataDisk" }; Lun = 0; }
$dataDisks = @($dataDisk0)
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -OSDiskImage $osSnapshot  -DataDiskImage $dataDisks
```

Buat versi gambar dengan menentukan snapshot sebagai disk OS dan disk yang dikelola sebagai disk data.

### Contoh 9: Tambahkan versi gambar baru dan salin ke kawasan tambahan.

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
$sourceImageId = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myVMRG/providers/Microsoft.Compute/virtualMachines/myVM"
$replicaCount = 1
$storageAccountType = "Standard_ZRS"
$region_eastus = @{Name = 'East US';ReplicaCount = 3;StorageAccountType = Standard_LRS}
$region_westus = @{Name = 'West US'}
$region_ukwest = @{Name = 'UK West';ReplicaCount = 2}
$region_southcentralus = @{Name = 'South Central US';StorageAccountType = Standard_LRS}
$targetRegions = @($region_eastus, $region_westus, $region_ukwest, $region_southcentralus)
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -SourceImageId $sourceImageId -ReplicaCount 1 -StorageAccountType $storageAccountType -TargetRegion $targetRegions
```

Membuat versi gambar di empat kawasan. Dalam contoh ini, jumlah replika global adalah 1 dan tipe akun penyimpanan global Standard_ZRS. AS Timur akan memiliki 3 replika, masing-masing disimpan di penyimpanan akun Standard_LRS. AS Barat akan mewarisi dari pengaturan global dan memiliki 1 replika yang disimpan di Standard_ZRS. UK West akan memiliki jumlah replika 2 yang disimpan di Standard_ZRS. As Tengah Selatan akan memiliki satu replika yang disimpan di Standard_LRS.

### Contoh 10: Menambahkan versi gambar baru dengan enkripsi di beberapa kawasan

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
$sourceImageId = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myVMRG/providers/Microsoft.Compute/virtualMachines/myVM"
$replicaCount = 1
$storageAccountType = "Standard_ZRS"

# East US regional settings
$eastUSdes = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myDESrg/providers/Microsoft.Compute/diskEncryptionSets/myEastUSDES"
$encryption_eastus_os = @{DiskEncryptionSetId = $eastUSdes }
$encryption_eastus_dd0 = @{DiskEncryptionSetId = $eastUSdes; Lun = 0 }
$encryption_eastus_dd = @($encryption_eastus_dd0)
$eastus_encryption = @{OSDiskImage = $eastus_encryption_os; DataDiskImages = $eastus_encryption_dd }
$region_eastus = @{Name = 'East US';ReplicaCount = 3;StorageAccountType = Standard_LRS; Encryption = $encryption_eastus}

# West US regional settings
$westUS2des = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myDESrg/providers/Microsoft.Compute/diskEncryptionSets/myWestUSDES"
$encryption_westus_os = @{DiskEncryptionSetId = $westUSdes }
$encryption_westus_dd0 = @{DiskEncryptionSetId = $westUSdes; Lun = 0 }
$encryption_westus_dd = @($encryption_westus_dd0)
$westus_encryption = @{OSDiskImage = $encryption_westus_os; DataDiskImages = $encryption_westus_dd }
$region_westus = @{Name = 'West US'; Encryption = $westus_encryption}}

# Create images
$targetRegions = @($region_eastus, $region_westus)
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -SourceImageId $sourceImageId -TargetRegion $targetRegions
```

Buat versi gambar dengan enkripsi di dua kawasan. Kumpulan enkripsi disk adalah sumber daya kawasan dan kumpulan enkripsi disk yang berbeda harus digunakan di setiap kawasan.

### Contoh 11: Membuat versi gambar dan mengecualikannya dari yang terbaru

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -SourceImageId $sourceImageId -PublishingProfileExcludeFromLatest
```

Tambahkan versi gambar baru ke dalam definisi gambar tetapi kecualikan agar tidak dipertimbangkan untuk versi terbaru dalam definisi gambarnya.

### Contoh 12: Membuat versi gambar dan mengatur tanggal masa berakhirnya

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$galleryImageVersionName = "1.0.0"
$location = "eastus"
$endOfLifeDate = "2024-08-02T00:00:00+00:00"
New-AzGalleryImageVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryImageDefinitionName $galleryImageDefinitionName -Name $galleryImageVersionName -Location $location -SourceImageId $sourceImageId -PublishingProfileEndOfLifeDate $endOfLifeDate
```

Contoh ini memiliki tanggal akhir masa berlaku untuk versi gambar yang diatur ke 2 Agustus 2024 di UTC mignight. Tanggal akhir masa pakai dapat ditentukan untuk definisi gambar dan versi gambar. Versi gambar masih dapat digunakan setelah tanggal masa berakhir.

## PARAMETERS

### -AsJob

Menjalankan cmdlet di latar belakang

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

### -DataDiskImage

Gambar disk data. misalnya @{Source = @{Id = <source_id>}; Lun = 1; SizeInGB = 100; HostCaching = "ReadOnly" }

```yaml
Type: Microsoft.Azure.Management.Compute.Models.GalleryDataDiskImage[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Nama galeri.

```yaml
Type: System.String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi

Lokasi sumber daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama

Nama versi gambar galeri.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: GalleryImageVersionName

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSDiskImage

OS disk image misalnya @{Source = @{Id = <source_id>}; SizeInGB = 100; HostCaching = "ReadOnly" }

```yaml
Type: Microsoft.Azure.Management.Compute.Models.GalleryOSDiskImage
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublishingProfileEndOfLifeDate

Tanggal berakhirnya galeri Versi Gambar.

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

Jumlah replika Versi Gambar yang akan dibuat per kawasan.

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
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceImageId

ID gambar sumber tempat Versi Gambar akan dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountType

Menentukan tipe akun penyimpanan yang akan digunakan untuk menyimpan gambar. Properti ini tidak dapat diperbarui. Nilai yang tersedia Standard_LRS, Standard_ZRS, dan Premium_LRS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### System.String

### System.Collections.Hashtable

### System.Int32

### System.Management.Automation.SwitchParameter

### System.DateTime

### System.Collections.Hashtable[]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSGalleryImageVersion

## CATATAN

## RELATED LINKS
