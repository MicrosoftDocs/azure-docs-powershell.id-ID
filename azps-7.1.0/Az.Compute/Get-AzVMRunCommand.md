---
external help file: ''
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azvmruncommand
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMRunCommand.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMRunCommand.md
ms.openlocfilehash: 1aafcedd89eb7c334eeec0f57a156e937bbf806c
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136763719"
---
# Get-AzVMRunCommand

## SYNOPSIS
Mendapatkan perintah jalankan tertentu untuk langganan di suatu lokasi.

## SYNTAX

### Daftar (Default)
```
Get-AzVMRunCommand -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzVMRunCommand -CommandId <String> -Location <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan1
```
Get-AzVMRunCommand -ResourceGroupName <String> -RunCommandName <String> -VMName <String>
 [-SubscriptionId <String[]>] [-Expand <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzVMRunCommand -InputObject <IComputeIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzVMRunCommand -ResourceGroupName <String> -VMName <String> [-SubscriptionId <String[]>]
 [-Expand <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan perintah jalankan tertentu untuk langganan di suatu lokasi.

## EXAMPLES

### Contoh 1: Dapatkan Perintah Jalankan dengan Nama
```powershell
PS C:\>  Get-AzVMRunCommand -ResourceGroupName $rgname -VMName $vmname -RunCommandName "firstruncommand2"

Location Name             Type
-------- ----             ----
eastus   firstruncommand2 Microsoft.Compute/virtualMachines/runCommands
```

Jalankan Perintah berdasarkan namanya.

### Contoh 2: Get Run Commands by VM
```powershell
PS C:\> Get-AzVMRunCommand -ResourceGroupName $rgname -VMName $vmname  

Location Name             Type
-------- ----             ----
eastus   firstruncommand  Microsoft.Compute/virtualMachines/runCommands
eastus   firstruncommand2 Microsoft.Compute/virtualMachines/runCommands
eastus   firstruncommand3 Microsoft.Compute/virtualMachines/runCommands
```

Dapatkan Perintah Jalankan berdasarkan nama VM

## PARAMETERS

### -CommandId
Id perintah.

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
Type: System.String
Parameter Sets: Get1, List1
Aliases:

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
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Lokasi tempat menjalankan kueri perintah.

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
Parameter Sets: Get1, List1
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
Parameter Sets: Get1
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
Type: System.String[]
Parameter Sets: Get, Get1, List, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Nama mesin virtual yang berisi perintah jalankan.

```yaml
Type: System.String
Parameter Sets: Get1, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.IComputeIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IRunCommandDocument

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IRunCommandDocumentBase

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IVirtualMachineRunCommand

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

