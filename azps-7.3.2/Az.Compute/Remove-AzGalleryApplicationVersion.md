---
external help file: ''
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/remove-azgalleryapplicationversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzGalleryApplicationVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzGalleryApplicationVersion.md
ms.openlocfilehash: 46acc1b6871749f65b8c17bdc04df0c9af2c4d44
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143186849"
---
# Remove-AzGalleryApplicationVersion

## SYNOPSIS
Menghapus Versi Aplikasi galeri.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/remove-azgalleryapplicationversion) untuk informasi terbaru.

## SYNTAX

### Hapus (Default)
```
Remove-AzGalleryApplicationVersion -GalleryApplicationName <String> -GalleryName <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzGalleryApplicationVersion -InputObject <IComputeIdentity> [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus Versi Aplikasi galeri.

## EXAMPLES

### Contoh 1: Menghapus Versi Aplikasi Galeri 
```powershell
Remove-AzGalleryApplication -ResourceGroupName $rgNmae -GalleryName $galleryName -GalleryApplicationName $galleryApplicationName -Name $name

```

Menghapus versi aplikasi galeri.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GalleryApplicationName
Nama Definisi Aplikasi galeri tempat Versi Aplikasi berada.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GalleryName
Nama Galeri Aplikasi Bersama tempat Definisi Aplikasi berada.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.IComputeIdentity
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Galeri Versi Aplikasi yang akan dihapus.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: GalleryApplicationVersionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
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

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.IComputeIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IComputeIdentity>: Parameter Identitas
  - `[CommandId <String>]`: Id perintah.
  - `[GalleryApplicationName <String>]`: Nama Galeri Definisi Aplikasi yang akan dibuat atau diperbarui. Karakter yang diperbolehkan adalah abjad dan angka dengan titik-titik, garis putus-putus, dan titik yang diperbolehkan di tengah. Panjang maksimum adalah 80 karakter.
  - `[GalleryApplicationVersionName <String>]`: Nama Galeri Versi Aplikasi yang akan dibuat. Perlu mengikuti pola nama versi semantik: Karakter yang diperbolehkan adalah digit dan titik. Digit harus berada dalam rentang bilangan bulat 32-bit. Format: <MajorVersion>.<MinorVersion>.<Patch>
  - `[GalleryImageName <String>]`: Nama definisi gambar galeri yang akan dibuat atau diperbarui. Karakter yang diperbolehkan adalah abjad dan angka dengan titik-titik, garis putus-putus, dan titik yang diperbolehkan di tengah. Panjang maksimum adalah 80 karakter.
  - `[GalleryImageVersionName <String>]`: Nama versi gambar galeri yang akan dibuat. Perlu mengikuti pola nama versi semantik: Karakter yang diperbolehkan adalah digit dan titik. Digit harus berada dalam rentang bilangan bulat 32-bit. Format: <MajorVersion>.<MinorVersion>.<Patch>
  - `[GalleryName <String>]`: Nama Shared Image Gallery. Karakter yang diperbolehkan adalah alfabet dan angka dengan titik dan titik yang diperbolehkan di tengah. Panjang maksimum adalah 80 karakter.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InstanceId <String>]`: ID instans mesin virtual.
  - `[Location <String>]`: Lokasi di mana perintah jalankan dikueri.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[RunCommandName <String>]`: Nama perintah jalankan mesin virtual.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.
  - `[VMName <String>]`: Nama mesin virtual tempat perintah jalankan harus dibuat atau diperbarui.
  - `[VMScaleSetName <String>]`: Nama kumpulan skala VM.

## RELATED LINKS

