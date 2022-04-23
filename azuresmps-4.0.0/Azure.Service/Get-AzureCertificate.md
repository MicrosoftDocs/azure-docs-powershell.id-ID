---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 7BEFA810-685C-4553-BED8-4CD6BCF8A5FE
online version: ''
schema: 2.0.0
ms.openlocfilehash: 952a342c7a7f63d0dd4a521c19b76802ec7a761e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143044181"
---
# Get-AzureCertificate

## SYNOPSIS
Mendapatkan objek sertifikat dari layanan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

```
Get-AzureCertificate [-ServiceName] <String> [-ThumbprintAlgorithm <String>] [-Thumbprint <String>]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureCertificate** mendapatkan objek sertifikat dari layanan Azure.

## EXAMPLES

### Contoh 1: Mendapatkan sertifikat dari layanan
```
PS C:\> $AzureCert = Get-AzureCertificate -ServiceName "ContosoService"
```

Perintah ini mendapatkan objek sertifikat dari layanan bernama ContosoService, lalu menyimpannya dalam variabel $AzureCert.

### Contoh 2: Mendapatkan sertifikat dari layanan
```
PS C:\> $AzureCert = Get-AzureCertificate -ServiceName "ContosoService" -Thumbprint '5383CE0343CB6563281CA97C1D4D712209CFFA97'
```

Perintah ini mendapatkan objek sertifikat yang diidentifikasi oleh sidik jari tertentu dari layanan bernama ContosoService, lalu menyimpannya dalam variabel $AzureCert.

## PARAMETERS

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
Menentukan nama layanan Azure tempat cmdlet ini mendapatkan sertifikat.

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

### -Sidik jari
Menentukan sidik jari sertifikat yang didapat cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThumbprintAlgorithm
Menentukan algoritma yang digunakan untuk membuat sidik jari sertifikat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CertificateContext

## NOTES

## RELATED LINKS

[Add-AzureCertificate](./Add-AzureCertificate.md)

[AzureCertificateSetting baru](./New-AzureCertificateSetting.md)

[Hapus-AzureCertificate](./Remove-AzureCertificate.md)


