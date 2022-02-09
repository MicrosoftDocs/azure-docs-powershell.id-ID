---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/new-azstreamanalyticsoutput
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/New-AzStreamAnalyticsOutput.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/New-AzStreamAnalyticsOutput.md
ms.openlocfilehash: 5c1532032bd825bfc957c48ea03e5d320e040390
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138268412"
---
# New-AzStreamAnalyticsOutput

## SYNOPSIS
Membuat output atau mengganti output yang sudah ada di bawah pekerjaan streaming yang sudah ada.

## SYNTAX

```
New-AzStreamAnalyticsOutput -File <String> -JobName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-IfMatch <String>] [-IfNoneMatch <String>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat output atau mengganti output yang sudah ada di bawah pekerjaan streaming yang sudah ada.

## EXAMPLES

### Contoh 1: Membuat output ke pekerjaan analitik streaming
```powershell
PS C:\> New-AzStreamAnalyticsOutput -ResourceGroupName azure-rg-test -JobName sajob-02-pwsh -Name output-01 -File .\test\template-json\StroageAccount.json

Name      Type                                            ETag
----      ----                                            ----
output-01 Microsoft.StreamAnalytics/streamingjobs/outputs 3819fb65-07f5-4dc3-83e1-d3149596f8d0
```

Perintah ini akan membuat output baru dalam pekerjaan analitik streaming.

(di bawah ini adalah contoh untuk "Account.json") { "properti": { "serialisasi": { "type": "Json", "properties": { "encoding": "UTF8", "format": "LineSeparated" } }, "datasource": { "type": "Microsoft.Storage /Blob", "properti": { "storageAccounts": [ { "accountName": "xxxxxxxxxxxxxxx", "accountKey": "xxxxxxxxxxxxxxxx" } ], "container": "xxxxxxxxxxxxxxxxx", "pathPattern": "cluster1/{client_id}", "dateFormat": "yyyy/MM/dd", "timeFormat": "HH", "authenticationMode": "ConnectionString" } } }

## PARAMETERS

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

### -File
Nama pekerjaan streaming.

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

### -IfMatch
ETag output.
Menghilangkan nilai ini agar selalu menimpa output saat ini.
Tentukan nilai ETag yang terakhir dilihat untuk mencegah secara tidak sengaja menimpa perubahan bersama.

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

### -IfNoneMatch
Atur ke '*' untuk memungkinkan output baru dibuat, tapi untuk mencegah memperbarui output yang sudah ada.
Nilai lainnya akan menghasilkan respons Gagal Pra-Kondisi 412.

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

### -JobName
Nama pekerjaan streaming.

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
Nama output.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: OutputName

Required: True
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

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IOutput

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IOutput

## CATATAN

ALIAS

## RELATED LINKS

