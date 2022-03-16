---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 91B2DE2F-442D-4428-8A6F-9C2CEC181CA7
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmsourceimage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMSourceImage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMSourceImage.md
ms.openlocfilehash: bbc8c987e2bfbc32f42065527fa69bd0bd256ce6
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140091683"
---
# Set-AzVMSourceImage

## SYNOPSIS
Menentukan gambar untuk mesin virtual.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.compute/set-azvmsourceimage) untuk informasi terkini.

## SYNTAX

### ImageReferenceSkuParameterSet (Default)
```
Set-AzVMSourceImage [-VM] <PSVirtualMachine> [-PublisherName] <String> [-Offer] <String> [-Skus] <String>
 [-Version] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ImageReferenceIdParameterSet
```
Set-AzVMSourceImage [-VM] <PSVirtualMachine> [-Id] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMSourceImage** menentukan gambar platform yang akan digunakan untuk mesin virtual.

## EXAMPLES

### Contoh 1: Mengatur nilai untuk gambar
```
PS C:\> $AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id 
PS C:\> Set-AzVMSourceImage -VM $VirtualMachine -PublisherName "MicrosoftWindowsServer" -Offer "WindowsServer" -Skus "2012-R2-Datacenter" -Version "latest"
```

Perintah pertama mendapatkan ketersediaan yang diatur bernama AvailabilitySet03 dalam grup sumber daya yang bernama ResourceGroup11, lalu menyimpan objek tersebut di $AvailabilitySet sumber daya.
Perintah kedua membuat objek mesin virtual, lalu menyimpannya di $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Mesin virtual tersebut merupakan bagian dari kumpulan ketersediaan yang disimpan di $AvailabilitySet.
Perintah terakhir mengatur nilai untuk nama penerbit, penawaran, SKU, dan versi.
Cmdlet **Get-AzVMImagePublisher**, **Get-AzVMImageOffer**, **Get-AzVMImageSku**, dan **Get-AzVMImage** dapat menemukan pengaturan ini.

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

### -Id
Menentukan ID.

```yaml
Type: System.String
Parameter Sets: ImageReferenceIdParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Offer
Menentukan tipe penawaran VMImage.
Untuk mendapatkan penawaran gambar, gunakan cmdlet Get-AzVMImageOffer.

```yaml
Type: System.String
Parameter Sets: ImageReferenceSkuParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublisherName
Menentukan nama penerbit VMImage.
Untuk mendapatkan penerbit, gunakan cmdlet Get-AzVMImagePublisher.

```yaml
Type: System.String
Parameter Sets: ImageReferenceSkuParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Skus
Menentukan VMImage SKU.
Untuk mendapatkan SKU, gunakan Get-AzVMImageSku cmdlet.

```yaml
Type: System.String
Parameter Sets: ImageReferenceSkuParameterSet
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Versi
Menentukan versi VMImage.
Untuk menggunakan versi terbaru, tentukan nilai terbaru dan bukan versi tertentu.

```yaml
Type: System.String
Parameter Sets: ImageReferenceSkuParameterSet
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual lokal untuk dikonfigurasi.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Get-AzAvailabilitySet](./Get-AzAvailabilitySet.md)

[Get-AzvMImage](./Get-AzVMImage.md)

[Get-AzvMImageOffer](./Get-AzVMImageOffer.md)

[Get-AzVMImagePublisher](./Get-AzVMImagePublisher.md)

[Get-azvmImagesku](./Get-AzVMImageSku.md)

[New-azvmConfig](./New-AzVMConfig.md)


