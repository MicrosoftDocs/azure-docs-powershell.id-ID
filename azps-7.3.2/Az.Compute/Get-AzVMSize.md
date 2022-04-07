---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: B7A675D3-EF79-4EE2-9330-D4C690739006
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azvmsize
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMSize.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMSize.md
ms.openlocfilehash: 84f76830daa6ea08fc5c7ba1ad7d45da9578a7e5
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140395439"
---
# Get-AzVMSize

## SYNOPSIS
Mendapatkan ukuran mesin virtual yang tersedia.

## SYNTAX

### ListVirtualMachineSizeParamSet (Default)
```
Get-AzVMSize [-Location] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ListAvailableSizesForAvailabilitySet
```
Get-AzVMSize [-ResourceGroupName] <String> [-AvailabilitySetName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ListAvailableSizesForVirtualMachine
```
Get-AzVMSize [-ResourceGroupName] <String> [-VMName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVMSize** mendapatkan ukuran mesin virtual yang tersedia.

## EXAMPLES

### Contoh 1: Mendapatkan ukuran mesin virtual untuk lokasi
```powershell
Get-AzVMSize -Location "Central US"
```

Perintah ini menggunakan ukuran yang tersedia untuk mesin virtual di lokasi yang ditentukan.

### Contoh 2: Mendapatkan ukuran untuk kumpulan ketersediaan
```powershell
Get-AzVMSize -ResourceGroupName "ResourceGroup03" -AvailabilitySetName "AvailabilitySet17"
```

Perintah ini memiliki ukuran yang tersedia untuk mesin virtual yang dapat Anda gunakan di kumpulan ketersediaan bernama AvailabilitySet17.

### Contoh 3: Mendapatkan ukuran untuk mesin virtual yang sudah ada
```powershell
Get-AzVMSize -ResourceGroupName "ResourceGroup03" -VMName "VirtualMachine12"
```

Perintah ini memiliki ukuran yang tersedia untuk mesin virtual yang sudah ada bernama VirtualMachine12.
Anda dapat mengubah ukuran mesin virtual ini ke ukuran yang didagangkan perintah ini.

## PARAMETERS

### -AvailabilitySetName
Menentukan nama Kumpulan Ketersediaan di mana cmdlet ini mendapatkan ukuran mesin virtual yang tersedia.

```yaml
Type: System.String
Parameter Sets: ListAvailableSizesForAvailabilitySet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Lokasi
Menentukan lokasi cmdlet ini mendapatkan ukuran mesin virtual yang tersedia.

```yaml
Type: System.String
Parameter Sets: ListVirtualMachineSizeParamSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya komputer virtual.

```yaml
Type: System.String
Parameter Sets: ListAvailableSizesForAvailabilitySet, ListAvailableSizesForVirtualMachine
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama mesin virtual yang akan mendapatkan ukuran mesin virtual yang tersedia untuk ukuran ulang.

```yaml
Type: System.String
Parameter Sets: ListAvailableSizesForVirtualMachine
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachineSize

## CATATAN

## RELATED LINKS

[Get-azvm](./Get-AzVM.md)


