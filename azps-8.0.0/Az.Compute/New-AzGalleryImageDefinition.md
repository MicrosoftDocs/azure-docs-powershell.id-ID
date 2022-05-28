---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azgalleryimagedefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryImageDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryImageDefinition.md
ms.openlocfilehash: 7b675cd8f98cd558883d13bc036edf1868645305
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145517326"
---
# New-AzGalleryImageDefinition

## SYNOPSIS

Membuat definisi gambar galeri.

## SYNTAX

```
New-AzGalleryImageDefinition [-ResourceGroupName] <String> [-GalleryName] <String> [-Name] <String> [-AsJob]
 [-Location] <String> -Publisher <String> -Offer <String> -Sku <String> -OsState <OperatingSystemStateTypes>
 -OsType <OperatingSystemTypes> [-Description <String>] [-DisallowedDiskType <String[]>]
 [-EndOfLifeDate <DateTime>] [-Eula <String>] [-HyperVGeneration <String>] [-MinimumMemory <Int32>]
 [-MinimumVCPU <Int32>] [-MaximumMemory <Int32>] [-MaximumVCPU <Int32>] [-PrivacyStatementUri <String>]
 [-PurchasePlanName <String>] [-PurchasePlanProduct <String>] [-PurchasePlanPublisher <String>]
 [-ReleaseNoteUri <String>] [-Tag <Hashtable>] [-Feature <GalleryImageFeature[]>] [-Architecture <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Membuat definisi gambar galeri.

## EXAMPLES

### Contoh 1: Membuat definisi gambar untuk gambar linux khusus

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$location = "eastus"
$publisherName = "GreatPublisher"
$offerName = "GreatOffer"
$skuName = "GreatSku"
$description = "My gallery"
New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Specialized" -OsType "Linux" -Description $description
```

Membuat definisi gambar galeri untuk berisi versi gambar untuk gambar linux khusus.

### Contoh 2: Membuat definisi gambar untuk gambar linux umum

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$location = "eastus"
$publisherName = "GreatPublisher"
$offerName = "GreatOffer"
$skuName = "GreatSku"
$description = "My gallery"
New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -Description $description
```

Membuat definisi gambar galeri untuk berisi versi gambar untuk gambar linux umum.

### Contoh 3: Membuat definisi gambar untuk gambar jendela khusus

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$location = "eastus"
$publisherName = "GreatPublisher"
$offerName = "GreatOffer"
$skuName = "GreatSku"
$description = "My gallery"
New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Specialized" -OsType "Windows" -Description $description
```

Membuat definisi gambar galeri untuk berisi versi gambar untuk gambar windows khusus.

### Contoh 4: Buat definisi gambar untuk gambar windows umum dan atur fitur.

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$location = "eastus"
$publisherName = "GreatPublisher"
$offerName = "GreatOffer"
$skuName = "GreatSku"
$description = "My gallery"
$IsHibernateSupported = @{Name='IsHibernateSupported';Value='True'} 
$IsAcceleratedNetworkSupported = @{Name='IsAcceleratedNetworkSupported';Value='False'}
$features = @($IsHibernateSupported,$IsAcceleratedNetworkSupported)
New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Windows" -Description $description -Feature $features
```

Membuat definisi gambar galeri untuk memuat versi gambar untuk gambar windows umum.

### Contoh 5: Membuat definisi gambar dengan informasi paket

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$location = "eastus"
$publisherName = "GreatPublisher"
$offerName = "GreatOffer"
$skuName = "GreatSku"
$purchasePlanName = "myPlanName"
$purchasePlanProduct = "myPlanProduct"
$purchasePlanPublisher = "myPlanPublisher"
New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -PurchasePlanName $purchasePlanName -PurchasePlanProduct $purchasePlanProduct -PurchasePlanPublisher $purchasePlanPublisher
```

Membuat definisi gambar galeri untuk gambar umum linux dan menentukan nama paket, produk, dan penerbit. Hanya versi gambar yang cocok dengan informasi paket yang dapat ditambahkan ke definisi ini.

### Contoh 6: Membuat definisi gambar dan menunjukkan tanggal akhir masa pakai

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$location = "eastus"
$publisherName = "GreatPublisher"
$offerName = "GreatOffer"
$skuName = "GreatSku"
$endOfLifeDate = "2024-08-02T00:00:00+00:00"
New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -EndOfLifeDate $endOfLifeDate
```

Contoh ini memiliki tanggal akhir masa pakai untuk definisi gambar yang diatur ke 2 Agustus 2024 pada mignight UTC. Tanggal akhir masa pakai dapat ditentukan untuk definisi gambar dan versi gambar. Definisi gambar masih dapat digunakan setelah tanggal akhir masa pakai.

### Contoh 7: Membuat definisi gambar dan merekomendasikan CPU dan memori minimum dan maksimum (GB)

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$location = "eastus"
$publisherName = "GreatPublisher"
$offerName = "GreatOffer"
$skuName = "GreatSku"
$minMemory = 32
$maxMemory = 128
$minVCPU = 2
$maxVCPU = 8
New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -MinimumMemory $minMemory -MaximumMemory $maxMemory -MinimumVCPU $minVCPU -MaximumVCPU $maxVCPU
```

