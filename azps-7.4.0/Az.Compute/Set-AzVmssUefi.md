---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmssuefi
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssUefi.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssUefi.md
ms.openlocfilehash: 40688e7f1461bbcdfe9a6d812b013f809d3a1531
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144658458"
---
# Set-AzVmssUefi

## SYNOPSIS
Memodifikasi properti UEFI dari komputer virtual gen 2 yang merupakan bagian dari set skala komputer virtual

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/set-azvmssuefi) untuk informasi terbaru.

## SYNTAX

```
Set-AzVmssUefi [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [[-EnableVtpm] <Boolean>]
 [[-EnableSecureBoot] <Boolean>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVmssUefi** memodifikasi properti UEFI komputer virtual dalam set skala komputer virtual. 

## EXAMPLES

### Contoh 1
```powershell
$VMSS = Get-AzVmss -ResourceGroupName "ResourceGroup11" -VMScaleSetName "ContosoVM07"
Set-AzVmssUefi -VirtualMachineScaleSet $VMSS -EnableVtpm $true -EnableSecureBoot $true
```

Perintah pertama mendapatkan set skala komputer virtual bernama ContosoVM07 dengan menggunakan **Get-AzVmss**.
Perintah menyimpannya dalam variabel $VMSS.
Perintah kedua memodifikasi pengaturan UEFI untuk mengaktifkan SecureBoot dan vTPM pada komputer virtual di $VMSS.
Perintah meneruskan hasil ke cmdlet Update-AzVmss, yang mengimplementasikan perubahan Anda.
Perubahan pada mode kasir menyebabkan komputer virtual dimulai ulang.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableSecureBoot
Parameter untuk beralih boot aman pada VM set skala

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableVtpm
Parameter untuk beralih vTPM pada VM dari set skala

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Profil set skala komputer virtual.

```yaml
Type: PSVirtualMachineScaleSet
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

### System.Boolean

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## NOTES

## RELATED LINKS
