---
external help file: Microsoft.Azure.Commands.StreamAnalytics.dll-Help.xml
Module Name: AzureRM
ms.assetid: 43B2A4FD-DA74-403A-89D0-40FE9A3E5A7E
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.streamanalytics/new-azurermstreamanalyticsoutput
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/StreamAnalytics/Commands.StreamAnalytics/help/New-AzureRmStreamAnalyticsOutput.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/StreamAnalytics/Commands.StreamAnalytics/help/New-AzureRmStreamAnalyticsOutput.md
ms.openlocfilehash: 7b18513a6a9e7ebbf82892500344d13f9cbc8185
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422220"
---
# New-AzureRmStreamAnalyticsOutput

## SYNOPSIS
Membuat atau memperbarui output untuk pekerjaan Analitik Stream.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmStreamAnalyticsOutput [-JobName] <String> [[-Name] <String>] [-File] <String> [-Force]
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmStreamAnalyticsOutput** membuat output dalam pekerjaan Analitik Stream atau memperbarui output yang sudah ada.
Nama output dapat ditentukan di dalam . File JSON atau di baris perintah.
Jika keduanya ditentukan, nama di baris perintah harus sesuai dengan nama dalam file.

Jika Anda menentukan output yang sudah ada dan tidak menentukan parameter *Force,* cmdlet akan menanyakan apakah akan mengganti output yang sudah ada atau tidak.

Jika Anda menentukan parameter *Paksa* dan menentukan nama output yang sudah ada, output akan diganti tanpa konfirmasi.

## EXAMPLES

### CONTOH 1: Menambahkan output ke pekerjaan
```
PS C:\>New-AzureRmStreamAnalyticsOutput -ResourceGroupName "StreamAnalytics-Default-West-US" -File "C:\Output.json" -JobName "StreamingJob" -Name "Output"
```

Perintah ini membuat output baru yang disebut Output dalam pekerjaan yang disebut StreamingJob.
Jika output yang sudah ada dengan nama ini sudah ditentukan, cmdlet akan menanyakan apakah akan menggantinya atau tidak.

### CONTOH 2: Mengganti definisi output pekerjaan
```
PS C:\>New-AzureRmStreamAnalyticsOutput -ResourceGroupName "StreamAnalytics-Default-West-US" -File "C:\Output.json" -JobName "StreamingJob" -Name "Output" -Force
```

Perintah ini menggantikan definisi untuk Output dalam pekerjaan yang disebut StreamingJob tanpa konfirmasi.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -File
Menentukan jalur ke file JSON yang berisi representasi JSON dari output Analitik Azure Stream yang akan dibuat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName
Menentukan nama pekerjaan Analitik Azure Stream untuk membuat output Analitik Azure Stream.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama output Analitik Azure Stream untuk dibuat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya untuk membuat output Analitik Azure Stream.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.StreamAnalytics.Models.PSOutput

## CATATAN

## RELATED LINKS

[Get-AzureRmStreamAnalyticsOutput](./Get-AzureRmStreamAnalyticsOutput.md)

[Remove-AzureRmStreamAnalyticsOutput](./Remove-AzureRmStreamAnalyticsOutput.md)

[Test-AzureRmStreamAnalyticsOutput](./Test-AzureRmStreamAnalyticsOutput.md)


