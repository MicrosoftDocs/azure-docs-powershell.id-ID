---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmssuefi
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssUefi.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssUefi.md
ms.openlocfilehash: 55f8c9958f848fa32bbb49a2226c0e590d39b2f6
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140078813"
---
# Set-AzVmssUefi

## SYNOPSIS
Mengubah properti UEFI mesin virtual gen 2 yang merupakan bagian dari set skala mesin virtual

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.compute/set-azvmssuefi) untuk informasi terkini.

## SYNTAX

```
Set-AzVmssUefi [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [[-EnableVtpm] <Boolean>]
 [[-EnableSecureBoot] <Boolean>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVmssUefi** mengubah properti mesin virtual UEFI dalam kumpulan skala mesin virtual. 

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $VMSS = Get-AzVmss -ResourceGroupName "ResourceGroup11" -VMScaleSetName "ContosoVM07"
PS C:\> Set-AzVmssUefi -VirtualMachineScaleSet $VMSS -EnableVtpm $true -EnableSecureBoot $true
```

Perintah pertama mendapatkan skala mesin virtual yang diatur bernama ContosoVM07 dengan **menggunakan Get-AzVms.**
Perintah menyimpannya di $VMSS variabel.
Perintah kedua memodifikasi pengaturan UEFI untuk mengaktifkan SecureBoot dan vTPM pada mesin virtual di $VMSS.
Perintah melewati hasil ke cmdlet Update-AzVmss, yang mengimplementasikan perubahan Anda.
Perubahan pada mode kas menyebabkan mesin virtual memulai ulang.

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
Parameter untuk mengaktifkan boot aman pada VM kumpulan skala

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
Parameter untuk mengaktifkan vTPM pada VM dari kumpulan skala

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

### -VirtualMachinescaleSet
Profil kumpulan skala mesin virtual.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

### System.Boolean

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## CATATAN

## RELATED LINKS
