---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/get-AzStackHCIVMAttestation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIVMAttestation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIVMAttestation.md
ms.openlocfilehash: f758ea3e878ff38c052fe663fa7bd16ddc704463
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143131553"
---
# Get-AzStackHCIVMAttestation

## SYNOPSIS
Get-AzStackHCIVMAttestation memperlihatkan daftar tamu yang ditambahkan ke Pengesahan IMDS pada simpul.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.stackhci/get-azstackhcivmattestation) untuk informasi terbaru.

## SYNTAX

```
Get-AzStackHCIVMAttestation [-Local] [<CommonParameters>]
```

## DESCRIPTION
Get-AzStackHCIVMAttestation memperlihatkan daftar tamu yang ditambahkan ke Pengesahan IMDS pada simpul.

## EXAMPLES

### CONTOH 1
```powershell
C:\PS\>Get-AzStackHCIVMAttestation
```

Dapatkan semua tamu di kluster.

### CONTOH 2
```powershell
C:\PS\>Get-AzStackHCIVMAttestation -Local
```

## PARAMETERS

### -Lokal
Hanya ambil tamu dengan Attestation dari simpul yang menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject.
### Nama: Nama VM.
### AttestationHost: Host bahwa VM saat ini tersambung.
### Status: Status koneksi.
## NOTES

## RELATED LINKS
