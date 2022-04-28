---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/enable-azstackhciattestation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Enable-AzStackHCIAttestation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Enable-AzStackHCIAttestation.md
ms.openlocfilehash: 9f8bad84711e6841619e799681af8765224b0b9b
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144193978"
---
# Enable-AzStackHCIAttestation

## SYNOPSIS
Enable-AzStackHCIAttestation mengonfigurasi host dan mengaktifkan tamu tertentu untuk pengesahan IMDS.

## SYNTAX

```
Enable-AzStackHCIAttestation [[-ComputerName] <String>] [-Credential <PSCredential>] [-AddVM] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Enable-AzStackHCIAttestation mengonfigurasi host dan mengaktifkan tamu tertentu untuk pengesahan IMDS.

## EXAMPLES

### CONTOH 1
```powershell
Enable-AzStackHCIAttestation -AddVM
```

Memanggil pada salah satu node kluster.

### CONTOH 2
```powershell
Enable-AzStackHCIAttestation -ComputerName "host1" -AddVM
```

Memanggil dari node WAC/Management dan menambahkan semua VM yang ada di seluruh kluster

## PARAMETERS

### -AddVM
Setelah mengaktifkan setiap node kluster untuk Pengesahan, tambahkan semua tamu di setiap simpul.

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

### -ComputerName
Menentukan host AzureStack HCI untuk melakukan operasi.
Catatan: host ini harus cocok dengan host VMName.

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
### Kluster: Nama kluster
### Node: Nama host.
### Pengesahan: Status Pengesahan IMDS.
## NOTES

## RELATED LINKS
