---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 63D48BA4-EE80-4740-90B9-0EE05B3F6536
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/get-azvmssvm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/Get-AzVmssVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/Get-AzVmssVM.md
ms.openlocfilehash: 33847b9a86d5fa39511102e964f8f2a63fce6960
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136013134"
---
# Get-AzVmssVM

## SYNOPSIS
Mendapatkan properti mesin virtual VMSS.

## SINTAKS

### DefaultParameter (Default)
```
Get-AzVmssVM [[-ResourceGroupName] <String>] [[-VMScaleSetName] <String>] [[-InstanceId] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### FriendMethod
```
Get-AzVmssVM [[-ResourceGroupName] <String>] [[-VMScaleSetName] <String>] [[-InstanceId] <String>]
 [-InstanceView] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzVmssVM** mendapatkan tampilan model dan tampilan contoh mesin virtual Virtual Machine Scale Set (VMSS).
Tampilan model adalah properti komputer virtual yang ditentukan pengguna.
Tampilan contoh adalah status tingkat contoh mesin virtual.
Tentukan parameter *Status* untuk mendapatkan hanya tampilan contoh mesin virtual.

## CONTOH

### Contoh 1: Mendapatkan properti mesin virtual VMSS
```
PS C:\> Get-AzVmssVM -ResourceGroupName "Group001" -VMScaleSetName "VMSS001"
```

Perintah ini memiliki properti mesin virtual VMSS bernama VMSS001 yang dimiliki oleh grup sumber daya bernama Group001.
Karena perintah tidak menentukan parameter *sakelar InstanceView,* cmdlet mendapatkan tampilan model mesin virtual.

### Contoh 2: Mendapatkan properti tampilan model mesin virtual VMSS
```
PS C:\> Get-AzVmssVM -ResourceGroupName "Group002" -VMScaleSetName "VMSS004" -InstanceId $ID
```

Perintah ini memiliki properti mesin virtual VMSS bernama VMSS004 yang dimiliki oleh grup sumber daya bernama Group002.
Perintah akan mendapatkan ID instans yang disimpan di $ID variabel untuk mendapatkan tampilan model.

### Contoh 3: Mendapatkan properti tampilan instans mesin virtual VMSS
```
PS C:\> Get-AzVmssVM -InstanceView  -ResourceGroupName $rgname  -VMScaleSetName $vmssName -InstanceId $ID
```

Perintah ini memiliki properti mesin virtual VMSS bernama VMSS004 yang dimiliki oleh grup sumber daya bernama Group002.
Karena perintah menentukan parameter *sakelar InstanceView,* cmdlet mendapatkan tampilan contoh mesin virtual.
Perintah akan mendapatkan ID instans yang disimpan di $ID variabel untuk mendapatkan tampilan instans.

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

### -InstanceId
Menentukan ID instans yang akan digunakan untuk mendapatkan tampilan model.

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

### -InstanceView
Mengindikasikan bahwa cmdlet ini hanya mendapatkan tampilan contoh mesin virtual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FriendMethod
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama Grup Sumber Daya VMSS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMScaleSetName
Spesies nama VMSS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachinescaleSetVM

## CATATAN

## LINK TERKAIT

[Set-AzVmssVM](./Set-AzVmssVM.md)

[Get-AzVmss](./Get-AzVmss.md)


