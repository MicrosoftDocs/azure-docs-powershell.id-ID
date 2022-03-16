---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: A1EA7D34-A8B4-4FA0-BD8C-3E846715AFBA
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMPlan.md
ms.openlocfilehash: 15ef2e289e3d4ecf031ef8f43e9db9948b171742
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140188421"
---
# Set-AzVMPlan

## SYNOPSIS
Mengatur informasi paket Marketplace di mesin virtual.

## SYNTAX

```
Set-AzVMPlan [-VM] <PSVirtualMachine> [-Name] <String> [[-Product] <String>] [[-PromotionCode] <String>]
 [[-Publisher] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMPlan** mengatur informasi paket Azure Marketplace untuk mesin virtual.
Sebelum dapat menyebarkan gambar Marketplace melalui baris perintah, akses programatik harus diaktifkan atau mesin virtual harus digunakan menggunakan portal Azure.

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

### -Nama
Menentukan nama gambar dari Marketplace.
Nilai ini sama dengan yang dikembalikan oleh cmdlet Get-AzVMImageSku.
Untuk informasi selengkapnya tentang cara menemukan informasi gambar, lihat Menemukan dan menggunakan gambar [VM Azure Marketplace dengan Azure PowerShell](/azure/virtual-machines/windows/cli-ps-findimage) dalam Microsoft Azure ter dokumentasi.

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
Anda dapat menemukan informasi ini menggunakan cmdlet Get-AzVMImagePublisher.

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
Anda dapat menggunakan cmdlet Get-AzVM untuk mendapatkan objek mesin virtual.
Anda dapat menggunakan cmdlet New-AzVMConfig untuk membuat objek mesin virtual.

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

[Get-azvm](./Get-AzVM.md)

[Get-AzVMImagePublisher](./Get-AzVMImagePublisher.md)

[Get-azvmImagesku](./Get-AzVMImageSku.md)

[New-azvmConfig](./New-AzVMConfig.md)
