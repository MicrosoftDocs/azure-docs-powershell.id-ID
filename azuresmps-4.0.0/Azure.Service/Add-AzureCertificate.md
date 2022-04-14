---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 9A6D5C40-2532-4FD1-A74F-16725CAD8EDD
online version: ''
schema: 2.0.0
ms.openlocfilehash: d15b97a6a98da7c38c40c5c7c17ad110ee319d59
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142095897"
---
# Add-AzureCertificate

## SYNOPSIS
Mengunggah sertifikat ke layanan awan Azure.

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

Perintah pertama mendapatkan sertifikat dari bursa MY pengguna dengan menggunakan cmdlet **Get-Item** inti Windows PowerShell.
Perintah menyimpan sertifikat dalam variabel $Certificate.

Perintah kedua mengunggah sertifikat di $certificate ke layanan awan.

## PARAMETERS

### -CertToDeploy
Menentukan sertifikat yang akan disebarkan.
Anda dapat menentukan jalur lengkap file sertifikat, seperti file yang memiliki *.cer atau *.
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
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Menentukan nama layanan Azure tempat cmdlet ini menambahkan sertifikat.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ManagementOperationContext

## CATATAN

## RELATED LINKS

[Get-AzureCertificate](./Get-AzureCertificate.md)

[AzureCertificateSetting baru](./New-AzureCertificateSetting.md)

[Hapus-AzureCertificate](./Remove-AzureCertificate.md)


