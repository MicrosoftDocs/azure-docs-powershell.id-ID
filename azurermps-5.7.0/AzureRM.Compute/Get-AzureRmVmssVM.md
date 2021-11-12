---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
ms.assetid: 63D48BA4-EE80-4740-90B9-0EE05B3F6536
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Get-AzureRmVmssVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Get-AzureRmVmssVM.md
ms.openlocfilehash: 8d24aadd185a58472268fc4edf9ca504e7592bb0
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423776"
---
# Get-AzureRmVmssVM

## SYNOPSIS
Mendapatkan properti mesin virtual VMSS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### DefaultParameter (Default)
```
Get-AzureRmVmssVM [[-ResourceGroupName] <String>] [[-VMScaleSetName] <String>] [[-InstanceId] <String>]
 [<CommonParameters>]
```

### FriendMethod
```
Get-AzureRmVmssVM [[-ResourceGroupName] <String>] [[-VMScaleSetName] <String>] [[-InstanceId] <String>]
 [-InstanceView] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmVmssVM** mendapatkan tampilan model dan tampilan contoh mesin virtual Virtual Machine Scale Set (VMSS).
Tampilan model adalah properti komputer virtual yang ditentukan pengguna.
Tampilan contoh adalah status tingkat contoh mesin virtual.
Tentukan parameter *Status* untuk mendapatkan hanya tampilan contoh mesin virtual.

## EXAMPLES

### Contoh 1: Mendapatkan properti mesin virtual VMSS
```
PS C:\> Get-AzureRmVmssVM -ResourceGroupName "Group001" -VMScaleSetName "VMSS001"
```

Perintah ini memiliki properti mesin virtual VMSS bernama VMSS001 yang dimiliki oleh grup sumber daya bernama Group001.
Karena perintah tidak menentukan parameter *sakelar InstanceView,* cmdlet mendapatkan tampilan model mesin virtual.

### Contoh 2: Mendapatkan properti tampilan model mesin virtual VMSS
```
PS C:\> Get-AzureRmVmssVM -ResourceGroupName "Group002" -VMScaleSetName "VMSS004" -InstanceId $ID
```

Perintah ini memiliki properti mesin virtual VMSS bernama VMSS004 yang dimiliki oleh grup sumber daya bernama Group002.
Perintah akan mendapatkan ID instans yang disimpan di $ID untuk mendapatkan tampilan model.

### Contoh 3: Mendapatkan properti tampilan instans mesin virtual VMSS
```
PS C:\> Get-AzureRmVmssVM -InstanceView  -ResourceGroupName $rgname  -VMScaleSetName $vmssName -InstanceId $ID
```

Perintah ini memiliki properti mesin virtual VMSS bernama VMSS004 yang dimiliki oleh grup sumber daya bernama Group002.
Karena perintah menentukan parameter *sakelar InstanceView,* cmdlet mendapatkan tampilan contoh mesin virtual.
Perintah akan mendapatkan ID instans yang disimpan di $ID variabel untuk mendapatkan tampilan instans.

## PARAMETERS

### -InstanceId
Menentukan ID instans yang akan digunakan untuk mendapatkan tampilan model.

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

### -InstanceView
Mengindikasikan bahwa cmdlet ini hanya mendapatkan tampilan contoh mesin virtual.

```yaml
Type: SwitchParameter
Parameter Sets: FriendMethod
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama Grup Sumber Daya VMSS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMScaleSetName
Spesies nama VMSS.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Cmdlet ini tidak menghasilkan output apa pun.

## CATATAN

## RELATED LINKS

[Set-AzureRmVmssVM](./Set-AzureRmVmssVM.md)

[Get-AzureRmVmss](./Get-AzureRmVmss.md)


