---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: 8F00099A-042A-4450-B6CF-9EDA2350CBFC
online version: ''
schema: 2.0.0
ms.openlocfilehash: bad618e09b3f67ced143f4f0ba44b9e09b0b7216
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142723976"
---
# Get-AzureRemoteAppCollection

## SYNOPSIS
Mengambil informasi tentang kumpulan Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRemoteAppCollection [[-CollectionName] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRemoteAppCollection** mengambil informasi tentang koleksi Azure RemoteApp di Microsoft Azure.
Objek mengembalikan objek dengan informasi tentang koleksi tertentu, atau jika tidak ada koleksi yang ditentukan, untuk semua kumpulan dalam langganan saat ini.

## EXAMPLES

### Contoh 1: Dapatkan daftar semua koleksi
```
PS C:\> Get-AzureRemoteAppCollection
```

Perintah ini mengembalikan daftar semua koleksi Azure RemoteApp dalam langganan.

### Contoh 2: Mendapatkan informasi tentang koleksi tertentu
```
PS C:\> Get-AzureRemoteAppCollection ContosoApps
```

Perintah ini mengembalikan informasi tentang kumpulan Azure RemoteApp bernama ContosoApps.

### Contoh 3: Mendapatkan daftar koleksi menggunakan wildcard
```
PS C:\> Get-AzureRemoteAppCollection Finance*
```

Perintah ini mengembalikan daftar semua kumpulan Azure RemoteApp yang cocok dengan Keuangan*.

## PARAMETERS

### -CollectionName
Menentukan nama koleksi Azure RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

[AzureRemoteAppCollection baru](./New-AzureRemoteAppCollection.md)

[Hapus-AzureRemoteAppCollection](./Remove-AzureRemoteAppCollection.md)

[Set-AzureRemoteAppCollection](./Set-AzureRemoteAppCollection.md)

[Update-AzureRemoteAppCollection](./Update-AzureRemoteAppCollection.md)


