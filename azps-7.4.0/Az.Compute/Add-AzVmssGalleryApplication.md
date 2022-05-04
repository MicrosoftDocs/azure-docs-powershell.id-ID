---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvmssgalleryapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssGalleryApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssGalleryApplication.md
ms.openlocfilehash: e4cd7939938398b510eddec8cc2c1484e1ea942a
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144633446"
---
# Add-AzVmssGalleryApplication

## SYNOPSIS
Tambahkan objek GalleryApplication ke objek PSVirtualMachineProfile.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/add-azvmssgalleryapplication) untuk informasi terbaru.

## SYNTAX

```
Add-AzVmssGalleryApplication -VirtualMachineScaleSetVM <PSVirtualMachineScaleSetVMProfile>
 -GalleryApplication <PSVMGalleryApplication> [-Order <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Menambahkan objek GalleryApplication ke objek PSVirtualMachineProfile.

## EXAMPLES

### Contoh 1
```powershell
$vmss = Get-AzVmss -ResourceGroupName $rgName -Name $vmssName
$vmGal = New-AzVmssGalleryApplication -PackageReferenceId $packageRefId -ConfigReferenceId $configRefId
Add-AzVmssGalleryApplication -VM $vmss.VirtualMachineProfile -GalleryApplication $vmGal -Order 1
```

Contoh ini membuat objek VMGalleryApplication lokal dan menambahkannya ke objek PSVirtualMachineScaleSetVM.

## PARAMETERS

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

### -GalleryApplication
Objek Aplikasi Galeri VM.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVMGalleryApplication
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pesanan
Urutan tempat aplikasi akan diinstal.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachineScaleSetVM
Objek PSVirtualMachineScaleSetVMProfile untuk menambahkan ID Referensi Aplikasi Galeri.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSetVMProfile
Parameter Sets: (All)
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSetVMProfile

## NOTES

## RELATED LINKS
