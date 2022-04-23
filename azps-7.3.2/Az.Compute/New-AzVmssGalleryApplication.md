---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmssgalleryapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVmssGalleryApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVmssGalleryApplication.md
ms.openlocfilehash: 093b787edf0498baf42fe4bcb9f51258e9dba96b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143186867"
---
# New-AzVmssGalleryApplication

## SYNOPSIS
Buat objek PSVMGalleryApplication lokal.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/new-azvmssgalleryapplication) untuk informasi terbaru.

## SYNTAX

```
New-AzVmssGalleryApplication -PackageReferenceId <String> [-ConfigReferenceId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek PSVMGalleryApplication lokal.

## EXAMPLES

### Contoh 1
```powershell
$vmss = Get-AzVmss -ResourceGroupName $rgName -Name $vmssName
$vmGal = New-AzVmssGalleryApplication -PackageReferenceId $packageRefId -ConfigReferenceId $configRefId
Add-AzVmssGalleryApplication -VM $vmss.VirtualMachineProfile -GalleryApplication $vmGal -Order 1
```

Contoh ini membuat objek VMGalleryApplication lokal dan menambahkannya ke objek PSVirtualMachineScaleSetVM.

## PARAMETERS

### -ConfigReferenceId
Id Referensi Konfigurasi dari Aplikasi Galeri.

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

### -PackageReferenceId
Id Referensi Paket Dari Aplikasi Galeri.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Management.Compute.Models.VMGalleryApplication

## NOTES

## RELATED LINKS
