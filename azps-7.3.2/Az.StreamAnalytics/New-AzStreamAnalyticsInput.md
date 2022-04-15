---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/new-azstreamanalyticsinput
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/New-AzStreamAnalyticsInput.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/New-AzStreamAnalyticsInput.md
ms.openlocfilehash: 36d5c4a939473211d7b57a0b1255059eb1674be0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142397447"
---
# New-AzStreamAnalyticsInput

## SYNOPSIS
Membuat input atau menggantikan input yang sudah ada di bawah pekerjaan streaming yang sudah ada.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.streamanalytics/new-azstreamanalyticsinput) untuk informasi terbaru.

## SYNTAX

```
New-AzStreamAnalyticsInput -File <String> -JobName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-IfMatch <String>] [-IfNoneMatch <String>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat input atau menggantikan input yang sudah ada di bawah pekerjaan streaming yang sudah ada.

## EXAMPLES

### Contoh 1: Membuat input pekerjaan dengan definisi dari file
```powershell
PS C:\> New-AzStreamAnalyticsInput -ResourceGroupName azure-rg-test -JobName sajob-02-pwsh -Name input-01 -File .\test\template-json\EventHub.json

Name     Type                                           ETag
----     ----                                           ----
input-01 Microsoft.StreamAnalytics/streamingjobs/inputs 6c9f5122-44b9-45bf-81c9-5349a9dd8851
```

Perintah ini membuat input dari file EventHub.json.

(di bawah ini adalah contoh untuk "EventHub.json") { "properties": { "type": "Stream", "serialisasi": { "type": "Json", "properties": { "encoding": "UTF8" } }, "compression": { "type": "None" }, "datasource": { "type": "Microsoft.EventHub/EventHub", "properties": { "serviceBusNamespace": "xxxxxx", "sharedAccessPolicyName": "xxxxx", "sharedAccessPolicyKey": "xxxxx", "xxxxx", "xxx," authenticationMode": "ConnectionString", "eventHubName": "xxxxx", "consumerGroupName": "xxxxxxx" } } } }

### Contoh 2: Membuat input pekerjaan dengan definisi dari file
```powershell
PS C:\> New-AzStreamAnalyticsInput -ResourceGroupName azure-rg-test -JobName sajob-02-pwsh -Name input-01 -File .\test\template-json\IotHub.json

Name     Type                                           ETag
----     ----                                           ----
input-01 Microsoft.StreamAnalytics/streamingjobs/inputs 6c9f5122-44b9-45bf-81c9-5349a9dd8851
```

Perintah ini membuat input dari file IotHub.json.

(di bawah ini adalah contoh untuk "IotHub.json") { "properties": { "type": "Stream", "serialization": { "type": "Json", "properties": { "encoding": "UTF8" } }, "compression": { "type": "None" }, "partitionKey": "", "datasource": { "type": "Microsoft.Devices/IotHubs", "properties": { "iotHubNamespace": "xxxxxxxx", "sharedAccessPolicyName": "xxxxxxx", "sharedAccessPolicyKey": "xxxxxxx", "consumerGroupName": "$Default", "titik akhir": "pesan/kejadian" } } } }

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
ETag input.
Hilangkan nilai ini untuk selalu menimpa input saat ini.
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
Atur ke '*' untuk memperbolehkan input baru dibuat, tetapi untuk mencegah pembaruan input yang sudah ada.
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
Nama input.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: InputName

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

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IInput

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IInput

## CATATAN

ALIAS

## RELATED LINKS

