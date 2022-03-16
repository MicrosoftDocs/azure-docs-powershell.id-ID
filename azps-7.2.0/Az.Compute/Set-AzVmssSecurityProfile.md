---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmsssecurityprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssSecurityProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssSecurityProfile.md
ms.openlocfilehash: 930cf28f780445eaacf180ec6556bbf1c9e97203
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140272631"
---
# Set-AzVmssSecurityProfile

## SYNOPSIS
Cmdlet ini memungkinkan pengguna untuk mengatur enum SecurityType untuk kumpulan skala Komputer Virtual.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.compute/set-azvmsssecurityprofile) untuk informasi terkini.

## SYNTAX

```
Set-AzVmssSecurityProfile [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [[-SecurityType] <SecurityTypes>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mengatur Tipe Keamanan VMSS

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $VMSS = Get-AzVmss -ResourceGroupName "ResourceGroup11" -VMScaleSetName "ContosoVM07"
PS C:\> $VMSS = Set-AzVmssSecurityProfile -VirtualMachineScaleSet $VMSS -SecurityType "TrustedLaunch"
```

Perintah pertama mendapatkan skala mesin virtual yang diatur bernama ContosoVM07 dengan **menggunakan Get-AzVms.**
Perintah menyimpannya di $VMSS variabel.
Perintah kedua mengatur enum SecurityType menjadi "TrustedLaunch"

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

### -SecurityType
Enum yang mewakili tipe keamanan (sebagai: Peluncuran Tepercaya)

```yaml
Type: SecurityTypes
Parameter Sets: (All)
Aliases:
Accepted values: TrustedLaunch

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

### Microsoft.Azure.Management.Compute.Models.SecurityTypes

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## CATATAN

## RELATED LINKS
