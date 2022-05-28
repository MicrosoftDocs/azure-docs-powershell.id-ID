---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/update-azcdnendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Update-AzCdnEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Update-AzCdnEndpoint.md
ms.openlocfilehash: 29efae654a53440fc425ef8a9bcb36cb48dafce5
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145546499"
---
# Update-AzCdnEndpoint

## SYNOPSIS
Memperbarui titik akhir CDN yang sudah ada dengan nama titik akhir yang ditentukan di bawah langganan, grup sumber daya, dan profil yang ditentukan.
Hanya tag yang dapat diperbarui setelah membuat titik akhir.
Untuk memperbarui asal, gunakan operasi Perbarui Asal.
Untuk memperbarui grup asal, gunakan operasi Perbarui grup Asal.
Untuk memperbarui domain kustom, gunakan operasi Perbarui Domain Kustom.

## SYNTAX

### UpdateExpanded1 (Default)
```
Update-AzCdnEndpoint -Name <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-ContentTypesToCompress <String[]>] [-DefaultOriginGroupId <String>]
 [-DeliveryPolicyDescription <String>] [-DeliveryPolicyRule <IDeliveryRule[]>] [-GeoFilter <IGeoFilter[]>]
 [-IsCompressionEnabled] [-IsHttpAllowed] [-IsHttpsAllowed] [-OptimizationType <OptimizationType>]
 [-OriginHostHeader <String>] [-OriginPath <String>] [-ProbePath <String>]
 [-QueryStringCachingBehavior <QueryStringCachingBehavior>] [-Tag <Hashtable>]
 [-UrlSigningKey <IUrlSigningKey[]>] [-WebApplicationFirewallPolicyLinkId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded1
```
Update-AzCdnEndpoint -InputObject <ICdnIdentity> [-ContentTypesToCompress <String[]>]
 [-DefaultOriginGroupId <String>] [-DeliveryPolicyDescription <String>]
 [-DeliveryPolicyRule <IDeliveryRule[]>] [-GeoFilter <IGeoFilter[]>] [-IsCompressionEnabled] [-IsHttpAllowed]
 [-IsHttpsAllowed] [-OptimizationType <OptimizationType>] [-OriginHostHeader <String>] [-OriginPath <String>]
 [-ProbePath <String>] [-QueryStringCachingBehavior <QueryStringCachingBehavior>] [-Tag <Hashtable>]
 [-UrlSigningKey <IUrlSigningKey[]>] [-WebApplicationFirewallPolicyLinkId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui titik akhir CDN yang sudah ada dengan nama titik akhir yang ditentukan di bawah langganan, grup sumber daya, dan profil yang ditentukan.
Hanya tag yang dapat diperbarui setelah membuat titik akhir.
Untuk memperbarui asal, gunakan operasi Perbarui Asal.
Untuk memperbarui grup asal, gunakan operasi Perbarui grup Asal.
Untuk memperbarui domain kustom, gunakan operasi Perbarui Domain Kustom.

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

### -ContentTypesToCompress
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

### -DefaultOriginGroupId
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

### -DeliveryPolicyDescription
Deskripsi kebijakan yang mudah digunakan.

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

### -DeliveryPolicyRule
Daftar aturan pengiriman.
Untuk membuat, lihat bagian CATATAN untuk properti DELIVERYPOLICYRULE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IDeliveryRule[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GeoFilter
Daftar aturan yang menentukan akses geografis pengguna dalam titik akhir CDN.
Setiap filter geografis menentukan aturan akses ke jalur atau konten tertentu, misalnya memblokir APAC untuk jalur /gambar/ Untuk membangun, lihat bagian CATATAN untuk properti GEOFILTER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IGeoFilter[]
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
Parameter Sets: UpdateViaIdentityExpanded1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsCompressionEnabled
Menunjukkan apakah pemadatan konten diaktifkan pada CDN.
Nilai defaultnya adalah salah.
Jika pemadatan diaktifkan, konten akan disajikan sebagai dikompresi jika pengguna meminta versi terkompresi.
Konten tidak akan dikompresi pada CDN saat konten yang diminta lebih kecil dari 1 byte atau lebih besar dari 1 MB.

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

### -IsHttpAllowed
Menunjukkan apakah lalu lintas HTTP diizinkan di titik akhir.
Nilai defaultnya adalah benar.
Setidaknya satu protokol (HTTP atau HTTPS) harus diizinkan.

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

### -IsHttpsAllowed
Menunjukkan apakah lalu lintas HTTPS diizinkan di titik akhir.
Nilai defaultnya adalah benar.
Setidaknya satu protokol (HTTP atau HTTPS) harus diizinkan.

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

### -Name
Nama titik akhir di bawah profil yang unik secara global.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded1
Aliases: EndpointName

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

### -OptimizationType
Menentukan skenario apa yang diinginkan pelanggan untuk titik akhir CDN ini untuk dioptimalkan, misalnya Unduh, Layanan media.
Dengan informasi ini, CDN dapat menerapkan pengoptimalan berbasis skenario.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.OptimizationType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OriginHostHeader
Nilai header host dikirim ke asal dengan setiap permintaan.
Properti di Titik Akhir ini hanya diperbolehkan ketika titik akhir menggunakan asal tunggal dan dapat ditimpa oleh properti yang sama yang ditentukan pada asal. Jika Anda membiarkan ini kosong, nama host permintaan menentukan nilai ini.
Azure CDN asal, seperti Web Apps, Storage Blob, dan Cloud Services memerlukan nilai header host ini agar sesuai dengan nama host asal secara default.

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
Jalur direktori pada asal yang dapat digunakan CDN untuk mengambil konten, misalnya contoso.cloudapp.net/originpath.

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

### -ProbePath
Jalur ke file yang dihosting di asal yang membantu mempercepat pengiriman konten dinamis dan menghitung rute yang paling optimal untuk CDN.
Ini relatif terhadap jalur asal.
Properti ini hanya relevan saat menggunakan satu asal.

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

### -ProfileName
Nama profil CDN yang unik dalam grup sumber daya.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QueryStringCachingBehavior
Menentukan bagaimana CDN permintaan cache yang menyertakan string kueri.
Anda dapat mengabaikan string kueri apa pun saat penembolokan, melewati penembolokan untuk mencegah permintaan yang berisi string kueri di-cache, atau menyimpan cache setiap permintaan dengan URL unik.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.QueryStringCachingBehavior
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup Sumber Daya dalam langganan Azure.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID Langganan Azure.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag titik akhir.

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

### -UrlSigningKey
Daftar kunci yang digunakan untuk memvalidasi hash URL yang ditandatangani.
Untuk membuat, lihat bagian CATATAN untuk properti URLSIGNINGKEY dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IUrlSigningKey[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebApplicationFirewallPolicyLinkId
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IEndpoint

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


DELIVERYPOLICYRULE <IDeliveryRule[]>: Daftar aturan pengiriman.
  - `Action <IDeliveryRuleAction1[]>`: Daftar tindakan yang dijalankan ketika semua kondisi aturan terpenuhi.
    - `Name <DeliveryRuleAction>`: Nama tindakan untuk aturan pengiriman.
  - `Order <Int32>`: Urutan penerapan aturan untuk titik akhir. Nilai yang mungkin {0,1,2,3,.........}. Aturan dengan urutan yang lebih rendah akan diterapkan sebelum aturan dengan urutan yang lebih besar. Aturan dengan urutan 0 adalah aturan khusus. Ini tidak memerlukan kondisi dan tindakan apa pun yang tercantum di dalamnya akan selalu diterapkan.
  - `[Condition <IDeliveryRuleCondition[]>]`: Daftar kondisi yang harus dicocokkan agar tindakan dijalankan
    - `Name <MatchVariable>`: Nama kondisi untuk aturan pengiriman.
  - `[Name <String>]`: Nama aturan

GEOFILTER <IGeoFilter[]>: Daftar aturan yang menentukan akses geo pengguna dalam titik akhir CDN. Setiap filter geografis mendefinisikan aturan akses ke jalur atau konten tertentu, misalnya memblokir APAC untuk jalur /pictures/
  - `Action <GeoFilterActions>`: Tindakan filter geografis, yaitu mengizinkan atau memblokir akses.
  - `CountryCode <String[]>`: Dua kode negara atau wilayah huruf yang menentukan akses negara atau wilayah pengguna dalam filter geografis, misalnya AU, MX, AS.
  - `RelativePath <String>`: Jalur relatif yang berlaku untuk filter geografis. (misalnya '/mypictures', '/mypicture/kitty.jpg', dan lain-lain.)

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

URLSIGNINGKEY <IUrlSigningKey[]>: Daftar kunci yang digunakan untuk memvalidasi hash URL yang ditandatangani.
  - `KeyId <String>`: Menentukan Id kunci yang ditentukan pelanggan. Id ini akan ada dalam permintaan masuk untuk menunjukkan kunci yang digunakan untuk membentuk hash.
  - `KeySourceParameterResourceGroupName <String>`: Grup sumber daya Key Vault pengguna yang berisi rahasia
  - `KeySourceParameterSecretName <String>`: Nama rahasia dalam Key Vault.
  - `KeySourceParameterSecretVersion <String>`: Versi (GUID) rahasia dalam Key Vault.
  - `KeySourceParameterSubscriptionId <String>`: Id Langganan Key Vault pengguna yang berisi rahasia
  - `KeySourceParameterVaultName <String>`: Nama Key Vault pengguna yang berisi rahasia

## RELATED LINKS

