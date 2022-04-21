---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 63D48BA4-EE80-4740-90B9-0EE05B3F6536
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azvmssvm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVmssVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVmssVM.md
ms.openlocfilehash: 857775cc971c3cab4ba9bb5fdd4ba43df2c34227
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142809820"
---
# Get-AzVmssVM

## SYNOPSIS
Mendapatkan properti mesin virtual VMSS.

## SYNTAX

### DefaultParameter (Default)
```
Get-AzVmssVM [[-ResourceGroupName] <String>] [[-VMScaleSetName] <String>] [[-InstanceId] <String>] [-UserData]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### FriendMethod
```
Get-AzVmssVM [[-ResourceGroupName] <String>] [[-VMScaleSetName] <String>] [[-InstanceId] <String>]
 [-InstanceView] [-UserData] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVmssVM** mendapatkan tampilan model dan tampilan instans mesin virtual Virtual Machine Scale Set (VMSS).
Tampilan model adalah properti mesin virtual yang ditentukan pengguna.
Tampilan instans adalah status tingkat instans mesin virtual.
Tentukan parameter *Status* untuk mendapatkan hanya tampilan instans mesin virtual.

## EXAMPLES

### Contoh 1: Dapatkan properti mesin virtual VMSS
```powershell
Get-AzVmssVM -ResourceGroupName "Group001" -VMScaleSetName "VMSS001"
```

Perintah ini mendapatkan properti mesin virtual VMSS bernama VMSS001 yang termasuk dalam grup sumber daya bernama Group001.
Karena perintah tidak menentukan parameter switch *InstanceView* , cmdlet mendapatkan tampilan model mesin virtual.

### Contoh 2: Dapatkan properti tampilan model mesin virtual VMSS
```powershell
Get-AzVmssVM -ResourceGroupName "Group002" -VMScaleSetName "VMSS004" -InstanceId $ID
```

Perintah ini mendapatkan properti mesin virtual VMSS bernama VMSS004 yang termasuk dalam grup sumber daya bernama Group002.
Perintah mendapatkan ID instans yang disimpan dalam variabel $ID untuk mendapatkan tampilan model.

### Contoh 3: Dapatkan properti tampilan instans dari mesin virtual VMSS
```powershell
Get-AzVmssVM -InstanceView  -ResourceGroupName $rgname  -VMScaleSetName $vmssName -InstanceId $ID
```

Perintah ini mendapatkan properti mesin virtual VMSS bernama VMSS004 yang termasuk dalam grup sumber daya bernama Group002.
Karena perintah menentukan parameter sakelar *InstanceView* , cmdlet mendapatkan tampilan instans mesin virtual.
Perintah mendapatkan ID instans yang disimpan dalam variabel $ID untuk mendapatkan tampilan instans.

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

### -InstanceId
Menentukan ID instans untuk mendapatkan tampilan model.

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
Menunjukkan bahwa cmdlet ini hanya mendapatkan tampilan instans mesin virtual.

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
Menentukan nama Grup Sumber Daya dari VMSS.

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

### -UserData
UserData untuk Vmss, yang akan dikodekan basis 64. Pelanggan tidak boleh memberikan rahasia apa pun di sini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSetVM

## NOTES

## RELATED LINKS

[Set-AzVmssVM](./Set-AzVmssVM.md)

[Get-AzVmss](./Get-AzVmss.md)


