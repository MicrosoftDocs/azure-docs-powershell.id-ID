---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/update-azadappfederatedidentitycredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzADAppFederatedIdentityCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Update-AzADAppFederatedIdentityCredential.md
ms.openlocfilehash: d2e766c85ddfb27a94fb44b5e56719a148a6d2f0
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145619235"
---
# Update-AzADAppFederatedIdentityCredential

## SYNOPSIS
Perbarui federatedIdentityCredentials dalam aplikasi.

## SYNTAX

```
Update-AzADAppFederatedIdentityCredential -ApplicationObjectId <String> -Id <String>
 [-AdditionalProperties <Hashtable>] [-Audience <String[]>] [-Description <String>] [-Issuer <String>]
 [-Subject <String>] [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Perbarui federatedIdentityCredentials dalam aplikasi.

## EXAMPLES

### Contoh 1: Memperbarui subjek untuk kredensial identitas federasi
```powershell
Update-AzADappfederatedidentitycredential -ApplicationObjectId $appObjectId -Id $credentialId -Subject 'subject'
```

Memperbarui subjek untuk kredensial identitas federasi

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
kunci: id aplikasi

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
Ini mengatakan apa yang harus platform identitas Microsoft terima dalam klaim aud dalam token masuk.
Nilai ini mewakili Azure AD di penyedia identitas eksternal Anda dan tidak memiliki nilai tetap di seluruh penyedia identitas - Anda mungkin perlu membuat pendaftaran aplikasi baru di IdP Anda untuk berfungsi sebagai audiens token ini.
Wajib diisi.

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

### -Id
kunci: id federatedIdentityCredential

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

### -Pengeluar sertifikat
URL penyedia identitas eksternal dan harus cocok dengan klaim penerbit token eksternal yang ditukar.
Kombinasi nilai pengeluar sertifikat dan subjek harus unik di aplikasi.
Wajib diisi.

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

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -Subjek
Wajib diisi.
Pengidentifikasi beban kerja perangkat lunak eksternal dalam penyedia identitas eksternal.
Seperti nilai audiens, ia tidak memiliki format tetap, karena setiap penyedia identitas menggunakan sendiri - kadang-kadang GUID, kadang-kadang pengidentifikasi yang dibatasi titik dua, kadang-kadang string arbitrer.
Nilai di sini harus cocok dengan sub klaim dalam token yang disajikan ke Azure AD.
Kombinasi pengeluar sertifikat dan subjek harus unik di aplikasi.
Mendukung $filter (eq).

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

### System.Boolean

## NOTES

ALIAS

## RELATED LINKS
