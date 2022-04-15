---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/new-azstreamanalyticsfunction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/New-AzStreamAnalyticsFunction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/New-AzStreamAnalyticsFunction.md
ms.openlocfilehash: c4751640d770d08eb674fd5f965ff455020a333a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142433611"
---
# New-AzStreamAnalyticsFunction

## SYNOPSIS
Membuat fungsi atau menggantikan fungsi yang sudah ada di bawah pekerjaan streaming yang sudah ada.

## SYNTAX

```
New-AzStreamAnalyticsFunction -File <String> -JobName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-IfMatch <String>] [-IfNoneMatch <String>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat fungsi atau menggantikan fungsi yang sudah ada di bawah pekerjaan streaming yang sudah ada.

## EXAMPLES

### Contoh 1: Membuat fungsi Stream Analytics
```powershell
New-AzStreamAnalyticsFunction -ResourceGroupName azure-rg-test -JobName sajob-02-pwsh -Name function-01 -File .\test\template-json\Function_JavascriptUdf.json
```
```output
Name        Type                                              ETag
----        ----                                              ----
function-01 Microsoft.StreamAnalytics/streamingjobs/functions 7bbd6ccd-c7a4-4910-b2ae-a3eae19d9b18

```

Perintah ini membuat fungsi dari file Function_JavascriptUdf.json.

(di bawah ini adalah contoh untuk "Function_JavascriptUdf.json") { "properties": { "type": "Scalar", "properties": { "inputs": [ { "dataType": "any" }, { "dataType": "any" } ], "output": { "dataType": "any" }, "binding": { "type": "Microsoft.StreamAnalytics/JavascriptUdf", "properties": { "script": "// Sample UDF yang mengembalikan jumlah dari dua values.\nfungsi main(arg3, arg4) {\n return arg1 + arg2;\n}" } } } } }

### Contoh 2: Membuat fungsi Stream Analytics
```powershell
New-AzStreamAnalyticsFunction -ResourceGroupName azure-rg-test -JobName sajob-02-pwsh -Name function-01 -File .\test\template-json\MachineLearningServices.json
```
```output
Name        Type                                              ETag
----        ----                                              ----
function-01 Microsoft.StreamAnalytics/streamingjobs/functions 7bbd6ccd-c7a4-4910-b2ae-a3eae19d9b18
```

Perintah ini membuat fungsi dari file MachineLearningServices.json.

(di bawah ini adalah contoh untuk "MachineLearningServices.json") { "properties": { "type": "Scalar", "properties": { "inputs": [ { "dataType": "record" } ], "output": { "dataType": "bigint" }, "binding": { "type": "Microsoft.MachineLearningServices", "properties": { "endpoint": "http://xxxxxxxxxxxxxxxxxxx.eastus.azurecontainer.io/score", "input": [ { "name": "data", "dataType": "object", "mapTo": 0 } ], "outputs": [ { "name": "output", "dataType": "int64", "mapTo": 0 } ], "batchSize": 10000, "numberOfParallelRequests": 1 } } } } }

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
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

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
ETag fungsi.
Hilangkan nilai ini untuk selalu menimpa fungsi saat ini.
Tentukan nilai ETag yang terakhir terlihat untuk mencegah timpa perubahan bersamaan secara tidak sengaja.

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
Atur ke '*' untuk memperbolehkan fungsi baru dibuat, tetapi untuk mencegah pembaruan fungsi yang sudah ada.
Nilai lain akan menghasilkan respons Gagal Pra-kondisi 412.

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
Nama fungsi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FunctionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

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

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IFunction

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IFunction

## CATATAN

ALIAS

## RELATED LINKS