Membuat definisi gambar galeri dan merekomendasikan rentang minimum dan maksimum untuk CPU dan memori yang didukung versi gambar dalam definisi gambar ini. Versi gambar masih dapat digunakan untuk membuat komputer virtual dengan pengaturan memori dan vCPU di luar rentang yang direkomendasikan.

### Contoh 8: Buat definisi gambar dan tunjukkan jenis disk OS mana yang tidak direkomendasikan untuk gambar

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$location = "eastus"
$publisherName = "GreatPublisher"
$offerName = "GreatOffer"
$skuName = "GreatSku"
$disallowedDiskTypes = @("Standard_LRS")
New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -DisallowedDiskType $disallowedDiskTypes
```

Membuat definisi gambar galeri dan menunjukkan jenis disk OS mana yang mungkin tidak kompatibel dengan versi gambar dalam definisi gambar ini. Versi gambar masih dapat digunakan untuk membuat komputer virtual dengan disk OS yang merupakan salah satu jenis disk yang tidak diizinkan.

### Contoh 9: Buat definisi gambar dan berikan EULA, URI pernyataan privasi, dan catatan rilis URI

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$location = "eastus"
$publisherName = "GreatPublisher"
$offerName = "GreatOffer"
$skuName = "GreatSku"
$eula = "https://myeula"
$privacyStatementUri = "https://mystatement"
$releaseNoteUri = "https://myreleasenotes"
New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -Eula $eula -PrivacyStatementUri $privacyStatementUri -ReleaseNoteUri $releaseNoteUri
```

Membuat definisi gambar galeri untuk gambar umum linux dan menentukan string atau jalur ke perjanjian EULA, pernyataan privasi, dan catatan rilis yang terkait dengan semua versi gambar dalam definisi gambar.

## PARAMETERS

### -Arsitektur
Arsitektur CPU yang didukung oleh disk OS. Nilai yang mungkin adalah "X64" dan "Arm64".

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

### -Deskripsi

Deskripsi sumber daya Definisi gambar galeri.

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

### -DisallowedDiskType

Jenis disk yang tidak diizinkan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndOfLifeDate

Tanggal akhir masa pakai galeri Definisi Gambar

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

### -Eula

Perjanjian Eula untuk galeri Definisi Gambar.

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

### -Fitur

Daftar fitur gambar galeri.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.GalleryImageFeature[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### -HyperVGeneration

Generasi hypervisor Komputer Virtual. Hanya berlaku untuk disk OS. Nilai yang diizinkan adalah V1 dan V2.

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

### -Lokasi

Lokasi sumber daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaximumMemory

Maksimum memori yang disarankan

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

### -MaximumVCPU

Maksimum inti CPU yang direkomendasikan

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

### -MinimumMemory

Minimum memori yang disarankan

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

### -MinimumVCPU

Minimum inti CPU yang direkomendasikan

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

### -Name

Nama definisi gambar galeri.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: GalleryImageDefinitionName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Penawaran

Nama galeri penawaran Definisi Gambar.

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

### -OsState

Status OS

```yaml
Type: Microsoft.Azure.Management.Compute.Models.OperatingSystemStateTypes
Parameter Sets: (All)
Aliases:
Accepted values: Generalized, Specialized

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OsType

Jenis OS

```yaml
Type: Microsoft.Azure.Management.Compute.Models.OperatingSystemTypes
Parameter Sets: (All)
Aliases:
Accepted values: Windows, Linux

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivacyStatementUri

Pernyataan privasi uri.

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

### -Publisher

Nama galeri penerbit Definisi Gambar.

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

### -PurchasePlanName

ID untuk paket pembelian.

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

### -PurchasePlanProduct

ID produk untuk paket pembelian.

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

### -PurchasePlanPublisher

ID penerbit untuk paket pembelian.

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

### -ReleaseNoteUri

Catatan rilis uri.

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

### -Sku

Nama galeri SKU Definisi Gambar.

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

### Microsoft.Azure.Management.Compute.Models.OperatingSystemStateTypes

### Microsoft.Azure.Management.Compute.Models.OperatingSystemTypes

### System.DateTime

### System.Collections.Hashtable

### System.Int32

### System.String[]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSGalleryImage

## NOTES

## RELATED LINKS
