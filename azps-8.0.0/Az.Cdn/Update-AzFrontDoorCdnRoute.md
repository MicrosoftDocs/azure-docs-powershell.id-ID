---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/update-azfrontdoorcdnroute
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Update-AzFrontDoorCdnRoute.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Update-AzFrontDoorCdnRoute.md
ms.openlocfilehash: e017809ab54ab738c25e834b79832b8432253ca3
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145548291"
---
# Update-AzFrontDoorCdnRoute

## SYNOPSIS
Memperbarui rute yang sudah ada dengan nama rute yang ditentukan di bawah langganan, grup sumber daya, profil, dan titik akhir AzureFrontDoor yang ditentukan.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzFrontDoorCdnRoute -EndpointName <String> -Name <String> -ProfileName <String>
 -ResourceGroupName <String> [-SubscriptionId <String>] [-CacheConfigurationQueryParameter <String>]
 [-CacheConfigurationQueryStringCachingBehavior <AfdQueryStringCachingBehavior>]
 [-CompressionSettingContentTypesToCompress <String[]>] [-CompressionSettingIsCompressionEnabled]
 [-CustomDomain <IActivatedResourceReference[]>] [-EnabledState <EnabledState>]
 [-ForwardingProtocol <ForwardingProtocol>] [-HttpsRedirect <HttpsRedirect>]
 [-LinkToDefaultDomain <LinkToDefaultDomain>] [-OriginGroupId <String>] [-OriginPath <String>]
 [-PatternsToMatch <String[]>] [-RuleSet <IResourceReference[]>] [-SupportedProtocol <AfdEndpointProtocols[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzFrontDoorCdnRoute -InputObject <ICdnIdentity> [-CacheConfigurationQueryParameter <String>]
 [-CacheConfigurationQueryStringCachingBehavior <AfdQueryStringCachingBehavior>]
 [-CompressionSettingContentTypesToCompress <String[]>] [-CompressionSettingIsCompressionEnabled]
 [-CustomDomain <IActivatedResourceReference[]>] [-EnabledState <EnabledState>]
 [-ForwardingProtocol <ForwardingProtocol>] [-HttpsRedirect <HttpsRedirect>]
 [-LinkToDefaultDomain <LinkToDefaultDomain>] [-OriginGroupId <String>] [-OriginPath <String>]
 [-PatternsToMatch <String[]>] [-RuleSet <IResourceReference[]>] [-SupportedProtocol <AfdEndpointProtocols[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui rute yang sudah ada dengan nama rute yang ditentukan di bawah langganan, grup sumber daya, profil, dan titik akhir AzureFrontDoor yang ditentukan.

## EXAMPLES

### Contoh 1: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

### Contoh 2: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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

### -CacheConfigurationQueryParameter
parameter kueri untuk disertakan atau dikecualikan (dipisahkan koma).

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

### -CacheConfigurationQueryStringCachingBehavior
Menentukan bagaimana Frontdoor menyimpan permintaan yang menyertakan string kueri.
Anda dapat mengabaikan string kueri apa pun saat penembolokan, mengabaikan string kueri tertentu, menyimpan cache setiap permintaan dengan URL unik, atau menyimpan string kueri tertentu.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.AfdQueryStringCachingBehavior
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompressionSettingContentTypesToCompress
Daftar tipe isi tempat pemadatan berlaku.
Nilai harus berupa jenis MIME yang valid.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompressionSettingIsCompressionEnabled
Menunjukkan apakah pemadatan konten diaktifkan di AzureFrontDoor.
Nilai defaultnya adalah salah.
Jika pemadatan diaktifkan, konten akan disajikan sebagai dikompresi jika pengguna meminta versi terkompresi.
Konten tidak akan dikompresi di AzureFrontDoor saat konten yang diminta lebih kecil dari 1 byte atau lebih besar dari 1 MB.

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

### -CustomDomain
Domain yang dirujuk oleh titik akhir ini.
Untuk membuat, lihat bagian CATATAN untuk properti CUSTOMDOMAIN dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IActivatedResourceReference[]
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

### -EnabledState
Apakah akan mengaktifkan penggunaan aturan ini.
Nilai yang diizinkan adalah 'Diaktifkan' atau 'Dinonaktifkan'

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.EnabledState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndpointName
Nama titik akhir di bawah profil yang unik secara global.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForwardingProtocol
Protokol yang akan digunakan aturan ini saat meneruskan lalu lintas ke backend.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.ForwardingProtocol
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpsRedirect
Apakah akan mengalihkan lalu lintas HTTP ke lalu lintas HTTPS secara otomatis.
Perhatikan bahwa ini adalah cara mudah untuk menyiapkan aturan ini dan ini akan menjadi aturan pertama yang dijalankan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.HttpsRedirect
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LinkToDefaultDomain
apakah rute ini akan ditautkan ke domain titik akhir default.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.LinkToDefaultDomain
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama aturan perutean.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: RouteName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -OriginGroupId
ID Sumber Daya.

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

### -OriginPath
Jalur direktori pada asal yang dapat digunakan AzureFrontDoor untuk mengambil konten, misalnya contoso.cloudapp.net/originpath.

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

### -PatternsToMatch
Pola rute aturan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileName
Nama profil Premium Azure Front Door Standard atau Azure Front Door yang unik dalam grup sumber daya.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup Sumber Daya dalam langganan Azure.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleSet
seperangkat aturan yang dirujuk oleh titik akhir ini.
Untuk membuat, lihat bagian CATATAN untuk properti RULESET dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IResourceReference[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID Langganan Azure.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportedProtocol
Daftar protokol yang didukung untuk rute ini.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.AfdEndpointProtocols[]
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IRoute

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CUSTOMDOMAIN <IActivatedResourceReference[]>: Domain yang direferensikan oleh titik akhir ini.
  - `[Id <String>]`: ID Sumber Daya.

INPUTOBJECT <ICdnIdentity>: Parameter Identitas
  - `[CustomDomainName <String>]`: Nama domain di bawah profil yang unik secara global.
  - `[EndpointName <String>]`: Nama titik akhir di bawah profil yang unik secara global.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[OriginGroupName <String>]`: Nama grup asal yang unik dalam titik akhir.
  - `[OriginName <String>]`: Nama asal yang unik dalam profil.
  - `[ProfileName <String>]`: Nama profil Azure Front Door Standard atau Azure Front Door Premium atau CDN yang unik dalam grup sumber daya.
  - `[ResourceGroupName <String>]`: Nama grup Sumber Daya dalam langganan Azure.
  - `[RouteName <String>]`: Nama aturan perutean.
  - `[RuleName <String>]`: Nama aturan pengiriman yang unik dalam titik akhir.
  - `[RuleSetName <String>]`: Nama seperangkat aturan di bawah profil yang unik secara global.
  - `[SecretName <String>]`: Nama Rahasia di bawah profil.
  - `[SecurityPolicyName <String>]`: Nama kebijakan keamanan di bawah profil.
  - `[SubscriptionId <String>]`: ID Langganan Azure.

RULESET <IResourceReference[]>: seperangkat aturan yang direferensikan oleh titik akhir ini.
  - `[Id <String>]`: ID Sumber Daya.

## RELATED LINKS

