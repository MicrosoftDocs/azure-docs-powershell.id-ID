---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 3CE367B1-7685-4046-8E9C-CE680B5AE03F
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Add-AzureRmVMSshPublicKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Add-AzureRmVMSshPublicKey.md
ms.openlocfilehash: 24c97e73728dab656a1d9fe3283e4eba6aae4ea2
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427341"
---
# Add-AzureRmVMSshPublicKey

## SYNOPSIS
Menambahkan kunci publik UNTUK KEYS untuk komputer virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmVMSshPublicKey [-VM] <PSVirtualMachine> [[-KeyData] <String>] [[-Path] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmVMSshPublicKey** menambahkan kunci publik yang dapat Anda gunakan untuk menyambungkan ke komputer virtual melalui Secure Shell (SHELL).

## EXAMPLES

### Contoh 1: Menambahkan kunci publik ke mesin virtual
```
PS C:\> $VirtualMachine = Get-AzureRmVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07"
PS C:\> $VirtualMachine = Add-AzureRmVMSshPublicKey -VM $VirtualMachine -KeyData "MIIDszCCApugAwIBAgIJALBV9YJCF/tAMA0GCSq12Ib3DQEB21QUAMEUxCzAJBgNV" -Path "/home/admin/.ssh/authorized_keys"
```

Perintah pertama mendapatkan mesin virtual bernama VirtualMachine07 menggunakan cmdlet **Get-AzureRmVM.**
Perintah menyimpan mesin virtual di $VirtualMachine variabel.

Perintah kedua menambahkan kunci publik ke lokasi di VirtualMachine07 yang ditentukan parameter Jalur.

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

### -KeyData
Menentukan pengodean basis 64 dari kunci publik.
Anda dapat menyambungkan ke mesin virtual dengan MENGGUNAKANJAWAB atau menggunakan kunci yang ditentukan parameter ini.

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
Untuk mendapatkan objek mesin virtual, gunakan cmdlet [Get-AzureRmVM.](./Get-AzureRmVM.md)
Anda dapat menggunakan cmdlet [New-AzureRmVMConfig](./New-AzureRmVMConfig.md) untuk membuat objek mesin virtual.

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

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRmVM](./Get-AzureRmVM.md)

[New-AzureRmVMConfig](./New-AzureRmVMConfig.md)
