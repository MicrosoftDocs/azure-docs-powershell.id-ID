---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 4E3D405D-69FB-42C2-8A5B-BDBD27B63088
online version: ''
schema: 2.0.0
ms.openlocfilehash: dd6749ac0c4592f4e6f246be4db686e3f20407b3
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421120"
---
# Remove-AzureCertificate

## SYNOPSIS
Menghapus sertifikat dari layanan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

```
Remove-AzureCertificate [-ServiceName] <String> [-ThumbprintAlgorithm] <String> [-Thumbprint] <String>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureCertificate** menghapus sertifikat dari layanan Azure.

## EXAMPLES

### Contoh 1: Menghapus sertifikat dari layanan
```
PS C:\> Remove-AzureCertificate -ServiceName "ContosoService" -Thumbprint '5383CE0343CB6563281CA97C1D4D712209CFFA97'
```

Perintah ini akan menghapus objek sertifikat yang memiliki thumbprint tertentu dari layanan cloud.

### Contoh 2: Menghapus semua sertifikat dari layanan
```
PS C:\> Get-AzureCertificate -ServiceName "ContosoService" | Remove-AzureCertificate
```

Perintah ini mendapatkan semua sertifikat dari layanan bernama ContosoService dengan menggunakan cmdlet **Get-AzureCertificate.**
Perintah itu menyampaikan setiap sertifikat ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet tersebut menghapus setiap sertifikat dari layanan awan.

### Contoh 3: Menghapus semua sertifikat dari layanan yang menggunakan algoritma thumbprint tertentu
```
PS C:\> Get-AzureCertificate -ServiceName "ContosoService" -ThumbprintAlgorithm "sha1" | Remove-AzureCertificate
```

Perintah ini mendapatkan semua sertifikat dari layanan bernama ContosoService yang menggunakan algoritma sha1 thumbprint.
Perintah tersebut meneruskan setiap sertifikat ke cmdlet saat ini, yang menghapus setiap sertifikat.

## PARAMETERS

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
Menentukan nama layanan Azure yang akan dihapus cmdlet ini.

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

### -Thumbprint
Menentukan thumbprint sertifikat yang dihapus cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThumbprintAlgorithm
Menentukan algoritma yang digunakan untuk membuat sertifikat yang dicetak.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

[Add-AzureCertificate](./Add-AzureCertificate.md)

[Get-AzureCertificate](./Get-AzureCertificate.md)

[New-AzureCertificateSetting](./New-AzureCertificateSetting.md)


