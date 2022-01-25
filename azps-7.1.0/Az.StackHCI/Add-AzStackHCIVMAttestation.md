---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/add-AzStackHCIVMAttestation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Add-AzStackHCIVMAttestation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Add-AzStackHCIVMAttestation.md
ms.openlocfilehash: b7822bced8ef06011a31c94a0a45e67b303f4ddc
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136754282"
---
# Add-AzStackHCIVMAttestation

## SYNOPSIS
Add-AzStackHCIVMAttestation mengonfigurasi tamu untuk AzureStack HCI IMDS Attestation.

## SYNTAX

### VMName (Default)
```
Add-AzStackHCIVMAttestation [-VMName] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Add-AzStackHCIVMAttestation [-VM] <Object[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TambahkanSemua
```
Add-AzStackHCIVMAttestation [-AddAll] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Add-AzStackHCIVMAttestation mengonfigurasi tamu untuk AzureStack HCI IMDS Attestation.

## EXAMPLES

### CONTOH 1
```powershell
C:\PS\>Add-AzStackHCIVMAttestation -AddAll
```

Menambahkan semua tamu pada simpul saat ini

### CONTOH 2
```powershell
C:\PS\>Invoke-Command -ScriptBlock {Add-AzStackHCIVMAttestation -VMName "guest1", "guest2"} -ComputerName "node1"
```

Melakukan invoking dari node manajemen/WAC

## PARAMETERS

### -AddAll
Menentukan sakelar yang akan menambahkan semua VM tamu saat ini di host ke Attestation IMDS di simpul saat ini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AddAll
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Konfirmasi Tidak Ada

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
