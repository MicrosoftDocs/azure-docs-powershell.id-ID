---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/disable-azstackhciattestation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Disable-AzStackHCIAttestation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Disable-AzStackHCIAttestation.md
ms.openlocfilehash: 0d9805de3716117ff853be1ef77b8922674a6f3e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142206973"
---
# Disable-AzStackHCIAttestation

## SYNOPSIS
Disable-AzStackHCIAttestation menonaktifkan Pengesahan IMDS pada host

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.stackhci/disable-azstackhciattestation) untuk informasi terbaru.

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
C:\PS\>Disable-AzStackHCIAttestation -RemoveVM
```

Hapus semua tamu dari Pengesahan IMDS sebelum menonaktifkan node kluster.

### CONTOH 2
```powershell
C:\PS\>Disable-AzStackHCIAttestation -ComputerName "host1"
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

### -Kredensial
Menentukan kredensial untuk ComputerName.
Defaultnya adalah pengguna saat ini menjalankan Cmdlet.

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

### -Paksa
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
Menentukan tamu di setiap simpul harus dihapus dari Pengesahan IMDS sebelum menonaktifkan pada kluster.
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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject
### Kluster: Nama kluster
### Node: Nama host.
### Atestation: Status Attesasi IMDS.
## CATATAN

## RELATED LINKS
