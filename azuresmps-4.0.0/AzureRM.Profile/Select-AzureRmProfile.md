---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: 253305eb6a19df78f3b6b9cd0e02ed22f0d9dfcf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141771528"
---
# Select-AzureRmProfile

## SYNOPSIS
Memuat informasi autentikasi Azure dari file.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### InMemoryProfile
```
Select-AzureRmProfile [-Profile] <AzureRMProfile> [<CommonParameters>]
```

### ProfilFromDisk
```
Select-AzureRmProfile [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Select-AzureRmProfile memuat informasi autentikasi dari file untuk mengatur lingkungan dan konteks Azure.
Cmdlet yang Anda jalankan dalam sesi saat ini menggunakan informasi ini untuk mengautentikasi permintaan ke Azure Resource Manager.

## EXAMPLES

### Contoh 1: Memilih profil dari PSAzureProfile
```
PS C:\> Select-AzureRmProfile -Profile (Add-AzureRmAccount)

Environment           : AzureCloud
Account               : test@outlook.com
TenantId              : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SubscriptionId        : yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy
SubscriptionName      : Test Subscription
CurrentStorageAccount :
```

Contoh ini memilih profil dari PSAzureProfile yang diteruskan ke cmdlet.

### Contoh 2: Memilih profil dari file JSON
```
PS C:\> Select-AzureRmProfile -Path C:\test.json

Environment           : AzureCloud
Account               : test@outlook.com
TenantId              : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SubscriptionId        : yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy
SubscriptionName      : Test Subscription
CurrentStorageAccount :
```

Contoh ini memilih profil dari file JSON yang diteruskan ke cmdlet. File JSON ini dapat dibuat dari Save-AzureRmProfile.

## PARAMETERS

### -Jalur
Menentukan jalur ke informasi profil yang disimpan menggunakan Save-AzureRMProfile.

```yaml
Type: String
Parameter Sets: ProfileFromDisk
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureRMProfile
Parameter Sets: InMemoryProfile
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSAzureProfile

## CATATAN

## RELATED LINKS

[Get-AzureRMContext]()

