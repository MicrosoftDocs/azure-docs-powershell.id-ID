---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.applicationinsights/get-azapplicationinsightswebtest
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/help/Get-AzApplicationInsightsWebTest.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/help/Get-AzApplicationInsightsWebTest.md
ms.openlocfilehash: d946a4efc2ffb51c92c57ed9ed75f781e8947dff
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146626348"
---
# Get-AzApplicationInsightsWebTest

## SYNOPSIS
Dapatkan definisi pengujian web Insights Aplikasi tertentu.

## SYNTAX

### List1 (Default)
```
Get-AzApplicationInsightsWebTest [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzApplicationInsightsWebTest -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzApplicationInsightsWebTest -InputObject <IApplicationInsightsIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar
```
Get-AzApplicationInsightsWebTest -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar2
```
Get-AzApplicationInsightsWebTest -AppInsightsName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan definisi pengujian web Insights Aplikasi tertentu.

## EXAMPLES

### Contoh 1: Mencantumkan semua pengujian web Insights Aplikasi di bawah langganan
```powershell
Get-AzApplicationInsightsWebTest
```

```output
Name                                 Location WebTestKind ResourceGroupName
----                                 -------- ----------- -----------------
bsaic-portal-appinsights-portal01    westus2  ping        azpwsh-rg-test
basic-portal02-appinsights-portal01  westus2  ping        azpwsh-rg-test
basic-portal03-appinsights-portal01  westus2  ping        azpwsh-rg-test
standard-portal-appinsights-portal01 westus2  standard    azpwsh-rg-test
standard-pwsh01                      westus2  standard    azpwsh-rg-test
```

Perintah ini mencantumkan semua pengujian web Insights Aplikasi di bawah langganan.

### Contoh 2: Mencantumkan semua pengujian web Insights Aplikasi di bawah grup sumber daya
```powershell
Get-AzApplicationInsightsWebTest -ResourceGroupName azpwsh-rg-test
```

```output
Name                                 Location WebTestKind ResourceGroupName
----                                 -------- ----------- -----------------
bsaic-portal-appinsights-portal01    westus2  ping        azpwsh-rg-test
basic-portal02-appinsights-portal01  westus2  ping        azpwsh-rg-test
basic-portal03-appinsights-portal01  westus2  ping        azpwsh-rg-test
standard-portal-appinsights-portal01 westus2  standard    azpwsh-rg-test
standard-pwsh01                      westus2  standard    azpwsh-rg-test
```

Perintah ini mencantumkan semua pengujian web Insights Aplikasi di bawah grup sumber daya.

### Contoh 3: Mencantumkan semua pengujian web Insights Aplikasi di bawah Insights Aplikasi tertentu
```powershell
Get-AzApplicationInsightsWebTest -ResourceGroupName azpwsh-rg-test -AppInsightsName appinsights-portal01
```

```output
Name                                 Location WebTestKind ResourceGroupName   Enabled
----                                 -------- ----------- -----------------   -------
bsaic-portal-appinsights-portal01    westus2  ping        azpwsh-rg-test      True
basic-portal02-appinsights-portal01  westus2  ping        azpwsh-rg-test      True
basic-portal03-appinsights-portal01  westus2  ping        azpwsh-rg-test      True
standard-portal-appinsights-portal01 westus2  standard    azpwsh-rg-test      True
standard-pwsh01                      westus2  standard    azpwsh-rg-test      True
```

Perintah ini mencantumkan semua pengujian web Insights Aplikasi di bawah Insights Aplikasi tertentu.

### Contoh 4: Mendapatkan definisi pengujian web Insights Aplikasi tertentu
```powershell
Get-AzApplicationInsightsWebTest -ResourceGroupName azpwsh-rg-test -Name standard-pwsh01
```

```output
Name            Location WebTestKind ResourceGroupName  Enabled
----            -------- ----------- -----------------  -------
standard-pwsh01 westus2  standard    azpwsh-rg-test     True
```

Perintah ini mendapatkan definisi pengujian web Insights Aplikasi tertentu.

### Contoh 5: Mendapatkan definisi pengujian web Insights Aplikasi tertentu menurut alur
```powershell
$location01 = New-AzApplicationInsightsWebTestGeolocationObject -Location "emea-nl-ams-azr"
$location02 = New-AzApplicationInsightsWebTestGeolocationObject -Location "us-ca-sjc-azr"
New-AzApplicationInsightsWebTest -ResourceGroupName azpwsh-rg-test -Name standardwebtestpwsh03 -Location 'westus2' `
-Tag @{"hidden-link:/subscriptions/xxxxxxxxxx-xxxx-xxxxx-xxxxxxxxxxxx/resourceGroups/azpwsh-rg-test/providers/microsoft.insights/components/appinsightsportal01" = "Resource"} `
-RequestUrl "https://docs.microsoft.com/" -RequestHttpVerb "GET" `
-TestName 'standardwebtestpwsh03' `
-RuleSslCheck -RuleSslCertRemainingLifetimeCheck 7 -RuleExpectedHttpStatusCode 200 `
-Enabled -Frequency 300 -Timeout 120 -Kind "standard" -RetryEnabled -GeoLocation $location01, $location02 ` |Get-AzApplicationInsightsWebTest
```

```output
Name                    Location WebTestKind ResourceGroupName  Enabled
----                    -------- ----------- -----------------  -------
standardwebtestpwsh03   westus2  standard    azpwsh-rg-test     True
```

Perintah ini mendapatkan definisi pengujian web Insights Aplikasi tertentu berdasarkan alur.

## PARAMETERS

### -AppInsightsName
Nama sumber daya komponen Insights Aplikasi.

```yaml
Type: System.String
Parameter Sets: List2
Aliases:

Required: True
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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.IApplicationInsightsIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama sumber daya WebTest Insights Aplikasi.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: WebTestName

Required: True
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
Parameter Sets: Get, List, List2
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
Type: System.String[]
Parameter Sets: Get, List, List1, List2
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.IApplicationInsightsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.IWebTest

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IApplicationInsightsIdentity>`: Parameter Identitas
  - `[AnnotationId <String>]`: ID anotasi unik. Ini unik dalam komponen Insights Aplikasi.
  - `[ComponentName <String>]`: Nama sumber daya komponen Insights Aplikasi.
  - `[ExportId <String>]`: ID konfigurasi Ekspor Berkelanjutan. Ini unik dalam komponen Insights Aplikasi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[KeyId <String>]`: ID Kunci API. Ini unik dalam komponen Insights Aplikasi.
  - `[PurgeId <String>]`: Dalam permintaan status penghapusan menyeluruh, ini adalah Id operasi yang statusnya dikembalikan.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[ResourceName <String>]`: Nama sumber daya komponen Insights Aplikasi.
  - `[StorageType <StorageType?>]`: Jenis sumber data komponen Application Insights untuk akun penyimpanan yang ditautkan.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[WebTestName <String>]`: Nama sumber daya WebTest Insights Aplikasi.

## RELATED LINKS

