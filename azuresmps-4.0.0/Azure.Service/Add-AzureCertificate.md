---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 9A6D5C40-2532-4FD1-A74F-16725CAD8EDD
online version: ''
schema: 2.0.0
ms.openlocfilehash: d15b97a6a98da7c38c40c5c7c17ad110ee319d59
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426275"
---
# Add-AzureCertificate

## SYNOPSIS
Mengunggah sertifikat ke layanan cloud Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

```
Add-AzureCertificate [-ServiceName] <String> [-CertToDeploy] <Object> [-Password <String>]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureCertificate** mengunggah sertifikat untuk layanan Azure.

## EXAMPLES

### Contoh 1: Upload sertifikat dan kata sandi
```
PS C:\> Add-AzureCertificate -ServiceName "ContosoService" -CertToDeploy ContosoCertificate.pfx -Password "password"
```

Perintah ini mengunggah file sertifikat ContosoCertificate.pfx ke layanan awan.
Perintah menentukan kata sandi untuk sertifikat.

### Contoh 2: Upload file sertifikat
```
PS C:\> Add-AzureCertificate -serviceName "MyService" -CertToDeploy ContosoCertificate.cer
```

Perintah ini mengunggah file sertifikat ContosoCertificate.cer ke layanan awan.
Perintah menentukan kata sandi untuk sertifikat.

### Contoh 3: Upload objek sertifikat
```
PS C:\> $Certificate = Get-Item cert:\PATTIFULLER\MY\1D6E34B526723E06C235BE8E5457784BF12C9F39
PS C:\> Add-AzureCertificate -ServiceName "ContosoService" -CertToDeploy $Certificate
```

Perintah pertama mendapatkan sertifikat dari penyimpanan MY pengguna menggunakan cmdlet **Get-Item** inti Windows PowerShell.
Perintah menyimpan sertifikat dalam $Certificate variabel.

Perintah kedua mengunggah sertifikat di $certificate ke layanan awan.

## PARAMETERS

### -CertToDeploy
Menentukan sertifikat untuk digunakan.
Anda bisa menentukan jalur lengkap dari file sertifikat, seperti file yang memiliki *.cer atau *.
ekstensi nama file pfx, atau objek Sertifikat X.509.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Menentukan kata sandi sertifikat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceName
Menentukan nama layanan Azure yang menambahkan sertifikat oleh cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### ManagementOperationContext

## CATATAN

## RELATED LINKS

[Get-AzureCertificate](./Get-AzureCertificate.md)

[New-AzureCertificateSetting](./New-AzureCertificateSetting.md)

[Remove-AzureCertificate](./Remove-AzureCertificate.md)


