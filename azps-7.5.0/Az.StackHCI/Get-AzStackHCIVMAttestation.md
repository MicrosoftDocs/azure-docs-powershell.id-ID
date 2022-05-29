---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/get-AzStackHCIVMAttestation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIVMAttestation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIVMAttestation.md
ms.openlocfilehash: 3e0316e909a017a1925831bb8b2c434585a50e19
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145719064"
---
# Get-AzStackHCIVMAttestation

## SYNOPSIS
Get-AzStackHCIVMAttestation memperlihatkan daftar tamu yang ditambahkan ke IMDS Attestation pada node.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.stackhci/get-azstackhcivmattestation) untuk informasi terbaru.

## SYNTAX

```
Get-AzStackHCIVMAttestation [-Local] [<CommonParameters>]
```

## DESCRIPTION
Get-AzStackHCIVMAttestation memperlihatkan daftar tamu yang ditambahkan ke IMDS Attestation pada node.

## EXAMPLES

### CONTOH 1
```powershell
Get-AzStackHCIVMAttestation
```

Dapatkan semua tamu di kluster.

### CONTOH 2
```powershell
Get-AzStackHCIVMAttestation -Local
```

## PARAMETERS

### -Lokal
Hanya ambil tamu dengan Pengesahan dari simpul yang mengeksekusi cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject.
### Nama: Nama VM.
### AttestationHost: Host yang saat ini terhubung dengan VM.
### Status: Status koneksi.
## NOTES

## RELATED LINKS
