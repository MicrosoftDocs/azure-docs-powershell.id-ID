---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azgalleryimagedefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryImageDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryImageDefinition.md
ms.openlocfilehash: 7e0aceabdc6075761f72e9b05903d9a2b222ae35
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136756816"
---
# New-AzGalleryImageDefinition

## SYNOPSIS

Buat definisi gambar galeri.

## SYNTAX

```
New-AzGalleryImageDefinition [-ResourceGroupName] <String> [-GalleryName] <String> [-Name] <String> [-AsJob]
 [-Location] <String> -Publisher <String> -Offer <String> -Sku <String> -OsState <OperatingSystemStateTypes>
 -OsType <OperatingSystemTypes> [-Description <String>] [-DisallowedDiskType <String[]>]
 [-EndOfLifeDate <DateTime>] [-Eula <String>] [-HyperVGeneration <String>] [-MinimumMemory <Int32>]
 [-MinimumVCPU <Int32>] [-MaximumMemory <Int32>] [-MaximumVCPU <Int32>] [-PrivacyStatementUri <String>]
 [-PurchasePlanName <String>] [-PurchasePlanProduct <String>] [-PurchasePlanPublisher <String>]
 [-ReleaseNoteUri <String>] [-Tag <Hashtable>] [-Feature <GalleryImageFeature[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Buat definisi gambar galeri.

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
PS C:\> New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Specialized" -OsType "Linux" -Description $description
```

Membuat definisi gambar galeri untuk memuat versi gambar untuk gambar linux khusus.

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
PS C:\> New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -Description $description
```

Membuat definisi gambar galeri untuk memuat versi gambar untuk gambar linux yang umum.

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
PS C:\> New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Specialized" -OsType "Windows" -Description $description
```

Membuat definisi gambar galeri untuk memuat versi gambar untuk gambar jendela khusus.

### Contoh 4: Buat definisi gambar untuk gambar jendela umum dan atur fitur. 

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
PS C:\> New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Windows" -Description $description -Feature $features
```

Membuat definisi gambar galeri untuk memuat versi gambar untuk gambar jendela umum.

### Contoh 5: Membuat definisi gambar dengan informasi rencana

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
PS C:\> New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -PurchasePlanName $purchasePlanName -PurchasePlanProduct $purchasePlanProduct -PurchasePlanPublisher $purchasePlanPublisher
```

Membuat definisi gambar galeri untuk gambar linux yang disosialisasikan dan menentukan nama rencana, produk, dan penerbit. Hanya versi gambar yang cocok dengan informasi rencana yang bisa ditambahkan ke definisi ini.

### Contoh 6: Membuat definisi gambar dan menunjukkan tanggal masa berakhir

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$location = "eastus"
$publisherName = "GreatPublisher"
$offerName = "GreatOffer"
$skuName = "GreatSku"
$endOfLifeDate = "2024-08-02T00:00:00+00:00"
PS C:\> New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -EndOfLifeDate $endOfLifeDate
```

Contoh ini memiliki tanggal masa berakhir untuk definisi gambar yang diatur ke 2 Agustus 2024 pada UTC mignight. Tanggal masa berakhir dapat ditentukan untuk definisi gambar dan versi gambar. Definisi gambar masih dapat digunakan setelah tanggal berakhir.

### Contoh 7: Buat definisi gambar dan rekomendasikan CPU dan maksimum CPU dan memori (GB)

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
PS C:\> New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -MinimumMemory $minMemory -MaximumMemory $maxMemory -MinimumVCPU $minVCPU -MaximumVCPU $maxVCPU
```

Membuat definisi gambar galeri dan menyarankan rentang minimum dan maksimum untuk CPU dan memori yang didukung oleh versi gambar di definisi gambar ini. Versi gambar masih dapat digunakan untuk membuat mesin virtual dengan pengaturan memori dan vCPU di luar rentang yang disarankan.

### Contoh 8: Buat definisi gambar dan indikasikan tipe disk OS mana yang tidak direkomendasikan untuk gambar

```powershell
$rgName = "myResourceGroup"
$galleryName = "myGallery"
$galleryImageDefinitionName = "myImage"
$location = "eastus"
$publisherName = "GreatPublisher"
$offerName = "GreatOffer"
$skuName = "GreatSku"
$disallowedDiskTypes = @("Standard_LRS")
PS C:\> New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -DisallowedDiskType $disallowedDiskTypes
```

Membuat definisi gambar galeri dan menunjukkan tipe disk OS mana yang mungkin tidak kompatibel dengan versi gambar dalam definisi gambar ini. Versi gambar masih dapat digunakan untuk membuat mesin virtual dengan disk OS yang merupakan salah satu tipe disk yang tidak diizinkan.

### Contoh 9: Buat definisi gambar dan sediakan EULA, URI pernyataan privasi, dan URI catatan rilis

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
PS C:\> New-AzGalleryImageDefinition -ResourceGroupName $rgName -GalleryName $galleryName -Name $galleryImageDefinitionName -Location $location -Publisher $publisherName -Offer $offerName -Sku $skuName -OsState "Generalized" -OsType "Linux" -Eula $eula -PrivacyStatementUri $privacyStatementUri -ReleaseNoteUri $releaseNoteUri
```

Membuat definisi gambar galeri untuk gambar umum linux dan menentukan string atau jalur ke perjanjian EULA, pernyataan privasi, dan catatan rilis yang terikat dengan semua versi gambar dalam definisi gambar.

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

Tipe disk yang tidak diizinkan.

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

Tanggal masa berakhir galeri Definisi Gambar

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

Hypervisor Generation dari Mesin Virtual. Berlaku untuk disk OS saja. Nilai yang diperbolehkan adalah V1 dan V2.

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

### -Maximum Maximum Maksimal

Jumlah maksimal memori yang direkomendasikan

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

Jumlah maksimal inti CPU yang direkomendasikan

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

### -Minimum Minimum MinimumMal

Minimum memori yang direkomendasikan

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

### -Nama

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

### -Offer

Nama galeri Penawaran Definisi Gambar.

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

Tipe OS

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

Uri pernyataan privasi.

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

Nama penerbit Definisi Gambar galeri.

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

Uri catatan rilis.

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

### -Konfirmasi

Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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

## CATATAN

## RELATED LINKS
