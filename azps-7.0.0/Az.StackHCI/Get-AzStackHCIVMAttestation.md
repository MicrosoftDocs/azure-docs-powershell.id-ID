---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/get-AzStackHCIVMAttestation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIVMAttestation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIVMAttestation.md
ms.openlocfilehash: a45b0eaacf8ba07b6b1d588d18acf37fe5f061bb
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136392459"
---
# Get-AzStackHCIVMAttestation

## SYNOPSIS
Get-AzStackHCIVMAttestation memperlihatkan daftar tamu yang ditambahkan ke Attestation IMDS di simpul.

## SYNTAX

```
Get-AzStackHCIVMAttestation [-Local] [<CommonParameters>]
```

## DESCRIPTION
Get-AzStackHCIVMAttestation memperlihatkan daftar tamu yang ditambahkan ke Attestation IMDS di simpul.

## EXAMPLES

### CONTOH 1
```powershell
C:\PS\>Get-AzStackHCIVMAttestation
```

Mendapatkan semua tamu dalam kluster.

### CONTOH 2
```powershell
C:\PS\>Get-AzStackHCIVMAttestation -Local
```

## PARAMETERS

### -Lokal
Hanya mengambil tamu dengan Attestation dari simpul menjalankan cmdlet.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject.
### Nama: Nama VM.
### AttestationHost: Host bahwa VM saat ini tersambung.
### Status: Status koneksi.
## CATATAN

## RELATED LINKS
