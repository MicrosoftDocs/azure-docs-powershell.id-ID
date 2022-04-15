---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/start-azvmssrollingextensionupgrade
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Start-AzVmssRollingExtensionUpgrade.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Start-AzVmssRollingExtensionUpgrade.md
ms.openlocfilehash: 708be2223d800f0b6441be52cf73af6d305661e6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142258927"
---
# Start-AzVmssRollingExtensionUpgrade

## SYNOPSIS
Cmdlet ini memulai pemutakhiran bergulir untuk semua ekstensi pada Kumpulan Skala Mesin Virtual tertentu ke versi terbaru yang tersedia. 

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/start-azvmssrollingextensionupgrade) untuk informasi terbaru.

## SYNTAX

### DefaultParameter
```
Start-AzVmssRollingExtensionUpgrade -ResourceGroupName <String> -VMScaleSetName <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject
```
Start-AzVmssRollingExtensionUpgrade -VirtualMachineScaleSet <PSVirtualMachineScaleSet> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByResourceId
```
Start-AzVmssRollingExtensionUpgrade -ResourceId <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memulai pemutakhiran bergulir untuk memindahkan semua ekstensi pada skala mesin virtual ini diatur ke versi terbaru yang tersedia.
Ekstensi yang sudah menjalankan versi terbaru yang tersedia tidak terpengaruh.

## EXAMPLES

### Contoh 1
```powershell
$vmss = Get-AzVM -ResourceGroupName "MyResourceGroupName" -VMScaleSetName "MyVmssName";
Add-AzVmssExtension -VirtualMachineScaleSet $vmss -Name "testExtension" -Publisher Microsoft.CPlat.Core -Type "NullWindows" -TypeHandlerVersion "3.0" -AutoUpgradeMinorVersion $True  -Setting "";
Start-AzVmssRollingExtensionUpgrade -ResourceGroupName "MyResourceGroupName" -VMScaleSetName "MyVmssName";
```

Contoh ini mendapatkan kumpulan skala VM yang sudah ada "MyVmssName", dan menambahkan ekstensi ke dalamnya. Perintah akhir menjalankan proses pemutakhiran bergulir ekstensi. 

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya dari objek kumpulan skala VM. 

```yaml
Type: System.String
Parameter Sets: ByResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Objek kumpulan skala VM.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMScaleSetName
Nama kumpulan skala VM.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSOperationStatusResponse

## CATATAN

## RELATED LINKS
