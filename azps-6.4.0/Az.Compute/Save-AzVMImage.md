---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: D2B5BC27-6D51-45BC-AE6A-F7FED11B8651
online version: https://docs.microsoft.com/powershell/module/az.compute/save-azvmimage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Save-AzVMImage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Save-AzVMImage.md
ms.openlocfilehash: fc817468bac319ae594f38c3266a79bdaaba63da
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136193433"
---
# Save-AzVMImage

## SYNOPSIS
Menyimpan mesin virtual sebagai VMImage.

## SYNTAX

### ResourceGroupNameParameterSetName (Default)
```
Save-AzVMImage [-Name] <String> [-DestinationContainerName] <String> [-VHDNamePrefix] <String> [-Overwrite]
 [[-Path] <String>] [-ResourceGroupName] <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### IdParameterSetName
```
Save-AzVMImage [-DestinationContainerName] <String> [-VHDNamePrefix] <String> [-Overwrite] [[-Path] <String>]
 [-Id] <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Save-AzVMImage** menyimpan mesin virtual sebagai VMImage.
Sebelum Anda membuat gambar mesin virtual, sysprep mesin virtual, lalu menandainya sebagai umum dengan menggunakan cmdlet Set-AzVM baru.
Output cmdlet ini adalah templat JavaScript Object Notation (JSON).
Anda dapat menggunakan mesin virtual dari gambar yang diambil.

## EXAMPLES

### Contoh 1: Mengambil gambar mesin virtual
```
PS C:\> Set-AzVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07" -Generalized 
PS C:\> Save-AzVMImage -ResourceGroupName "ResourceGroup11" -VMName "VirtualMachine07" -DestinationContainerName "VMContainer01" -VHDNamePrefix "VM07"
```

Perintah pertama menandai mesin virtual bernama VirtualMachine07 sebagai umum.
Perintah kedua mengambil gambar mesin virtual bernama VirtualMachine07 sebagai VMImage.
Properti **Output** mengembalikan templat JSON.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang dan kembalikan Pekerjaan untuk melacak kemajuan.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationContainerName
Menentukan nama wadah di dalam wadah "sistem" yang ingin Anda tahan gambar Anda.
Jika wadah tidak ada, wadah dibuat untuk Anda.
Hard disk virtual (VHD) yang merupakan VMImage berada dalam wadah yang ditentukan oleh parameter ini.
Jika VHD tersebar di beberapa akun penyimpanan, cmdlet ini membuat satu wadah yang memiliki nama ini di setiap akun penyimpanan.
URL gambar yang disimpan mirip dengan: https:// \<storageAccountName\> .blob.core.windows.net/system/Microsoft.Compute/Images/ \<imagesContainer\> / \<vhdPrefix-osDisk\> .xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.vhd.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Menentukan ID Sumber Daya komputer virtual.

```yaml
Type: System.String
Parameter Sets: IdParameterSetName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama.

```yaml
Type: System.String
Parameter Sets: ResourceGroupNameParameterSetName
Aliases: VMName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Overwrite
Mengindikasikan bahwa cmdlet ini menimpa VHD yang memiliki prefiks yang sama dalam wadah tujuan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Jalur file tempat templat gambar yang diambil disimpan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya komputer virtual.

```yaml
Type: System.String
Parameter Sets: ResourceGroupNameParameterSetName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VHDNamePrefix
Menentukan prefiks dalam nama blob yang merupakan profil penyimpanan VMImage.
Misalnya, prefiks vhdPrefix untuk hasil disk sistem operasi dalam nama vhdPrefix-osdisk. \<guid\> . vhd.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: VirtualHardDiskNamePrefix

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSComputeLongRunningOperation

## CATATAN

## RELATED LINKS

[Get-AzvMImage](./Get-AzVMImage.md)

[Get-AzvMImageOffer](./Get-AzVMImageOffer.md)

[Get-AzVMImagePublisher](./Get-AzVMImagePublisher.md)

[Get-azvmImagesku](./Get-AzVMImageSku.md)

[Set-azvm](./Set-AzVM.md)


