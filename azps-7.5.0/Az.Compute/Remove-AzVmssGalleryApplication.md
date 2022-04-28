---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/remove-azvmssgalleryapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzVmssGalleryApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzVmssGalleryApplication.md
ms.openlocfilehash: dd928a05e0f675121bfb41148d055b7d169cace2
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144209423"
---
# Remove-AzVmssGalleryApplication

## SYNOPSIS
Hapus objek VMGalleryApplication dari objek PSVirtualMachineScaleSetVMProfile.

## SYNTAX

```
Remove-AzVmssGalleryApplication -VirtualMachineScaleSetVM <PSVirtualMachineScaleSetVMProfile>
 -GalleryApplicationsReferenceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Menghapus objek VMGalleryApplication dari objek PSVirtualMachineScaleSetVMProfile.

## EXAMPLES

### Contoh 1
```powershell
$vmss = Get-AzVmss -ResourceGroupName $rgname -Name $vmssName
Remove-AzVmssGalleryApplication -VirtualMachineScaleSetVM $vmss.VirtualMachineProfile -GalleryApplicationsReferenceId $refId
```

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

### -GalleryApplicationsReferenceId
Id Referensi Paket dari Aplikasi Galeri yang akan dihapus.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachineScaleSetVM
Objek PSVirtualMachineScaleSetVMProfile untuk menghapus ID Referensi Aplikasi Galeri dari.

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
