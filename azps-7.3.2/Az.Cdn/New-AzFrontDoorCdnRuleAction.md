---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azfrontdoorcdnruleaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnRuleAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnRuleAction.md
ms.openlocfilehash: b248ea6e7163eb99230d5ce343e49eea29e33190
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142073407"
---
# New-AzFrontDoorCdnRuleAction

## SYNOPSIS
Membuat tindakan aturan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cdn/new-azfrontdoorcdnruleaction) untuk informasi terbaru.

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
New-AzFrontDoorCdnRuleAction -CacheBehavior BypassCache
```

Membuat tindakan aturan.

## PARAMETERS

### -CacheBehavior
Singgahan perilaku untuk tindakan tersebut.

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
Durasi yang kontennya perlu disinggahkan.
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
Jangan sertakan kesalahan #.

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
Mengatur nilai ini akan menggantikan string kueri yang sudah ada; biarkan kosong untuk mempertahankan string kueri masuk.
String kueri harus dalam \<key\>=\<value\> format.
? dan & akan ditambahkan secara otomatis, jadi jangan sertakan.

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
Tentukan URL relatif tempat permintaan di atas akan ditulis ulang.

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
Tindakan untuk dijalankan.

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
Apakah mengubah header permintaan atau header respons.

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
Nilai untuk tindakan yang ditentukan.

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
Menentukan tindakan pengesampingan grup asal untuk aturan pengiriman.

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
Parameter kueri untuk disertakan atau dikecualikan (dipisahkan koma).

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

### -QueryStringBehavior
Menentukan parameter untuk tindakan string kueri kunci singgahan.
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
Jika nilai kosong, semua string cocok.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdRuleAction

## CATATAN

## RELATED LINKS
