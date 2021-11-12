---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 7D7D1FAE-5360-428B-AAE9-9D1109A7B67F
online version: ''
schema: 2.0.0
ms.openlocfilehash: edb4058998ecd0ee327dced446dd5ec8d51b5cc9
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428083"
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

Perintah ini mengembalikan objek hanya dengan informasi akun ContosoStore01.

### Contoh 3: Menampilkan tabel akun penyimpanan
```
PS C:\> Get-AzureStorageAccount | Format-Table -AutoSize -Property @{Label="Name";Expression={$_.StorageAccountName}},"Label","Location"
```

Perintah ini mengembalikan objek dengan semua akun penyimpanan yang terkait dengan langganan saat ini, dan outputnya sebagai tabel yang memperlihatkan nama akun, label akun, dan lokasi penyimpanan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### ManagementOperationContext

## CATATAN
* Ketik `help node-dev` untuk mendapatkan bantuan Node.js cmdlet terkait pengembangan. Ketik `help php-dev` untuk mendapatkan bantuan tentang cmdlet yang terkait dengan pengembangan PHP.

## RELATED LINKS

[New-AzureStorageAccount](./New-AzureStorageAccount.md)

[Set-AzureStorageAccount](./Set-AzureStorageAccount.md)


