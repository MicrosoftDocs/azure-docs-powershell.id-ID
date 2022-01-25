---
external help file: ''
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azgalleryapplicationversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzGalleryApplicationVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzGalleryApplicationVersion.md
ms.openlocfilehash: c350ac56154adde37cf9d148bce0eaa517d918f6
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136724168"
---
# Get-AzGalleryApplicationVersion

## SYNOPSIS
Mengambil informasi tentang galeri Versi Aplikasi.

## SYNTAX

### Daftar (Default)
```
Get-AzGalleryApplicationVersion -GalleryApplicationName <String> -GalleryName <String>
 -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzGalleryApplicationVersion -GalleryApplicationName <String> -GalleryName <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String[]>] [-Expand <ReplicationStatusTypes>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzGalleryApplicationVersion -InputObject <IComputeIdentity> [-Expand <ReplicationStatusTypes>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mengambil informasi tentang galeri Versi Aplikasi.

## EXAMPLES

### Contoh 1: Dapatkan Versi Aplikasi Galeri
```powershell
PS C:\> Get-AzGalleryApplicationVersion -ResourceGroupName $rgName -GalleryName $galleryName -GalleryApplicationName $galleryAppName -Name $versionName

```

Ambil sumber daya Versi Aplikasi Galeri dengan Grup Sumber Daya, Galeri, nama Aplikasi Galeri yang disediakan, dan nama versi.

### Contoh 2: Dapatkan semua Versi Aplikasi Galeri dalam GalleryApplication
```powershell
PS C:\> Get-AzGalleryApplicationVersion -GalleryName $GalleryName -ResourceGroupName $rgName -GalleryApplicationName $galleryAppName

```

Ambil semua sumber daya Versi Aplikasi Galeri di Grup Sumber Daya, Galeri, dan Nama Aplikasi Galeri yang disediakan.

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

### -Perluas
Ekspresi yang diperluas untuk diterapkan pada operasi.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Compute.Support.ReplicationStatusTypes
Parameter Sets: Get, GetViaIdentity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GalleryApplicationName
Nama galeri Definisi Aplikasi di mana Versi Aplikasi berada.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GalleryName
Nama Galeri Aplikasi Bersama di mana Definisi Aplikasi berada.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.IComputeIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Versi Aplikasi galeri yang akan diambil.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: GalleryApplicationVersionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure anda.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String[]
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.IComputeIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IGalleryApplicationVersion

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IComputeIdentity> : Parameter Identitas
  - `[CommandId <String>]`: Id perintah.
  - `[GalleryApplicationName <String>]`: Nama galeri Definisi Aplikasi yang akan dibuat atau diperbarui. Karakter yang diperbolehkan adalah alfabet dan angka dengan titik, garis putus-putus, dan titik yang diperbolehkan di tengah. Panjang maksimum adalah 80 karakter.
  - `[GalleryApplicationVersionName <String>]`: Nama galeri Versi Aplikasi yang akan dibuat. Harus mengikuti pola nama versi semantik: Karakter yang diperbolehkan adalah digit dan titik. Digit harus berada di dalam rentang bilangan bulat 32-bit. Format: <MajorVersion> . <MinorVersion> .<Patch>
  - `[GalleryImageName <String>]`: Nama definisi gambar galeri yang akan dibuat atau diperbarui. Karakter yang diperbolehkan adalah alfabet dan angka dengan titik, garis putus-putus, dan titik yang diperbolehkan di tengah. Panjang maksimum adalah 80 karakter.
  - `[GalleryImageVersionName <String>]`: Nama versi gambar galeri yang akan dibuat. Harus mengikuti pola nama versi semantik: Karakter yang diperbolehkan adalah digit dan titik. Digit harus berada di dalam rentang bilangan bulat 32-bit. Format: <MajorVersion> . <MinorVersion> .<Patch>
  - `[GalleryName <String>]`: Nama Galeri Gambar Bersama. Karakter yang diperbolehkan adalah alfabet dan angka dengan titik dan titik yang diperbolehkan di tengah. Panjang maksimum adalah 80 karakter.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InstanceId <String>]`: ID contoh mesin virtual.
  - `[Location <String>]`: Lokasi tempat menjalankan kueri perintah.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[RunCommandName <String>]`: Nama perintah mesin virtual yang dijalankan.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.
  - `[VMName <String>]`: Nama mesin virtual tempat perintah jalankan harus dibuat atau diperbarui.
  - `[VMScaleSetName <String>]`: Nama kumpulan skala VM.

## RELATED LINKS

