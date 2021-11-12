---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 3CE367B1-7685-4046-8E9C-CE680B5AE03F
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/add-azvmsshpublickey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/Add-AzVMSshPublicKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/Add-AzVMSshPublicKey.md
ms.openlocfilehash: e17b495147c308d20d6d5b950914d26ce56a5706
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132410064"
---
# Add-AzVMSshPublicKey

## SYNOPSIS
Menambahkan kunci publik untuk KEYS untuk mesin virtual, ketika hanya membuat VM.

## SINTAKS

```
Add-AzVMSshPublicKey [-VM] <PSVirtualMachine> [[-KeyData] <String>] [[-Path] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Add-AzVMSshPublicKey** menambahkan kunci publik yang dapat Anda gunakan untuk menyambungkan ke mesin virtual Linux melalui Secure Shell (SHELL). Hal ini tidak dapat digunakan setelah pembuatan VM, jika Anda mencoba menggunakan ini setelah pembuatan VM tanpa Update-AzVM, tidak akan ada kesalahan, jika Anda menggunakan perintah dengan Update-AzVM, perintah akan muncul kesalahan.

## CONTOH

### Contoh 1: Menambahkan kunci publik ke mesin virtual
```
PS C:\> $VirtualMachine = Get-AzVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07"
PS C:\> $VirtualMachine = Add-AzVMSshPublicKey -VM $VirtualMachine -KeyData "MIIDszCCApugAwIBAgIJALBV9YJCF/tAMA0GCSq12Ib3DQEB21QUAMEUxCzAJBgNV" -Path "/home/admin/.ssh/authorized_keys"
```

Perintah pertama mendapatkan mesin virtual bernama VirtualMachine07 menggunakan cmdlet **Get-AzVM.**
Perintah menyimpan mesin virtual di $VirtualMachine variabel.
Perintah kedua menambahkan kunci publik ke lokasi di VirtualMachine07 yang ditentukan parameter Jalur.

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

### -KeyData
Menentukan pengodean basis 64 dari kunci publik.
Anda dapat menyambungkan ke mesin virtual Linux menggunakan LINUX atau menggunakan kunci yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Menentukan jalur lengkap file, di komputer virtual, tempat cmdlet ini menyimpan kunci publik JPG.
Jika file sudah ada, cmdlet ini akan menambahkan kunci ke file.

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

### -VM
Menentukan objek mesin virtual yang telah dimodifikasi cmdlet ini.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet [Get-AzVM.](./Get-AzVM.md)
Anda dapat menggunakan cmdlet [New-AzVMConfig](./New-AzVMConfig.md) untuk membuat objek mesin virtual.

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

## INPUT

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## LINK TERKAIT

[Get-azvm](./Get-AzVM.md)

[New-azvmConfig](./New-AzVMConfig.md)
