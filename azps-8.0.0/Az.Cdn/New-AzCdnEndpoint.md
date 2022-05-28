---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azcdnendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnEndpoint.md
ms.openlocfilehash: e7e78642cfaad3fd156a3af8a3facc120af71836
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145499821"
---
# New-AzCdnEndpoint

## SYNOPSIS
Membuat titik akhir CDN baru dengan nama titik akhir yang ditentukan di bawah langganan, grup sumber daya, dan profil yang ditentukan.

## SYNTAX

```
New-AzCdnEndpoint -Name <String> -ProfileName <String> -ResourceGroupName <String> -Location <String>
 [-SubscriptionId <String>] [-ContentTypesToCompress <String[]>] [-DefaultOriginGroupId <String>]
 [-DeliveryPolicyDescription <String>] [-DeliveryPolicyRule <IDeliveryRule[]>] [-GeoFilter <IGeoFilter[]>]
 [-IsCompressionEnabled] [-IsHttpAllowed] [-IsHttpsAllowed] [-OptimizationType <OptimizationType>]
 [-Origin <IDeepCreatedOrigin[]>] [-OriginGroup <IDeepCreatedOriginGroup[]>] [-OriginHostHeader <String>]
 [-OriginPath <String>] [-ProbePath <String>] [-QueryStringCachingBehavior <QueryStringCachingBehavior>]
 [-Tag <Hashtable>] [-UrlSigningKey <IUrlSigningKey[]>] [-WebApplicationFirewallPolicyLinkId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat titik akhir CDN baru dengan nama titik akhir yang ditentukan di bawah langganan, grup sumber daya, dan profil yang ditentukan.

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

### -IsCompressionEnabled
Menunjukkan apakah pemadatan konten diaktifkan pada CDN.
Nilai defaultnya adalah salah.
Jika pemadatan diaktifkan, konten akan disajikan sebagai dikompresi jika permintaan pengguna untuk versi terkompresi.
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
Menunjukkan apakah lalu lintas HTTP diizinkan pada titik akhir.
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

### -Lokasi
Lokasi sumber daya.

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

### -Name
Nama titik akhir di bawah profil yang unik secara global.

```yaml
Type: System.String
Parameter Sets: (All)
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
Menentukan skenario apa yang diinginkan pelanggan untuk titik akhir CDN ini untuk dioptimalkan, misalnya Unduh, layanan Media.
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

