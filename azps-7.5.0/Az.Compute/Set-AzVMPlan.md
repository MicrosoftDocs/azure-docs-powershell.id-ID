---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: A1EA7D34-A8B4-4FA0-BD8C-3E846715AFBA
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMPlan.md
ms.openlocfilehash: dba9e4f49084f181d9c4ec6efda07fe0780d982d
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145778196"
---
# Set-AzVMPlan

## SYNOPSIS
Mengatur informasi paket Marketplace pada komputer virtual.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/set-azvmplan) untuk informasi terbaru.

## SYNTAX

```
Set-AzVMPlan [-VM] <PSVirtualMachine> [-Name] <String> [[-Product] <String>] [[-PromotionCode] <String>]
 [[-Publisher] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMPlan** mengatur informasi rencana Marketplace Azure untuk komputer virtual.
Sebelum dapat menyebarkan gambar Marketplace melalui baris perintah, akses terprogram harus diaktifkan atau komputer virtual harus disebarkan dengan menggunakan portal Azure.

## EXAMPLES

### Contoh 1
```powershell
New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_B1s" |
    Set-AzVMPlan -Publisher "Canonical" -Product "UbuntuServer" -Name "18.04-LTS"
```

```Output
Name            : VirtualMachine07
HardwareProfile : {VmSize}
Plan            : {Name, Publisher, Product}
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Name
Menentukan nama gambar dari Marketplace.
Ini adalah nilai yang sama yang dikembalikan oleh cmdlet Get-AzVMImageSku.
Untuk informasi selengkapnya tentang cara menemukan informasi gambar, lihat [Menemukan dan menggunakan gambar VM Marketplace Azure dengan Azure PowerShell](/azure/virtual-machines/windows/cli-ps-findimage) dalam dokumentasi Microsoft Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Produk
Menentukan produk gambar dari Marketplace.
Ini adalah informasi yang sama dengan nilai **Penawaran** dari elemen **imageReference** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PromotionCode
Menentukan kode promosi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Menentukan penerbit gambar.
Anda dapat menemukan informasi ini dengan menggunakan cmdlet Get-AzVMImagePublisher.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan objek komputer virtual untuk mengatur paket Marketplace.
Anda dapat menggunakan cmdlet Get-AzVM untuk mendapatkan objek komputer virtual.
Anda dapat menggunakan cmdlet New-AzVMConfig untuk membuat objek komputer virtual.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## NOTES

## RELATED LINKS

[Dapatkan-AzVM](./Get-AzVM.md)

[Get-AzVMImagePublisher](./Get-AzVMImagePublisher.md)

[Get-AzVMImageSku](./Get-AzVMImageSku.md)

[New-AzVMConfig](./New-AzVMConfig.md)
