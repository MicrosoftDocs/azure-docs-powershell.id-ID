---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.applicationinsights/new-azapplicationinsights
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/help/Update-AzApplicationInsights.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/help/Update-AzApplicationInsights.md
ms.openlocfilehash: 4d6195d204c17a9859dfefcca39ddd30ab81a723
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145504189"
---
# Update-AzApplicationInsights

## SYNOPSIS
Membuat (atau memperbarui) komponen Insights Aplikasi.
Catatan: Anda tidak dapat menentukan nilai yang berbeda untuk InstrumentationKey atau AppId dalam operasi Put.

## SYNTAX

```
Update-AzApplicationInsights -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-ApplicationType <ApplicationType>] [-DisableIPMasking] [-DisableLocalAuth] [-Etag <String>]
 [-FlowType <FlowType>] [-ForceCustomerStorageForProfiler] [-HockeyAppId <String>]
 [-ImmediatePurgeDataOn30Day] [-IngestionMode <IngestionMode>]
 [-PublicNetworkAccessForIngestion <PublicNetworkAccessType>]
 [-PublicNetworkAccessForQuery <PublicNetworkAccessType>] [-RequestSource <RequestSource>]
 [-RetentionInDays <Int32>] [-SamplingPercentage <Double>] [-Tag <Hashtable>] [-WorkspaceResourceId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat (atau memperbarui) komponen Insights Aplikasi.
Catatan: Anda tidak dapat menentukan nilai yang berbeda untuk InstrumentationKey atau AppId dalam operasi Put.

## EXAMPLES

### Contoh 1: Memperbarui komponen application insights
```powershell
Update-AzApplicationInsights -ResourceGroupName "rgName" -Name "aiName" -PublicNetworkAccessForIngestion "Disabled" -PublicNetworkAccessForQuery "Disabled"
```

memperbarui komponen application insights "aiName" PublicNetworkAccessForIngestion/PublicNetworkAccessForQuery keduanya menjadi "Dinonaktifkan"

## PARAMETERS

### -ApplicationType
Jenis aplikasi yang sedang dipantau.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Support.ApplicationType
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

### -DisableIPMasking
Nonaktifkan masking IP.

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

### -DisableLocalAuth
Nonaktifkan Autentikasi berbasis Non-AAD.

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

### -Etag
Etag sumber daya

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

### -FlowType
Digunakan oleh sistem Insights Aplikasi untuk menentukan jenis alur apa komponen ini dibuat.
Ini akan diatur ke 'Bluefield' saat membuat/memperbarui komponen melalui REST API.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Support.FlowType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceCustomerStorageForProfiler
Paksa pengguna untuk membuat akun penyimpanan mereka sendiri untuk profiler dan debugger.

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

### -HockeyAppId
ID aplikasi unik yang dibuat ketika aplikasi baru ditambahkan ke HockeyApp, digunakan untuk komunikasi dengan HockeyApp.

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

### -ImmediatePurgeDataOn30Day
Hapus menyeluruh data segera setelah 30 hari.

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

### -IngestionMode
Menunjukkan alur penyerapan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Support.IngestionMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama sumber daya komponen Insights Aplikasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ApplicationInsightsComponentName, ComponentName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicNetworkAccessForIngestion
Jenis akses jaringan untuk mengakses penyerapan Insights Aplikasi.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Support.PublicNetworkAccessType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicNetworkAccessForQuery
Jenis akses jaringan untuk mengakses kueri Insights Aplikasi.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Support.PublicNetworkAccessType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestSource
Menjelaskan alat apa yang membuat komponen Insights Aplikasi ini.
Pelanggan yang menggunakan API ini harus mengatur ini ke 'rest' default.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Support.RequestSource
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
Nama tidak peka huruf besar/kecil.

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

### -RetentionInDays
Periode retensi dalam hari.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SamplingPercentage
Persentase data yang dihasilkan oleh aplikasi yang dipantau yang sedang diambil sampelnya untuk telemetri Insights Aplikasi.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
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

### -Tag
Tag sumber daya

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceResourceId
Id Sumber Daya ruang kerja analitik log tempat data akan diserap.
Properti ini diperlukan untuk membuat aplikasi dengan versi API ini.
Aplikasi dari versi lama tidak akan memiliki properti ini.

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

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api202002.IApplicationInsightsComponent

## NOTES

ALIAS

## RELATED LINKS

