---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/enable-azstackhciremotesupport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Enable-AzStackHCIRemoteSupport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Enable-AzStackHCIRemoteSupport.md
ms.openlocfilehash: 7ab519e81cf5d82c732d63cde2cac4a136893938
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138301820"
---
# Enable-AzStackHCIRemoteSupport

## SYNOPSIS
Mengaktifkan Dukungan Jarak Jauh.

## SYNTAX

```
Enable-AzStackHCIRemoteSupport [-AccessLevel] <String> [[-ExpireInMinutes] <Int32>] [[-SasCredential] <String>]
 [-AgreeToRemoteSupportConsent] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mengaktifkan Dukungan Jarak Jauh memungkinkan pengguna Dukungan Microsoft yang sah mengakses perangkat secara jarak jauh untuk diagnostik atau perbaikan, bergantung pada tingkat akses yang diberikan.

## EXAMPLES

### CONTOH 1
```poweshell
C:\PS\>Enable-AzStackHCIRemoteSupport -AccessLevel Diagnostics -ExpireInMinutes 1440 -SasCredential "Sample SAS"
```

### CONTOH 2
```powershell
C:\PS\>Enable-AzStackHCIRemoteSupport -AccessLevel DiagnosticsRepair -ExpireInMinutes 1440 -SasCredential "Sample SAS" -AgreeToRemoteSupportConsent
```

## PARAMETERS

### -AccessLevel
Mengontrol operasi jarak jauh yang dapat dijalankan. Ini bisa berupa Diagnostik atau DiagnosticsAndRepair.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: [System.String]::Empty
Accept pipeline input: False
Accept wildcard characters: False
```

### -AgreeToRemoteSupportConsent
Jika diatur ke true, maka catat persetujuan pengguna sebagaimana diberikan dan lanjutkan tanpa perintah.

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

### -ExpireInMinutes
Menentukan dukungan jarak jauh yang akan kedaluwarsa dalam hari. Default hingga 480 menit (8 jam).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: 480
Accept pipeline input: False
Accept wildcard characters: False
```

### -SasCredential
Kredensial SAS Koneksi Hibrid.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: [System.String]::Empty
Accept pipeline input: False
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS
