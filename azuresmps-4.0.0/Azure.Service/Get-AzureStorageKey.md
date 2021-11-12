---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 35588231-CBAC-4411-9531-9A06BD298ACA
online version: ''
schema: 2.0.0
ms.openlocfilehash: 5b015e8a2c566ff3de7efa242d77f738cc5c009a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421568"
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

### Contoh 1: Mendapatkan objek yang berisi tombol penyimpanan primer dan sekunder
```
PS C:\> Get-AzureStorageKey -StorageAccountName "ContosoStore01"
```

Perintah ini akan mendapatkan objek dengan kunci penyimpanan utama dan sekunder untuk akun penyimpanan ContosoStore01.

### Contoh 2: Dapatkan kunci akun penyimpanan utama dan simpan dalam variabel
```
PS C:\> $ContosoStoreKey = (Get-AzureStorageKey -StorageAccountName "ContosoStore01").Primary
```

Perintah ini meletakkan kunci akun penyimpanan utama untuk akun penyimpanan ContosoStore01 dalam $ContosoStoreKey penyimpanan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN
* Untuk mendapatkan bantuan dengan Node.js Anda, gunakan `help node-dev` perintah tersebut. Untuk bantuan dengan ekstensi PHP, gunakan `help php-dev` perintah.

## RELATED LINKS

[Get-AzureStorageAccount](./Get-AzureStorageAccount.md)

[New-AzureStorageAccount](./New-AzureStorageAccount.md)

[New-AzureStorageKey](./New-AzureStorageKey.md)

[Remove-AzureStorageAccount](./Remove-AzureStorageAccount.md)

[Set-AzureStorageAccount](./Set-AzureStorageAccount.md)


