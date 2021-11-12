---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: E712421A-FA69-46E7-A0DE-F2734D767F2D
online version: ''
schema: 2.0.0
ms.openlocfilehash: 41d0fbf835872c07cd70f34a9ae420436f37dc8f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426537"
---
# Get-AzureVMImage

## SYNOPSIS
Dapatkan propertinya di salah satu atau beberapa daftar sistem operasi atau gambar mesin virtual di repositori gambar.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureVMImage [[-ImageName] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVMImage** mendapatkan properti pada satu atau beberapa daftar sistem operasi atau gambar mesin virtual di penyimpanan gambar.
Cmdlet mengembalikan informasi untuk semua gambar di penyimpanan, atau tentang gambar tertentu jika nama gambar itu disediakan.

## EXAMPLES

### Contoh 1: Dapatkan objek gambar tertentu dari penyimpanan gambar saat ini.
```
PS C:\> Get-AzureVMImage -ImageName Image001
```

Perintah ini mendapatkan objek gambar yang bernama Image001 dari penyimpanan gambar saat ini.

### Contoh 2: Mendapatkan semua gambar dari penyimpanan gambar saat ini
```
PS C:\> Get-AzureVMImage
```

Perintah ini mengambil semua gambar dari penyimpanan gambar saat ini.

### Contoh 3: Atur konteks langganan, lalu dapatkan semua gambar
```
PS C:\> $SubsId = <MySubscriptionID>
C:\PS>$Cert = Get-AzureCertificate cert:\LocalMachine\MY\<CertificateThumbprint>
C:\PS>$MyOSImages = Get-AzureVMImage
```

Perintah ini mengatur konteks langganan, lalu mengambil semua gambar dari penyimpanan gambar.

## PARAMETERS

### -ImageName
Menentukan nama sistem operasi atau gambar mesin virtual di penyimpanan gambar.
Jika Anda tidak menentukan parameter ini, semua gambar akan dikembalikan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureVMImage](./Add-AzureVMImage.md)

[Remove-AzureVMImage](./Remove-AzureVMImage.md)

[Save-AzureVMImage](./Save-AzureVMImage.md)

[Update-AzureVMImage](./Update-AzureVMImage.md)


