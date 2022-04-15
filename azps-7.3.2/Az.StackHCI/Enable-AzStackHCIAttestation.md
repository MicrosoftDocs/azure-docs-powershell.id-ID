---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/enable-azstackhciattestation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Enable-AzStackHCIAttestation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Enable-AzStackHCIAttestation.md
ms.openlocfilehash: a6ddddb826e7e75334ddc94e7ef5cb8604baf4a1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142025255"
---
# Enable-AzStackHCIAttestation

## SYNOPSIS
Enable-AzStackHCIAttestation mengonfigurasi host dan memungkinkan tamu tertentu untuk mengesankan IMDS.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.stackhci/enable-azstackhciattestation) untuk informasi terbaru.

## SYNTAX

```
Enable-AzStackHCIAttestation [[-ComputerName] <String>] [-Credential <PSCredential>] [-AddVM] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Enable-AzStackHCIAttestation mengonfigurasi host dan memungkinkan tamu tertentu untuk mengesankan IMDS.

## EXAMPLES

### CONTOH 1
```poweshell
C:\PS\>Enable-AzStackHCIAttestation -AddVM
```

Memanggil salah satu simpul kluster.

### CONTOH 2
```powershell
C:\PS\>Enable-AzStackHCIAttestation -ComputerName "host1" -AddVM
```

Invoking from WAC/Management node and adding all existing VMs cluster-wide

## PARAMETERS

### -AddVM
Setelah mengaktifkan setiap simpul kluster untuk Pengesahan, tambahkan semua tamu di setiap simpul.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCustomObject. Mengembalikan Properti berikut di PSCustomObject
### Kluster: Nama kluster
### Node: Nama host.
### Atestation: Status Attesasi IMDS.
## CATATAN

## RELATED LINKS
