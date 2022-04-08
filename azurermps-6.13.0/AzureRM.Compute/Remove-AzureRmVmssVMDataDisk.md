---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/remove-azurermvmssvmdatadisk
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/Remove-AzureRmVmssVMDataDisk.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/Remove-AzureRmVmssVMDataDisk.md
ms.openlocfilehash: 266143a7ef5d68c90e3099726826a8cec72470ded26f6b7d99154fd81d2c02d6
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140855136"
---
# Remove-AzureRmVmssVMDataDisk

## SYNOPSIS
Menghapus disk data dari kumpulan skala mesin virtual VM

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmVmssVMDataDisk [-VirtualMachineScaleSetVM] <PSVirtualMachineScaleSetVM> [-Lun] <Int32>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmVmssVMDataDisk** menghapus disk data dari kumpulan skala VM

## EXAMPLES

### Contoh 1: Menghapus disk data dari kumpulan skala VM
```powershell
PS C:\> $VmssVM = Get-AzureRmVmssVM -ResourceGroupName "myrg" -VMScaleSetName "myvmss" -InstanceId 0 
PS C:\> Remove-AzureRmVmssVMDataDisk -VM $VirtualMachine -Lun 0
PS C:\> Update-AzureRmVmssVM -VirtualMachineScaleSetVM $VmssVM
```

Perintah pertama mendapatkan Vmss VM yang sudah ada yang diberikan oleh nama grup sumber daya, nama vmss dan ID instans.
Perintah kedua menghapus data disk lun 0 dari VM scale set VM yang disimpan dalam $VmssVM Perintah terakhir memperbarui Vmss VM dengan disk data yang dihapus.

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

### -Lun
Menentukan nomor unit logika disk.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -virtualMachinescaleSetvm
Profil VM yang mengatur skala mesin virtual.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSetVM
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachinescaleSetVM

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachinescaleSetVM

## CATATAN

## RELATED LINKS
