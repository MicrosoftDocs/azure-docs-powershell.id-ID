---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmgalleryapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVmGalleryApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVmGalleryApplication.md
ms.openlocfilehash: cf1953a69d8c92d2820e9c626fa9176d8089d347
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145734292"
---
# New-AzVmGalleryApplication

## SYNOPSIS
Buat objek PSVMGalleryApplication lokal.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/new-azvmgalleryapplication) untuk informasi terbaru.

## SYNTAX

```
New-AzVmGalleryApplication -PackageReferenceId <String> [-ConfigReferenceId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek PSVMGalleryApplication lokal.

## EXAMPLES

### Contoh 1
```powershell
$vm = Get-AzVm -ResourceGroupName $rgName -Name $vmName
$vmGal = New-AzVmGalleryApplication -PackageReferenceId $packageRefId -ConfigReferenceId $configRefId
Add-AzVmGalleryApplication -VM $vm -GalleryApplication $vmGal -Order 1
```

Contoh ini membuat objek VMGalleryApplication lokal dan menambahkannya ke objek PSVirtualMachine.

## PARAMETERS

### -ConfigReferenceId
Id Referensi Konfigurasi Aplikasi Galeri.

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
Id Referensi Paket dari Aplikasi Galeri.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVMGalleryApplication

## NOTES

## RELATED LINKS
