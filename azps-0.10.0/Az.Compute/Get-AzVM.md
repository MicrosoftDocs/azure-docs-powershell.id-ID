---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help-Help.xml
Module Name: Az.Compute
ms.assetid: 6250EC11-79CF-428B-A72F-9BD72C1751F0
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/get-azvm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Get-AzVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Get-AzVM.md
ms.openlocfilehash: 2f33b0dbee4f584553eac1047471adef08e3523b
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423543"
---
# Get-AzVM

## SYNOPSIS
Mendapatkan properti mesin virtual.

## SYNTAX

### ListAllVirtualMachinesParamSet (Default)
```
Get-AzVM [-Status] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ListVirtualMachineInResourceGroupParamSet
```
Get-AzVM [-ResourceGroupName] <String> [-Status] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetVirtualMachineInResourceGroupParamSet
```
Get-AzVM [-ResourceGroupName] <String> [-Name] <String> [-Status] [-DisplayHint <DisplayHintType>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ListNextLinkVirtualMachinesParamSet
```
Get-AzVM [-Status] [-NextLink] <Uri> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVM** mendapatkan tampilan model dan tampilan contoh mesin virtual Azure.
Tampilan model adalah properti komputer virtual yang ditentukan pengguna.
Tampilan contoh adalah status tingkat contoh mesin virtual.
Tentukan parameter *Status* untuk mendapatkan hanya tampilan contoh mesin virtual.

## EXAMPLES

### Contoh 1: Dapatkan properti tampilan model dan contoh
```
PS C:\> Get-AzVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07"
```

Perintah ini mendapatkan tampilan model dan properti tampilan contoh dari mesin virtual bernama VirtualMachine07.

### Contoh 2: Mendapatkan properti tampilan contoh
```
PS C:\> Get-AzVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07" -Status
```

Perintah ini mendapatkan properti dari mesin virtual bernama VirtualMachine07.
Perintah ini menentukan *parameter Status.*
Oleh karena itu, perintah hanya mendapatkan properti tampilan contoh.

### Contoh 3: Dapatkan properti untuk semua mesin virtual dalam grup sumber daya
```
PS C:\> Get-AzVM -ResourceGroupName "ResourceGroup11"
```

Perintah ini mendapatkan properti untuk semua mesin virtual dalam grup sumber daya bernama ResourceGroup11.

### Contoh 4: Mendapatkan semua mesin virtual dalam langganan Anda
```
PS C:\> Get-AzVM
```

Perintah ini akan mendapatkan semua mesin virtual dalam langganan Anda.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -DisplayHint
Menentukan cara objek mesin virtual ditampilkan.

Nilai valid adalah:

-- Ringkas: hanya menampilkan properti tingkat atas

-- Perluas: menampilkan semua properti dalam semua tingkat
```yaml
Type: DisplayHintType
Parameter Sets: GetVirtualMachineInResourceGroupParamSet
Aliases: 
Accepted values: Compact, Expand

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama mesin virtual yang akan dapatkan.

```yaml
Type: String
Parameter Sets: GetVirtualMachineInResourceGroupParamSet
Aliases: ResourceName, VMName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextLink
Menentukan tautan berikutnya.

```yaml
Type: Uri
Parameter Sets: ListNextLinkVirtualMachinesParamSet
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: String
Parameter Sets: ListVirtualMachineInResourceGroupParamSet, GetVirtualMachineInResourceGroupParamSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
Mengindikasikan bahwa cmdlet ini hanya mendapatkan tampilan contoh mesin virtual.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachineInstanceView

## CATATAN

## RELATED LINKS

[New-azvm](./New-AzVM.md)

[Remove-azvm](./Remove-AzVM.md)

[Mulai ulang-azvm](./Restart-AzVM.md)

[Start-azvm](./Start-AzVM.md)

[Stop-azvm](./Stop-AzVM.md)

[Update-azvm](./Update-AzVM.md)


