---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.applicationinsights/new-azapplicationinsightswebtest
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTest.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/New-AzApplicationInsightsWebTest.md
ms.openlocfilehash: 6ced1a69eed1d797eea4d5736a38d2d7de85493d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142261231"
---
# New-AzApplicationInsightsWebTest

## SYNOPSIS
Membuat atau memperbarui definisi uji web Insights Aplikasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.applicationinsights/new-azapplicationinsightswebtest) untuk informasi terbaru.

## SYNTAX

### CreateStandard (Default)
```
New-AzApplicationInsightsWebTest -Name <String> -ResourceGroupName <String> -Location <String>
 [-SubscriptionId <String>] [-ContentIgnoreCase] [-ContentMatch <String>] [-ContentPassIfTextFound]
 [-Description <String>] [-Enabled] [-Frequency <Int32>] [-GeoLocation <IWebTestGeolocation[]>]
 [-Kind <WebTestKindEnum>] [-RequestBody <String>] [-RequestFollowRedirect] [-RequestHeader <IHeaderField[]>]
 [-RequestHttpVerb <String>] [-RequestParseDependent] [-RequestUrl <String>] [-RetryEnabled]
 [-RuleExpectedHttpStatusCode <Int32>] [-RuleIgnoreHttpsStatusCode]
 [-RuleSslCertRemainingLifetimeCheck <Int32>] [-RuleSslCheck] [-Tag <Hashtable>] [-TestName <String>]
 [-Timeout <Int32>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### CreateClassic
```
New-AzApplicationInsightsWebTest -Name <String> -ResourceGroupName <String> -Location <String>
 [-SubscriptionId <String>] [-Configuration <String>] [-ContentMatch <String>] [-Description <String>]
 [-Enabled] [-Frequency <Int32>] [-GeoLocation <IWebTestGeolocation[]>] [-Kind <WebTestKindEnum>]
 [-RequestParseDependent] [-RequestUrl <String>] [-RetryEnabled] [-RuleExpectedHttpStatusCode <Int32>]
 [-Tag <Hashtable>] [-TestName <String>] [-Timeout <Int32>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui definisi uji web Insights Aplikasi.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui jenis standar uji web Aplikasi Insights
```powershell
$geoLocation = @()
```
```powershell
$geoLocation += New-AzApplicationInsightsWebTestGeolocationObject -Location "emea-nl-ams-azr"
$geoLocation += New-AzApplicationInsightsWebTestGeolocationObject -Location "us-ca-sjc-azr"
```
```powershell
New-AzApplicationInsightsWebTest -ResourceGroup azpwsh-rg-test -Name standard-pwsh01 -Location 'westus2' `
-Tag @{"hidden-link:/subscriptions/xxxxxxxxxx-xxxx-xxxxx-xxxxxxxxxxxx/resourceGroups/azpwsh-rg-test/providers/microsoft.insights/components/appinsights-portal01" = "Resource"} `
-RequestUrl "https://www.bing.com" -RequestHttpVerb "GET" -TestName 'standard-pwsh01' `
-RuleExpectedHttpStatusCode 200 -Frequency 300 -Enabled -Timeout 120 -Kind 'standard' -RetryEnabled -GeoLocation $geoLocation
```
```output
Name            Location WebTestKind ResourceGroupName  Enabled
----            -------- ----------- -----------------  -------
standard-pwsh01 westus2  standard    azpwsh-rg-test     True
```

Perintah ini membuat atau memperbarui jenis standar uji web aplikasi Insights.

Kami memasukkan tautan tersembunyi dalam `Tag` parameter untuk mengaitkan WebTest dan Aplikasi Insights.

### Contoh 2: Membuat atau memperbarui jenis ping dari uji web Aplikasi Insights
```powershell
$geoLocation = @()
```
```powershell
$geoLocation += New-AzApplicationInsightsWebTestGeolocationObject -Location "emea-nl-ams-azr"
```
```powershell
$geoLocation += New-AzApplicationInsightsWebTestGeolocationObject -Location "us-ca-sjc-azr"
```
```powershell
New-AzApplicationInsightsWebTest -ResourceGroupName azpwsh-rg-test -Name 'pingwebtest-pwsh01' -TestName 'pingwentest-pwsh01testname' -Location 'westus2' `
-Tag @{"hidden-link:/subscriptions/xxxxxxxxxx-xxxx-xxxxx-xxxxxxxxxxxx/resourceGroups/azpwsh-rg-test/providers/microsoft.insights/components/appinsights-portal01" = "Resource"} `
-GeoLocation $geoLocation -RetryEnabled -Enabled -Frequency 300 -Timeout 90 `
-Kind 'ping' -RequestUrl 'https://cn.bing.com' -RequestParseDependent -RuleExpectedHttpStatusCode 200 `
-ContentMatch "status"
```
```output
Name               Location WebTestKind ResourceGroupName   Enabled
----               -------- ----------- -----------------   -------
pingwebtest-pwsh01 westus2  ping        azpwsh-rg-test      True
```

Perintah ini membuat atau memperbarui jenis ping dari uji web Aplikasi Insights.

### Contoh 3: Membuat atau memperbarui jenis ping dari uji web Aplikasi Insights dengan konfigurasi kustom
```powershell
$geoLocation = @()
```
```powershell
$geoLocation += New-AzApplicationInsightsWebTestGeolocationObject -Location "emea-nl-ams-azr"
```
```powershell
$geoLocation += New-AzApplicationInsightsWebTestGeolocationObject -Location "us-ca-sjc-azr"
```
```powershell
New-AzApplicationInsightsWebTest -ResourceGroupName azpwsh-rg-test -Name 'pingwebtest-pwsh01' -TestName 'pingwentest-pwsh01testname' -Location 'westus2' `
-Tag @{"hidden-link:/subscriptions/xxxxxxxxxx-xxxx-xxxxx-xxxxxxxxxxxx/resourceGroups/azpwsh-rg-test/providers/microsoft.insights/components/appinsights-portal01" = "Resource"} `
-GeoLocation $geoLocation -RetryEnabled -Enabled -Frequency 300 -Timeout 90 `
-Kind 'ping' `
-Configuration "<WebTest  Name=`"basic-portal03`"  Id=`"9407db10-5d84-487f-98a3-a1ee67bb98f0`"  Enabled=`"True`"  CssProjectStructure=`"`"  CssIteration=`"`"  Timeout=`"90`"  WorkItemIds=`"`"  xmlns=`"http://microsoft.com/schemas/VisualStudio/TeamTest/2010`"  Description=`"`"  CredentialUserName=`"`"  CredentialPassword=`"`"  PreAuthenticate=`"True`"  Proxy=`"default`"  StopOnError=`"False`"  RecordedResultFile=`"`"  ResultsLocale=`"`"> 
    <Items> 
        <Request Method=`"GET`"  Guid=`"a2025e53-0702-d03e-f311-5774ec16893d`"  Version=`"1.1`"  Url=`"https://www.bing.com`"  ThinkTime=`"0`"  Timeout=`"90`"  ParseDependentRequests=`"True`"  FollowRedirects=`"True`"  RecordResult=`"True`"  Cache=`"False`"  ResponseTimeGoal=`"0`"  Encoding=`"utf-8`"  ExpectedHttpStatusCode=`"200`"  ExpectedResponseUrl=`"`"  ReportingName=`"`"  IgnoreHttpStatusCode=`"False`" /> 
    </Items> 
    <ValidationRules> 
        <ValidationRule  Classname=`"Microsoft.VisualStudio.TestTools.WebTesting.Rules.ValidationRuleFindText, Microsoft.VisualStudio.QualityTools.WebTestFramework, Version=10.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`"  DisplayName=`"Find Text`"  Description=`"Verifies the existence of the specified text in the response.`"  Level=`"High`"  ExectuionOrder=`"BeforeDependents`">
            <RuleParameters> 
            <RuleParameter Name=`"FindText`" Value=`"test&#x20;content&#x20;match`" /> 
            <RuleParameter Name=`"IgnoreCase`" Value=`"False`" /> 
            <RuleParameter Name=`"UseRegularExpression`" Value=`"False`" /> 
            <RuleParameter Name=`"PassIfTextFound`" Value=`"True`" /> 
            </RuleParameters> 
        </ValidationRule> 
    </ValidationRules> 
</WebTest>"
```
```output
Name               Location WebTestKind ResourceGroupName   Enabled
----               -------- ----------- -----------------   -------
pingwebtest-pwsh01 westus2  ping        azpwsh-rg-test      True
```

Perintah ini membuat atau memperbarui jenis ping dari uji web Aplikasi Insights dengan konfigurasi kustom.

## PARAMETERS

### -Configuration
Spesifikasi XML dari WebTest untuk dijalankan terhadap aplikasi.

```yaml
Type: System.String
Parameter Sets: CreateClassic
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContentIgnoreCase
Ketika diatur, nilai ini membuat kasus validasi ContentMatch tidak peka.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CreateStandard
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContentMatch
Konten untuk dicari dalam pengembalian WebTest.
Tidak boleh null atau kosong.

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

### -ContentPassIfTextFound
Jika true, validasi akan berlalu jika ada kecocokan untuk string ContentMatch.
Jika false, validasi akan gagal jika ada kecocokan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CreateStandard
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

### -Deskripsi
Deskripsi yang ditentukan pengguna untuk WebTest ini.

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

### -Difungsikan
Apakah tes sedang dipantau secara aktif.

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

### -Frekuensi
Interval dalam detik antara uji berjalan untuk WebTest ini.
Nilai defaultnya adalah 300.

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

### -GeoLokasi
Daftar tempat menjalankan tes secara fisik untuk memberikan cakupan global untuk aksesibilitas aplikasi Anda.
Untuk membangun, lihat bagian CATATAN untuk properti GEOLOCATION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.IWebTestGeolocation[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jenis
Jenis uji web ini, pilihan yang valid adalah ping, multistep, dan standar.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Support.WebTestKindEnum
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya

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
Nama sumber daya Aplikasi Insights WebTest.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: WebTestName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestBody
Isi string berkode Base64 untuk dikirim dengan uji web ini.

```yaml
Type: System.String
Parameter Sets: CreateStandard
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestFollowRedirect
Ikuti pengalihan untuk uji web ini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CreateStandard
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestHeader
Daftar header dan nilainya untuk ditambahkan ke panggilan WebTest.
Untuk membangun, lihat bagian CATATAN untuk properti REQUESTHEADER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.IHeaderField[]
Parameter Sets: CreateStandard
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestHttpVerb
Kata kerja http untuk digunakan untuk uji web ini.

```yaml
Type: System.String
Parameter Sets: CreateStandard
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestParseDependent
Mengurai permintaan Dependen untuk WebTest ini.

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

### -RequestUrl
Lokasi url untuk diuji.

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

### -RetryEnabled
Izinkan untuk percobaan ulang jika WebTest ini gagal.

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

### -RuleExpectedHttpStatusCode
Validasi bahwa WebTest mengembalikan kode status http yang disediakan.

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

### -RuleIgnoreHttpsStatusCode
Ketika diatur, validasi akan mengabaikan kode status.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CreateStandard
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleSslCertRemainingLifetimeCheck
Sejumlah hari untuk diperiksa masih tersisa sebelum sert SSL yang sudah ada kedaluwarsa.
Nilai harus positif dan SSLCheck harus diatur ke true.

```yaml
Type: System.Int32
Parameter Sets: CreateStandard
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleSslCheck
Memeriksa untuk melihat apakah sertifikat SSL masih valid.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CreateStandard
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
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestName
Nama yang ditentukan pengguna jika WebTest ini.

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

### -Waktu habis
Detik hingga WebTest ini akan habis dan gagal.
Nilai defaultnya adalah 30.

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

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.IWebTest

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


GEOLOCATION <IWebTestGeolocation[]>: Daftar tempat menjalankan tes secara fisik untuk memberikan cakupan global untuk aksesibilitas aplikasi Anda.
  - `[Location <String>]`: ID Lokasi untuk WebTest untuk dijalankan.

REQUESTHEADER <IHeaderField[]>: Daftar header dan nilainya untuk ditambahkan ke panggilan WebTest.
  - `[Name <String>]`: Nama header.
  - `[Value <String>]`: Nilai header.

## RELATED LINKS

