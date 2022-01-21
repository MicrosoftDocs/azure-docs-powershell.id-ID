---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/remove-AzStackHCIVMAttestation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Remove-AzStackHCIVMAttestation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Remove-AzStackHCIVMAttestation.md
ms.openlocfilehash: 8183271a5ec1992634066eaf40bc9d190a56809f
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136532957"
---
# Remove-AzStackHCIVMAttestation

## SYNOPSIS
Remove-AzStackHCIVMAttestation menghapus tamu dari AzureStack HCI IMDS Attestation.

## SYNTAX

### VMName (Default)
```
Remove-AzStackHCIVMAttestation [-VMName] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Remove-AzStackHCIVMAttestation [-VM] <Object[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveAll
```
Remove-AzStackHCIVMAttestation [-RemoveAll] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Remove-AzStackHCIVMAttestation menghapus tamu dari AzureStack HCI IMDS Attestation.

## EXAMPLES

### CONTOH 1
```
Removing all guests on current node
```

C:\PS \> remove-azStackhCIVMAttestation -RemoveVM

### CONTOH 2
```
Invoking from the management node/WAC
```

C:\PS \> Invoke-Command -ScriptBlock {Remove-AzStackHCIVMAttestation -VMName "guest1", "guest2"} -ComputerName "node1"

## PARAMETERS

### -Force
Tidak ada konfirmasi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveAll
Menentukan sakelar yang akan menghapus semua VM tamu dari Attestation di node saat ini

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RemoveAll
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan larik objek VM dari Get-VM.

```yaml
Type: System.Object[]
Parameter Sets: VMObject
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Menentukan array VM tamu untuk diaktifkan.

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject
### Nama: Nama VM.
### AttestationHost: Host bahwa VM saat ini tersambung.
### Status: Status koneksi.
## CATATAN

## RELATED LINKS
