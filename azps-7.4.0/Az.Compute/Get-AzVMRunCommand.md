---
external help file: ''
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azvmruncommand
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMRunCommand.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMRunCommand.md
ms.openlocfilehash: d3eab10a16eb92a77d666138b541726855254cd2
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144660330"
---
# Get-AzVMRunCommand

## SYNOPSIS
Mendapatkan perintah jalankan khusus untuk langganan di lokasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/get-azvmruncommand) untuk informasi terbaru.

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

### Get1
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
Mendapatkan perintah jalankan khusus untuk langganan di lokasi.

## EXAMPLES

### Contoh 1: Dapatkan Perintah Jalankan berdasarkan Nama
```powershell
Get-AzVMRunCommand -ResourceGroupName $rgname -VMName $vmname -RunCommandName "firstruncommand2"
```

```output
Location Name             Type
-------- ----             ----
eastus   firstruncommand2 Microsoft.Compute/virtualMachines/runCommands
```

Dapatkan Perintah Jalankan dengan namanya.

### Contoh 2: Dapatkan Perintah Eksekusi oleh VM
```powershell
Get-AzVMRunCommand -ResourceGroupName $rgname -VMName $vmname  
```

```output
Location Name             Type
-------- ----             ----
eastus   firstruncommand  Microsoft.Compute/virtualMachines/runCommands
eastus   firstruncommand2 Microsoft.Compute/virtualMachines/runCommands
eastus   firstruncommand3 Microsoft.Compute/virtualMachines/runCommands
```

Dapatkan Perintah Eksekusi berdasarkan nama VM

## PARAMETERS

### -CommandId
ID perintah.

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
Ekspresi perluas untuk diterapkan pada operasi.

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

### -Lokasi
Lokasi tempat perintah eksekusi dikueri.

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
Nama perintah eksekusi komputer virtual.

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
Info masuk langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
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
Nama komputer virtual yang berisi perintah jalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.IComputeIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IRunCommandDocument

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IRunCommandDocumentBase

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IVirtualMachineRunCommand

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IComputeIdentity>: Parameter Identitas
  - `[CommandId <String>]`: Id perintah.
  - `[GalleryApplicationName <String>]`: Nama Definisi Aplikasi galeri yang akan dibuat atau diperbarui. Karakter yang diizinkan adalah alfabet dan angka dengan titik, tanda hubung, dan titik yang diizinkan di tengah. Panjang maksimum adalah 80 karakter.
  - `[GalleryApplicationVersionName <String>]`: Nama Galeri Versi Aplikasi yang akan dibuat. Perlu mengikuti pola nama versi semantik: Karakter yang diizinkan adalah digit dan titik. Digit harus berada dalam rentang bilangan bulat 32-bit. Format: <MajorVersion>.<MinorVersion>.<Patch>
  - `[GalleryImageName <String>]`: Nama definisi gambar galeri yang akan dibuat atau diperbarui. Karakter yang diizinkan adalah alfabet dan angka dengan titik, tanda hubung, dan titik yang diizinkan di tengah. Panjang maksimum adalah 80 karakter.
  - `[GalleryImageVersionName <String>]`: Nama versi gambar galeri yang akan dibuat. Perlu mengikuti pola nama versi semantik: Karakter yang diizinkan adalah digit dan titik. Digit harus berada dalam rentang bilangan bulat 32-bit. Format: <MajorVersion>.<MinorVersion>.<Patch>
  - `[GalleryName <String>]`: Nama Shared Image Gallery. Karakter yang diperbolehkan adalah alfabet dan angka dengan titik dan titik yang diizinkan di tengah. Panjang maksimum adalah 80 karakter.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InstanceId <String>]`: ID instans komputer virtual.
  - `[Location <String>]`: Lokasi tempat perintah eksekusi dikueri.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[RunCommandName <String>]`: Nama perintah eksekusi komputer virtual.
  - `[SubscriptionId <String>]`: Kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.
  - `[VMName <String>]`: Nama komputer virtual tempat perintah jalankan harus dibuat atau diperbarui.
  - `[VMScaleSetName <String>]`: Nama set skala VM.

## RELATED LINKS

