---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: A1EA7D34-A8B4-4FA0-BD8C-3E846715AFBA
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/set-azurermvmplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/Set-AzureRmVMPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/Set-AzureRmVMPlan.md
ms.openlocfilehash: 0cd83ac19cc45ab9e45c5b6b3baa5039ad6b253bc5652319306843e1b1867d42
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415836"
---
# Set-AzureRmVMPlan

## SYNOPSIS
Mengatur informasi paket Marketplace di mesin virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmVMPlan [-VM] <PSVirtualMachine> [-Name] <String> [[-Product] <String>] [[-PromotionCode] <String>]
 [[-Publisher] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmVMPlan** mengatur informasi paket Azure Marketplace untuk komputer virtual.
Sebelum dapat menyebarkan gambar Marketplace melalui baris perintah, akses programatik harus diaktifkan atau mesin virtual harus digunakan menggunakan portal Azure.

## EXAMPLES

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
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
Nilai ini sama dengan yang dikembalikan oleh cmdlet Get-AzureRmVMImageSku cmdlet.
Untuk informasi selengkapnya tentang cara menemukan informasi gambar, lihat Menemukan dan menggunakan gambar [VM Azure Marketplace](/azure/virtual-machines/windows/cli-ps-findimage) dengan Azure PowerShell dalam Microsoft Azure dokumen.

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

### -Product
Menentukan produk gambar dari Marketplace.
Ini adalah informasi yang sama **dengan** nilai Penawaran **elemenreferensi** gambar.

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

### -Kode Promosi
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
Anda dapat menemukan informasi ini menggunakan cmdlet Get-AzureRmVMImagePublisher.

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
Menentukan objek mesin virtual yang akan digunakan untuk menetapkan paket Marketplace.
Anda dapat menggunakan cmdlet Get-AzureRmVM cmdlet untuk mendapatkan objek mesin virtual.
Anda dapat menggunakan cmdlet New-AzureRmVMConfig untuk membuat objek mesin virtual.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Get-AzureRmVM](./Get-AzureRmVM.md)

[Get-AzureRmVMImagePublisher](./Get-AzureRmVMImagePublisher.md)

[Get-AzureRmVMImageSku](./Get-AzureRmVMImageSku.md)

[New-AzureRmVMConfig](./New-AzureRmVMConfig.md)
