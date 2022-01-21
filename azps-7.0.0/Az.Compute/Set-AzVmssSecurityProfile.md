---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmsssecurityprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssSecurityProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssSecurityProfile.md
ms.openlocfilehash: 54973b0916094ca293117460cd7c522a2152a41f
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136553795"
---
# Set-AzVmssSecurityProfile

## SYNOPSIS
Cmdlet ini memungkinkan pengguna untuk mengatur enum SecurityType untuk kumpulan skala Komputer Virtual.

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

Perintah pertama mendapatkan skala mesin virtual yang diatur bernama ContosoVM07 dengan **menggunakan Get-AzVmss**.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

### Microsoft.Azure.Management.Compute.Models.SecurityTypes

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## CATATAN

## RELATED LINKS
