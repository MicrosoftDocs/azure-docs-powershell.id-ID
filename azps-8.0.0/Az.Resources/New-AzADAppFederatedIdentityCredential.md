---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azadappfederatedidentitycredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzADAppFederatedIdentityCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzADAppFederatedIdentityCredential.md
ms.openlocfilehash: e60c54e89433a1cf4ec5cc28adf186fb4f47061e
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145551948"
---
# New-AzADAppFederatedIdentityCredential

## SYNOPSIS
Buat federatedIdentityCredential untuk aplikasi.

## SYNTAX

```
New-AzADAppFederatedIdentityCredential -ApplicationObjectId <String> -Audience <String[]> -Issuer <String>
 -Name <String> -Subject <String> [-AdditionalProperties <Hashtable>] [-Description <String>]
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Buat federatedIdentityCredential untuk aplikasi.

## EXAMPLES

### Contoh 1: Membuat kredensial identitas federasi untuk aplikasi
```powershell
New-AzADappfederatedidentitycredential -ApplicationObjectId $appObjectId -Audience api://AzureADTokenExchange -Issuer https://login.microsoftonline.com/3d1e2be9-a10a-4a0c-8380-7ce190f98ed9/v2.0 -name 'test-cred' -Subject 'subject'
```

Membuat kredensial identitas federasi untuk aplikasi

## PARAMETERS

### -AdditionalProperties
Parameter Tambahan

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

### -ApplicationObjectId
key: id aplikasi

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

### -Audiens
Mencantumkan audiens yang bisa muncul di token eksternal.
Bidang ini wajib, dan default ke 'api://AzureADTokenExchange'.
Dikatakan apa yang harus diterima platform identitas Microsoft dalam klaim aud dalam token masuk.
Nilai ini mewakili Azure AD di penyedia identitas eksternal Anda dan tidak memiliki nilai tetap di seluruh penyedia identitas - Anda mungkin perlu membuat pendaftaran aplikasi baru di IdP Anda untuk berfungsi sebagai audiens token ini.
Wajib diisi.

```yaml
Type: System.String[]
Parameter Sets: (All)
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

### -Deskripsi
Deskripsi kredensial identitas federasi yang tidak divalidasi dan disediakan pengguna.
Opsional.

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

### -Pengeluar sertifikat
URL penyedia identitas eksternal dan harus cocok dengan klaim penerbit token eksternal yang dipertukarkan.
Kombinasi nilai penerbit dan subjek harus unik di aplikasi.
Wajib diisi.

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
adalah pengidentifikasi unik untuk kredensial identitas federasi, yang memiliki batas karakter 120 karakter dan harus ramah URL.
Hal ini tidak dapat diubah setelah dibuat.
Wajib diisi.
Tidak dapat diubah ke null.
Mendukung $filter (eq).

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

### -Subjek
Wajib diisi.
Pengidentifikasi beban kerja perangkat lunak eksternal dalam penyedia identitas eksternal.
Seperti nilai audiens, ia tidak memiliki format tetap, karena setiap IdP menggunakan sendiri - kadang-kadang GUID, kadang-kadang pengidentifikasi yang dibatasi titik dua, kadang-kadang string arbitrer.
Nilai di sini harus cocok dengan sub klaim dalam token yang disajikan ke Azure AD.
Kombinasi pengeluar sertifikat dan subjek harus unik di aplikasi.
Mendukung $filter (eq).

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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10Beta.IMicrosoftGraphFederatedIdentityCredential

## NOTES

ALIAS

## RELATED LINKS