### -Origin
Sumber konten yang dikirimkan melalui CDN.
Untuk membuat, lihat bagian CATATAN untuk properti ORIGIN dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IDeepCreatedOrigin[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OriginGroup
Grup asal yang terdiri dari asal yang digunakan untuk menyeimbangkan beban lalu lintas berdasarkan ketersediaan.
Untuk membuat, lihat bagian CATATAN untuk properti ORIGINGROUP dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IDeepCreatedOriginGroup[]
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
Azure CDN asal, seperti Web Apps, Blob Storage, dan Cloud Services memerlukan nilai header host ini agar sesuai dengan nama host asal secara default.

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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QueryStringCachingBehavior
Menentukan bagaimana CDN membuat cache permintaan yang menyertakan string kueri.
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
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya.

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

GEOFILTER <IGeoFilter[]>: Daftar aturan yang menentukan akses geo pengguna dalam titik akhir CDN. Setiap filter geografis menentukan aturan akses ke jalur atau konten tertentu, misalnya memblokir APAC untuk jalur /gambar/
  - `Action <GeoFilterActions>`: Tindakan filter geografis, yaitu mengizinkan atau memblokir akses.
  - `CountryCode <String[]>`: Kode negara atau wilayah dua huruf yang menentukan akses negara atau wilayah pengguna dalam filter geografis, misalnya AU, MX, AS.
  - `RelativePath <String>`: Jalur relatif yang berlaku untuk filter geografis. (misalnya '/mypictures', '/mypicture/kitty.jpg', dan lain-lain.)

ORIGIN <IDeepCreatedOrigin[]>: Sumber konten yang dikirimkan melalui CDN.
  - `Name <String>`: Nama asal yang harus unik dalam titik akhir. 
  - `[Enabled <Boolean?>]`: Asal diaktifkan untuk penyeimbangan beban atau tidak. Secara default, asal selalu diaktifkan.
  - `[HostName <String>]`: Alamat asal. Ini bisa berupa nama domain, alamat IPv4, atau alamat IPv6. Ini harus unik di semua asal dalam titik akhir.
  - `[HttpPort <Int32?>]`: Nilai port HTTP. Harus antara 1 dan 65535.
  - `[HttpsPort <Int32?>]`: Nilai port HTTPS. Harus antara 1 dan 65535.
  - `[OriginHostHeader <String>]`: Nilai header host yang dikirim ke asal dengan setiap permintaan. Jika Anda membiarkan ini kosong, nama host permintaan menentukan nilai ini. Azure CDN asal, seperti Web Apps, Blob Storage, dan Cloud Services memerlukan nilai header host ini agar sesuai dengan nama host asal secara default.
  - `[Priority <Int32?>]`: Prioritas asal dalam grup asal yang diberikan untuk penyeimbangan beban. Prioritas yang lebih tinggi tidak akan digunakan untuk penyeimbangan beban jika asal prioritas yang lebih rendah sehat. Harus antara 1 dan 5.
  - `[PrivateLinkAlias <String>]`: Alias sumber daya Private Link. Mengisi bidang opsional ini menunjukkan bahwa asal ini adalah 'Privat'
  - `[PrivateLinkApprovalMessage <String>]`: Pesan kustom yang akan disertakan dalam permintaan persetujuan untuk menyambungkan ke Private Link.
  - `[PrivateLinkLocation <String>]`: Lokasi sumber daya Private Link. Diperlukan hanya jika 'privateLinkResourceId' diisi
  - `[PrivateLinkResourceId <String>]`: Id Sumber Daya dari sumber daya Private Link. Mengisi bidang opsional ini menunjukkan bahwa backend ini adalah 'Privat'
  - `[Weight <Int32?>]`: Berat asal dalam grup asal yang diberikan untuk penyeimbangan beban. Harus antara 1 dan 1000

ORIGINGROUP <IDeepCreatedOriginGroup[]>: Grup asal yang terdiri dari asal yang digunakan untuk menyeimbangkan beban lalu lintas berdasarkan ketersediaan.
  - `Name <String>`: Nama grup asal yang harus unik dalam titik akhir.
  - `[HealthProbeSetting <IHealthProbeParameters>]`: Pengaturan pemeriksaan kesehatan ke asal yang digunakan untuk menentukan kesehatan asal.
    - `[ProbeIntervalInSecond <Int32?>]`: Jumlah detik antara pemeriksaan kesehatan. Defaultnya adalah 240 detik.
    - `[ProbePath <String>]`: Jalur relatif terhadap asal yang digunakan untuk menentukan kesehatan asal.
    - `[ProbeProtocol <ProbeProtocol?>]`: Protokol yang digunakan untuk pemeriksaan kesehatan.
    - `[ProbeRequestType <HealthProbeRequestType?>]`: Jenis permintaan pemeriksaan kesehatan yang dibuat.
  - `[Origin <IResourceReference[]>]`: Sumber konten yang dikirimkan melalui CDN dalam grup asal tertentu.
    - `[Id <String>]`: ID Sumber Daya.
  - `[ResponseBasedOriginErrorDetectionSetting <IResponseBasedOriginErrorDetectionParameters>]`: Objek JSON yang berisi properti untuk menentukan kesehatan asal menggunakan permintaan/respons nyata. Properti ini saat ini tidak didukung.
    - `[HttpErrorRange <IHttpErrorRangeParameters[]>]`: Daftar rentang kode status Http yang dianggap sebagai kesalahan server untuk asal dan ditandai sebagai tidak sehat.
      - `[Begin <Int32?>]`: Awal inklusif dari rentang kode status http.
      - `[End <Int32?>]`: Akhir inklusif dari rentang kode status http.
    - `[ResponseBasedDetectedErrorType <ResponseBasedDetectedErrorTypes?>]`: Jenis kesalahan respons untuk permintaan pengguna nyata yang asalnya akan dianggap tidak sehat
    - `[ResponseBasedFailoverThresholdPercentage <Int32?>]`: Persentase permintaan yang gagal dalam sampel di mana failover harus dipicu.
  - `[TrafficRestorationTimeToHealedOrNewEndpointsInMinute <Int32?>]`: Waktu dalam menit untuk mengalihkan lalu lintas ke titik akhir secara bertahap ketika titik akhir yang tidak sehat menjadi sehat atau titik akhir baru ditambahkan. Defaultnya adalah 10 menit. Properti ini saat ini tidak didukung.

URLSIGNINGKEY <IUrlSigningKey[]>: Daftar kunci yang digunakan untuk memvalidasi hash URL yang ditandatangani.
  - `KeyId <String>`: Menentukan ID kunci yang ditentukan pelanggan. Id ini akan ada dalam permintaan masuk untuk menunjukkan kunci yang digunakan untuk membentuk hash.
  - `KeySourceParameterResourceGroupName <String>`: Grup sumber daya Key Vault pengguna yang berisi rahasia
  - `KeySourceParameterSecretName <String>`: Nama rahasia dalam Key Vault.
  - `KeySourceParameterSecretVersion <String>`: Versi (GUID) rahasia dalam Key Vault.
  - `KeySourceParameterSubscriptionId <String>`: Id Langganan Key Vault pengguna yang berisi rahasia
  - `KeySourceParameterVaultName <String>`: Nama Key Vault pengguna yang berisi rahasia

## RELATED LINKS

