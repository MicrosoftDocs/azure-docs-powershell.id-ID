---
external help file: ''
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azvmssvmruncommand
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVmssVMRunCommand.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVmssVMRunCommand.md
ms.openlocfilehash: 49c02ae887379e005b1aaf9db8b6f7e306961d4b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143231147"
---
# Get-AzVmssVMRunCommand

## SYNOPSIS
Operasi untuk mendapatkan perintah jalankan VMSS VM.

## SYNTAX

### Daftar (Default)
```
Get-AzVmssVMRunCommand -InstanceId <String> -ResourceGroupName <String> -VMScaleSetName <String>
 [-SubscriptionId <String[]>] [-Expand <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzVmssVMRunCommand -InstanceId <String> -ResourceGroupName <String> -RunCommandName <String>
 -VMScaleSetName <String> [-SubscriptionId <String[]>] [-Expand <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzVmssVMRunCommand -InputObject <IComputeIdentity> [-Expand <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk mendapatkan perintah jalankan VMSS VM.

## EXAMPLES

### Contoh 1: Dapatkan RunCommand menurut nama
```powershell
Get-AzVmssVMRunCommand -InstanceId 3 -ResourceGroupName $rgname -RunCommandName "first" -VMScaleSetName $vmssname
```

```output
Location Name  Type
-------- ----  ----
eastus   first Microsoft.Compute/virtualMachineScaleSets/virtualMachines/runCommands
```

Dapatkan dengan nama runcommand

### Contoh 2: Get RunCommand by Instance
```powershell
Get-AzVmssVMRunCommand -InstanceId 3 -ResourceGroupName $rgname  -VMScaleSetName $vmssname
```

```output
Location Name  Type
-------- ----  ----
eastus   first Microsoft.Compute/virtualMachineScaleSets/virtualMachines/runCommands
```

Dapatkan RunCommand menurut Instance

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
Ekspresi perluas untuk diterapkan pada operasi.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -InstanceId
ID instans mesin virtual.

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

### -RunCommandName
Nama perintah jalankan mesin virtual.

```yaml
Type: System.String
Parameter Sets: Get
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
Type: System.String[]
Parameter Sets: Get, List
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
Parameter Sets: Get, List
Aliases:

Required: True
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

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IVirtualMachineRunCommand

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

