---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/disable-azstackhciattestation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Disable-AzStackHCIAttestation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Disable-AzStackHCIAttestation.md
ms.openlocfilehash: f21e60d1ea56c5501aeb5e5d368c7b0f274f6095
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145719244"
---
# Disable-AzStackHCIAttestation

## SYNOPSIS
Disable-AzStackHCIAttestation menonaktifkan Pengesahan IMDS pada host

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.stackhci/disable-azstackhciattestation) untuk informasi terbaru.

## SYNTAX

```
Disable-AzStackHCIAttestation [[-ComputerName] <String>] [-Credential <PSCredential>] [-RemoveVM] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Disable-AzStackHCIAttestation menonaktifkan Pengesahan IMDS pada host

## EXAMPLES

### CONTOH 1
```powershell
Disable-AzStackHCIAttestation -RemoveVM
```

Hapus semua tamu dari IMDS Attestation sebelum menonaktifkan pada node kluster.

### CONTOH 2
```powershell
Disable-AzStackHCIAttestation -ComputerName "host1"
```

## PARAMETERS

### -ComputerName
Menentukan host AzureStack HCI untuk melakukan operasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Menentukan kredensial untuk ComputerName.
Defaultnya adalah pengguna saat ini yang menjalankan Cmdlet.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [System.Management.Automation.PSCredential]::Empty
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -RemoveVM
Menentukan tamu pada setiap simpul harus dihapus dari Pengesahan IMDS sebelum menonaktifkan pada kluster.
Nonaktifkan tidak dapat dilanjutkan sebelum tamu dihapus.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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
### Kluster: Nama kluster
### Node: Nama host.
### Pengesahan: Status Pengesahan IMDS.
## NOTES

## RELATED LINKS
