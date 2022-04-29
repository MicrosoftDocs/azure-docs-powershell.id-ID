---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/add-AzStackHCIVMAttestation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Add-AzStackHCIVMAttestation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Add-AzStackHCIVMAttestation.md
ms.openlocfilehash: b88bac708f5864400bb1c7af47f7ca2e56dcd7a4
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144192060"
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
Add-AzStackHCIVMAttestation -AddAll
```

Menambahkan semua tamu pada simpul saat ini

### CONTOH 2
```powershell
Invoke-Command -ScriptBlock {Add-AzStackHCIVMAttestation -VMName "guest1", "guest2"} -ComputerName "node1"
```

Memanggil dari node manajemen/WAC

## PARAMETERS

### -AddAll
Menentukan sakelar yang akan menambahkan semua VM tamu saat ini pada host ke Pengesahan IMDS pada simpul saat ini.

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
Tidak Ada Konfirmasi

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
Menentukan array objek VM dari Get-VM.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject
### Nama: Nama VM.
### AttestationHost: Host yang saat ini terhubung dengan VM.
### Status: Status koneksi.
## NOTES

## RELATED LINKS
