---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 35588231-CBAC-4411-9531-9A06BD298ACA
online version: ''
schema: 2.0.0
ms.openlocfilehash: 5b015e8a2c566ff3de7efa242d77f738cc5c009a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143043641"
---
# Get-AzureStorageKey

## SYNOPSIS
Mengembalikan kunci akun penyimpanan utama dan sekunder untuk akun penyimpanan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorageKey [-StorageAccountName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageKey** mengembalikan objek dengan nama akun Azure Storage, kunci akun utama, dan kunci akun sekunder dari akun penyimpanan Azure yang ditentukan sebagai properti.

## EXAMPLES

### Contoh 1: Dapatkan objek yang berisi kunci penyimpanan primer dan sekunder
```
PS C:\> Get-AzureStorageKey -StorageAccountName "ContosoStore01"
```

Perintah ini mendapatkan objek dengan kunci penyimpanan utama dan sekunder untuk akun penyimpanan ContosoStore01.

### Contoh 2: Dapatkan kunci akun penyimpanan utama dan simpan dalam variabel
```
PS C:\> $ContosoStoreKey = (Get-AzureStorageKey -StorageAccountName "ContosoStore01").Primary
```

Perintah ini menempatkan kunci akun penyimpanan utama untuk akun penyimpanan ContosoStore01 dalam variabel $ContosoStoreKey.

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

### -StorageAccountName
Menentukan nama akun penyimpanan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ServiceName

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

## NOTES
* Untuk mendapatkan bantuan terkait Node.js, gunakan perintah.`help node-dev` Untuk bantuan dengan ekstensi PHP, gunakan perintah.`help php-dev`

## RELATED LINKS

[Get-AzureStorageAccount](./Get-AzureStorageAccount.md)

[AzureStorageAccount baru](./New-AzureStorageAccount.md)

[AzureStorageKey Baru](./New-AzureStorageKey.md)

[Hapus-AzureStorageAccount](./Remove-AzureStorageAccount.md)

[Set-AzureStorageAccount](./Set-AzureStorageAccount.md)


