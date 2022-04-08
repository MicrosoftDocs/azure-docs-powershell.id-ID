---
external help file: ''
Module Name: Az.Datadog
online version: https://docs.microsoft.com/powershell/module/az.datadog/set-azdatadogmonitordefaultkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Set-AzDatadogMonitorDefaultKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Set-AzDatadogMonitorDefaultKey.md
ms.openlocfilehash: fd78c0699913a0a8acee54566d737077352e4c8b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140403023"
---
# Set-AzDatadogMonitorDefaultKey

## SYNOPSIS
Mengatur kunci api default.

## SYNTAX

```
Set-AzDatadogMonitorDefaultKey -MonitorName <String> -ResourceGroupName <String> -Key <String>
 [-SubscriptionId <String>] [-CreatedAt <String>] [-CreatedBy <String>] [-Name <String>]
 [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mengatur kunci api default.

## EXAMPLES

### Contoh 1: Atur tombol api default untuk sumber daya monitor
```powershell
PS C:\> Set-AzDatadogMonitorDefaultKey -ResourceGroupName azure-rg-Datadog -MonitorName Datadog -Key 'xxxxxxxxxxxxxxxxxxxxxx'

Created CreatedBy Key                              Name
------- --------- ---                              ----
                  xxxxxxxxxxxxxxxxxxxxxx
```

Perintah ini mengatur tombol api default untuk sumber daya monitor.

## PARAMETERS

### -CreatedAt
Waktu pembuatan kunci API.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreatedBy
Pengguna yang membuat kunci API.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Key
Nilai kunci API.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitorName
Memantau nama sumber daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kunci API.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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

### System.Boolean

## CATATAN

ALIAS

## RELATED LINKS

