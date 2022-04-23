---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 7D7D1FAE-5360-428B-AAE9-9D1109A7B67F
online version: ''
schema: 2.0.0
ms.openlocfilehash: edb4058998ecd0ee327dced446dd5ec8d51b5cc9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143158715"
---
# Get-AzureStorageAccount

## SYNOPSIS
Mendapatkan akun penyimpanan untuk langganan Azure saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorageAccount [[-StorageAccountName] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageAccount** mengembalikan objek yang berisi informasi tentang akun penyimpanan untuk langganan saat ini.
Jika parameter *StorageAccountName* ditentukan, maka hanya informasi tentang akun penyimpanan tertentu yang dikembalikan.

## EXAMPLES

### Contoh 1: Mengembalikan semua akun penyimpanan
```
PS C:\> Get-AzureStorageAccount
```

Perintah ini mengembalikan objek dengan semua akun penyimpanan yang terkait dengan langganan saat ini.

### Contoh 2: Mengembalikan informasi akun untuk akun tertentu
```
PS C:\> Get-AzureStorageAccount -StorageAccountName "ContosoStore01"
```

Perintah ini mengembalikan objek dengan informasi akun ContosoStore01 saja.

### Contoh 3: Menampilkan tabel akun penyimpanan
```
PS C:\> Get-AzureStorageAccount | Format-Table -AutoSize -Property @{Label="Name";Expression={$_.StorageAccountName}},"Label","Location"
```

Perintah ini mengembalikan objek dengan semua akun penyimpanan yang terkait dengan langganan saat ini, dan menghasilkannya sebagai tabel yang memperlihatkan nama akun, label akun, dan lokasi penyimpanan.

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
Jika ditentukan, cmdlet ini hanya mengembalikan objek akun penyimpanan yang ditentukan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ManagementOperationContext

## NOTES
* Ketikkan `help node-dev` untuk mendapatkan bantuan tentang cmdlet terkait pengembangan Node.js. Ketikkan `help php-dev` untuk mendapatkan bantuan tentang cmdlet terkait pengembangan PHP.

## RELATED LINKS

[AzureStorageAccount baru](./New-AzureStorageAccount.md)

[Set-AzureStorageAccount](./Set-AzureStorageAccount.md)


