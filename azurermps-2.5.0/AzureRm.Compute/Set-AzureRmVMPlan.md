---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: A1EA7D34-A8B4-4FA0-BD8C-3E846715AFBA
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/set-azurermvmplan
schema: 2.0.0
ms.openlocfilehash: 6d9a739156d3a4beb0d0dd86f3d7a96086d9fc32
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142147555"
---
# Set-AzureRmVMPlan

## SYNOPSIS
Mengatur informasi rencana Marketplace di mesin virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmVMPlan [-VM] <PSVirtualMachine> [-Name] <String> [[-Product] <String>] [[-PromotionCode] <String>]
 [[-Publisher] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmVMPlan** mengatur informasi rencana Azure Marketplace untuk mesin virtual.

Sebelum dapat menyebarkan gambar Marketplace melalui baris perintah, akses programatik harus diaktifkan atau mesin virtual harus disebarkan menggunakan portal Azure.

## EXAMPLES

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama gambar dari Marketplace.
Ini adalah nilai yang sama yang dikembalikan oleh cmdlet Get-AzureRmVMImageSku.
Untuk informasi selengkapnya tentang cara menemukan informasi gambar, lihat [Menemukan dan menggunakan gambar VM Azure Marketplace dengan Azure PowerShell](/azure/virtual-machines/windows/cli-ps-findimage) dalam dokumentasi Microsoft Azure.

```yaml
Type: String
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
Type: String
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
Type: String
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
Anda bisa menemukan informasi ini dengan menggunakan cmdlet Get-AzureRmVMImagePublisher.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual untuk mengatur rencana Marketplace.
Anda dapat menggunakan cmdlet Get-AzureRmVM untuk mendapatkan objek mesin virtual.
Anda dapat menggunakan cmdlet New-AzureRmVMConfig untuk membuat objek mesin virtual.

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSVirtualMachine
Parameter 'VM' menerima nilai tipe 'PSVirtualMachine' dari pipeline

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Get-AzureRmVM](./Get-AzureRmVM.md)

[Get-AzureRmVMImagePublisher](./Get-AzureRmVMImagePublisher.md)

[Get-AzureRmvmImagesku](./Get-AzureRmVMImageSku.md)

[AzureRmVMConfig Baru](./New-AzureRmVMConfig.md)
