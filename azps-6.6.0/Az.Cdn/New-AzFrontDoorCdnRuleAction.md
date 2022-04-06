---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azfrontdoorcdnruleaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnRuleAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnRuleAction.md
ms.openlocfilehash: 57251e4b99a8449acb18b0f5782954477b9690a6
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140287591"
---
# New-AzFrontDoorCdnRuleAction

## SYNOPSIS
Membuat tindakan aturan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.cdn/new-azfrontdoorcdnruleaction) untuk informasi terkini.

## SYNTAX

### AfdRuleCacheExpirationAction (Default)
```
New-AzFrontDoorCdnRuleAction -CacheBehavior <String> [-CacheDuration <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AfdRuleHeaderTypeAction
```
New-AzFrontDoorCdnRuleAction -HeaderType <String> -HeaderAction <String> -HeaderName <String>
 [-HeaderValue <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AfdRuleCacheKeyQueryStringAction
```
New-AzFrontDoorCdnRuleAction -QueryStringBehavior <String> -QueryParameters <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AfdRuleUrlRedirectAction
```
New-AzFrontDoorCdnRuleAction -RedirectType <String> [-DestinationProtocol <String>] [-CustomPath <String>]
 [-CustomHostname <String>] [-CustomQueryString <String>] [-CustomFragment <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AfdRuleUrlRewriteAction
```
New-AzFrontDoorCdnRuleAction -SourcePattern <String> -Destination <String> [-PreservePath]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AfdRuleOriginGroupOverrideAction
```
New-AzFrontDoorCdnRuleAction -OriginGroupOverride <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat tindakan aturan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzFrontDoorCdnRuleAction -CacheBehavior BypassCache
```

Membuat tindakan aturan.

## PARAMETERS

### -CacheBeaviior
Perilaku cache untuk tindakan.

```yaml
Type: String
Parameter Sets: AfdRuleCacheExpirationAction
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheDuration
Durasi untuk konten yang diperlukan untuk disingginggasi.
Format yang diperbolehkan adalah \[d.\] hh:mm:ss

```yaml
Type: String
Parameter Sets: AfdRuleCacheExpirationAction
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomFragment
Fragmen untuk ditambahkan ke URL pengalihan.
Fragmen adalah bagian dari URL yang muncul setelah #.
Jangan sertakan #.

```yaml
Type: String
Parameter Sets: AfdRuleUrlRedirectAction
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomHostname
Host untuk mengalihkan.
Biarkan kosong untuk menggunakan host masuk sebagai host tujuan.

```yaml
Type: String
Parameter Sets: AfdRuleUrlRedirectAction
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomPath
Jalur lengkap untuk mengalihkan.
Jalur tidak boleh kosong dan harus dimulai dengan /.
Biarkan kosong untuk menggunakan jalur masuk sebagai jalur tujuan.

```yaml
Type: String
Parameter Sets: AfdRuleUrlRedirectAction
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomQueryString
Kumpulan string kueri yang akan ditempatkan di URL pengalihan.
Pengaturan nilai ini akan mengganti setiap string kueri yang sudah ada; biarkan kosong untuk mempertahankan string kueri masuk.
String kueri harus dalam \<key\>=\<value\> format.
? dan & akan ditambahkan secara otomatis, jadi jangan sertakan mereka.

```yaml
Type: String
Parameter Sets: AfdRuleUrlRedirectAction
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tujuan
Tentukan URL relatif yang menjadi tujuan penulisan ulang permintaan di atas.

```yaml
Type: String
Parameter Sets: AfdRuleUrlRewriteAction
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationProtocol
Protokol untuk digunakan untuk pengalihan.
Nilai defaultnya adalah MatchRequest.

```yaml
Type: String
Parameter Sets: AfdRuleUrlRedirectAction
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HeaderAction
Tindakan yang akan dilakukan.

```yaml
Type: String
Parameter Sets: AfdRuleHeaderTypeAction
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HeaderName
Nama header untuk diubah.

```yaml
Type: String
Parameter Sets: AfdRuleHeaderTypeAction
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HeaderType
Baik mengubah header permintaan atau header respons.

```yaml
Type: String
Parameter Sets: AfdRuleHeaderTypeAction
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HeaderValue
Nilai untuk tindakan tertentu.

```yaml
Type: String
Parameter Sets: AfdRuleHeaderTypeAction
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OriginGroupOverride
Menentukan tindakan penggantian grup origin untuk aturan pengiriman.

```yaml
Type: String
Parameter Sets: AfdRuleOriginGroupOverrideAction
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreservePath
Apakah akan mempertahankan jalur yang tidak cocok.

```yaml
Type: SwitchParameter
Parameter Sets: AfdRuleUrlRewriteAction
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QueryParameters
Parameter kueri untuk menyertakan atau mengecualikan (dipisahkan koma).

```yaml
Type: String
Parameter Sets: AfdRuleCacheKeyQueryStringAction
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QueryStringBestringior
Menentukan parameter untuk tindakan string kueri kunci cache.
Nilai yang diterima : Include, IncludeAll, Exclude, ExcludeAll

```yaml
Type: String
Parameter Sets: AfdRuleCacheKeyQueryStringAction
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectType
Tipe pengalihan aturan akan digunakan saat mengalihkan lalu lintas.

```yaml
Type: String
Parameter Sets: AfdRuleUrlRedirectAction
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourcePattern
Tentukan pola URI permintaan yang mengidentifikasi tipe permintaan yang mungkin ditulis ulang.
Jika nilai kosong, semua string akan cocok.

```yaml
Type: String
Parameter Sets: AfdRuleUrlRewriteAction
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdRuleAction

## CATATAN

## RELATED LINKS
