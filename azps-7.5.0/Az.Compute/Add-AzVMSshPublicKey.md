---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 3CE367B1-7685-4046-8E9C-CE680B5AE03F
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvmsshpublickey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVMSshPublicKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVMSshPublicKey.md
ms.openlocfilehash: e28064d4e5a7ff273279c8c6cde7724c27f3a56c
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144222635"
---
# Add-AzVMSshPublicKey

## SYNOPSIS
Menambahkan kunci publik untuk SSH untuk komputer virtual, saat hanya membuat VM.

## SYNTAX

```
Add-AzVMSshPublicKey [-VM] <PSVirtualMachine> [[-KeyData] <String>] [[-Path] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzVMSshPublicKey** menambahkan kunci umum yang dapat Anda gunakan untuk terhubung ke komputer virtual Linux melalui Secure Shell (SSH). Ini tidak dapat digunakan setelah pembuatan VM, jika Anda mencoba menggunakan ini setelah pembuatan VM tanpa Update-AzVM, tidak akan ada kesalahan, jika Anda menggunakan perintah dengan Update-AzVM, perintah akan mengalami kesalahan.

## EXAMPLES

### Contoh 1: Menambahkan kunci publik ke komputer virtual
```powershell
$VirtualMachine = Get-AzVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07"
$VirtualMachine = Add-AzVMSshPublicKey -VM $VirtualMachine -KeyData "MIIDszCCApugAwIBAgIJALBV9YJCF/tAMA0GCSq12Ib3DQEB21QUAMEUxCzAJBgNV" -Path "/home/admin/.ssh/authorized_keys"
```

Perintah pertama mendapatkan komputer virtual bernama VirtualMachine07 dengan menggunakan cmdlet **Get-AzVM** .
Perintah menyimpan komputer virtual dalam variabel $VirtualMachine.
Perintah kedua menambahkan kunci publik ke lokasi di VirtualMachine07 yang ditentukan parameter Path.

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

### -KeyData
Menentukan pengodean dasar 64 dari kunci publik.
Anda dapat terhubung ke komputer virtual Linux dengan menggunakan SSH atau dengan menggunakan kunci yang ditentukan parameter ini.

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

### -Jalur
Menentukan jalur lengkap file, pada komputer virtual, tempat cmdlet ini menyimpan kunci umum SSH.
Jika file sudah ada, cmdlet ini menambahkan kunci ke file.

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
Menentukan objek komputer virtual yang dimodifikasi cmdlet ini.
Untuk mendapatkan objek komputer virtual, gunakan cmdlet [Get-AzVM](./Get-AzVM.md) .
Anda dapat menggunakan cmdlet [New-AzVMConfig](./New-AzVMConfig.md) untuk membuat objek komputer virtual.

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

[New-AzVMConfig](./New-AzVMConfig.md)
