---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: E712421A-FA69-46E7-A0DE-F2734D767F2D
online version: ''
schema: 2.0.0
ms.openlocfilehash: 41d0fbf835872c07cd70f34a9ae420436f37dc8f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143158584"
---
# Get-AzureVMImage

## SYNOPSIS
Mendapatkan properti pada satu atau daftar sistem operasi atau gambar mesin virtual di repository gambar.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureVMImage [[-ImageName] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVMImage** mendapatkan properti pada satu atau daftar sistem operasi atau gambar mesin virtual di repositori gambar.
Cmdlet mengembalikan informasi untuk semua gambar dalam repositori, atau tentang gambar tertentu jika nama gambar disediakan.

## EXAMPLES

### Contoh 1: Dapatkan objek gambar tertentu dari repository gambar saat ini.
```
PS C:\> Get-AzureVMImage -ImageName Image001
```

Perintah ini mendapatkan objek gambar bernama Image001 dari repository gambar saat ini.

### Contoh 2: Dapatkan semua gambar dari repository gambar saat ini
```
PS C:\> Get-AzureVMImage
```

Perintah ini mengambil semua gambar dari penyimpanan gambar saat ini.

### Contoh 3: Atur konteks langganan lalu dapatkan semua gambar
```
PS C:\> $SubsId = <MySubscriptionID>
C:\PS>$Cert = Get-AzureCertificate cert:\LocalMachine\MY\<CertificateThumbprint>
C:\PS>$MyOSImages = Get-AzureVMImage
```

Perintah ini mengatur konteks langganan lalu mengambil semua gambar dari penyimpanan gambar.

## PARAMETERS

### -ImageName
Menentukan nama sistem operasi atau gambar mesin virtual dalam penyimpanan gambar.
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureVMImage](./Add-AzureVMImage.md)

[Hapus-AzureVMImage](./Remove-AzureVMImage.md)

[Simpan-AzureVMImage](./Save-AzureVMImage.md)

[Pembaruan-AzureVMImage](./Update-AzureVMImage.md)


