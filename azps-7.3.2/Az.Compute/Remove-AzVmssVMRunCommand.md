---
external help file: ''
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/remove-azvmssvmruncommand
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzVmssVMRunCommand.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzVmssVMRunCommand.md
ms.openlocfilehash: 6300e9f7b9af5041d72eb9bee7d318523326e93a
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140550339"
---
# Remove-AzVmssVMRunCommand

## SYNOPSIS
Operasi untuk menghapus perintah VMSS VM run.

## SYNTAX

### Hapus (Default)
```
Remove-AzVmssVMRunCommand -InstanceId <String> -ResourceGroupName <String> -RunCommandName <String>
 -VMScaleSetName <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzVmssVMRunCommand -InputObject <IComputeIdentity> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk menghapus perintah VMSS VM run.

## EXAMPLES

### Contoh 1: Hapus VMSS VM RunCommand
```powershell
Remove-AzVmssVMRunCommand -InstanceId 3 -ResourceGroupName $rgname -RunCommandName "first" -VMScaleSetName $vmssname

```

Hapus VMSS VM RunCommand

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -InstanceId
ID contoh mesin virtual.

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

### -NoWait
Menjalankan perintah secara asinkron

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
Mengembalikan true saat perintah berhasil

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

### -RunCommandName
Nama perintah mesin virtual yang dijalankan.

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
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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

### -VMScaleSetName
Nama kumpulan skala VM.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.IComputeIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IComputeIdentity>: Parameter Identitas
  - `[CommandId <String>]`: Id perintah.
  - `[GalleryApplicationName <String>]`: Nama galeri Definisi Aplikasi yang akan dibuat atau diperbarui. Karakter yang diperbolehkan adalah alfabet dan angka dengan titik, garis putus-putus, dan titik yang diperbolehkan di tengah. Panjang maksimum adalah 80 karakter.
  - `[GalleryApplicationVersionName <String>]`: Nama galeri Versi Aplikasi yang akan dibuat. Harus mengikuti pola nama versi semantik: Karakter yang diperbolehkan adalah digit dan titik. Digit harus berada di dalam rentang bilangan bulat 32-bit. Format: <MajorVersion>.<MinorVersion>.<Patch>
  - `[GalleryImageName <String>]`: Nama definisi gambar galeri yang akan dibuat atau diperbarui. Karakter yang diperbolehkan adalah alfabet dan angka dengan titik, garis putus-putus, dan titik yang diperbolehkan di tengah. Panjang maksimum adalah 80 karakter.
  - `[GalleryImageVersionName <String>]`: Nama versi gambar galeri yang akan dibuat. Harus mengikuti pola nama versi semantik: Karakter yang diperbolehkan adalah digit dan titik. Digit harus berada di dalam rentang bilangan bulat 32-bit. Format: <MajorVersion>.<MinorVersion>.<Patch>
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

