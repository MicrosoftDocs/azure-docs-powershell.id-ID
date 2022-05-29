---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/enable-azstackhciremotesupport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Enable-AzStackHCIRemoteSupport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Enable-AzStackHCIRemoteSupport.md
ms.openlocfilehash: cdc9ab12925a6e1a52703139f022d00cc1bf33f5
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145719216"
---
# Enable-AzStackHCIRemoteSupport

## SYNOPSIS
Mengaktifkan Dukungan Jarak Jauh.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.stackhci/enable-azstackhciremotesupport) untuk informasi terbaru.

## SYNTAX

```
Enable-AzStackHCIRemoteSupport [-AccessLevel] <String> [[-ExpireInMinutes] <Int32>] [[-SasCredential] <String>]
 [-AgreeToRemoteSupportConsent] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mengaktifkan Dukungan Jarak Jauh memungkinkan pengguna Dukungan Microsoft yang berwenang untuk mengakses perangkat dari jarak jauh untuk diagnostik atau perbaikan tergantung pada tingkat akses yang diberikan.

## EXAMPLES

### CONTOH 1
```powershell
Enable-AzStackHCIRemoteSupport -AccessLevel Diagnostics -ExpireInMinutes 1440 -SasCredential "Sample SAS"
```

### CONTOH 2
```powershell
Enable-AzStackHCIRemoteSupport -AccessLevel DiagnosticsRepair -ExpireInMinutes 1440 -SasCredential "Sample SAS" -AgreeToRemoteSupportConsent
```

## PARAMETERS

### -AccessLevel
Mengontrol operasi jarak jauh yang dapat dilakukan. Ini bisa berupa Diagnostik atau DiagnosticsAndRepair.

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
Jika diatur ke true, maka rekam persetujuan pengguna sebagaimana disediakan dan dilanjutkan tanpa perintah.

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
Menentukan kedaluwarsa dukungan jarak jauh dalam hari. Default ke 480 menit (8 jam).

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
