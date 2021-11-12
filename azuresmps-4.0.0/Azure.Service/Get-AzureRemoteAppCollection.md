---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: 8F00099A-042A-4450-B6CF-9EDA2350CBFC
online version: ''
schema: 2.0.0
ms.openlocfilehash: bad618e09b3f67ced143f4f0ba44b9e09b0b7216
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421583"
---
# Get-AzureRemoteAppCollection

## SYNOPSIS
Mengambil informasi tentang koleksi Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRemoteAppCollection [[-CollectionName] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRemoteAppCollection** mengambil informasi tentang kumpulan Azure RemoteApp di Microsoft Azure.
Objek akan mengembalikan objek dengan informasi tentang koleksi tertentu, atau jika tidak ada koleksi yang ditentukan, untuk semua koleksi dalam langganan saat ini.

## EXAMPLES

### Contoh 1: Mendapatkan daftar semua koleksi
```
PS C:\> Get-AzureRemoteAppCollection
```

Perintah ini mengembalikan daftar semua koleksi Azure RemoteApp dalam langganan.

### Contoh 2: Mendapatkan informasi tentang koleksi tertentu
```
PS C:\> Get-AzureRemoteAppCollection ContosoApps
```

Perintah ini mengembalikan informasi tentang koleksi Azure RemoteApp bernama ContosoApps.

### Contoh 3: Mendapatkan daftar koleksi menggunakan wildcard
```
PS C:\> Get-AzureRemoteAppCollection Finance*
```

Perintah ini mengembalikan daftar semua koleksi Azure RemoteApp yang cocok dengan Finance*.

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

[New-AzureRemoteAppCollection](./New-AzureRemoteAppCollection.md)

[Remove-AzureRemoteAppCollection](./Remove-AzureRemoteAppCollection.md)

[Set-AzureRemoteAppCollection](./Set-AzureRemoteAppCollection.md)

[Update-AzureRemoteAppCollection](./Update-AzureRemoteAppCollection.md)


