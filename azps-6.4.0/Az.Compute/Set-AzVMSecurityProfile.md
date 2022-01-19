---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmsecurityprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMSecurityProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMSecurityProfile.md
ms.openlocfilehash: 112ea9a75e6d76c858e474375c5a8c81c1aee2ea
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136205414"
---
# Set-AzVMSecurityProfile

## SYNOPSIS
Mengatur enum SecurityType untuk Mesin Virtual.

## SYNTAX

```
Set-AzVMSecurityProfile [-VM] <PSVirtualMachine> [-SecurityType <SecurityTypes>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVmSecurityProfile** mengatur Tipe Keamanan VM

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $VM = Get-AzVM -ResourceGroupName "ResourceGroup11" -VMName "ContosoVM07"
PS C:\> $VM = Set-AzVmSecurityProfile -VM $VM -SecurityType "TrustedLaunch"
```

Perintah pertama mendapatkan mesin virtual bernama ContosoVM07 dengan menggunakan **Get-AzVm**.
Perintah menyimpannya di $VM variabel.
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
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Profil mesin virtual.

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### Microsoft.Azure.Management.Compute.Models.SecurityTypes

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS
