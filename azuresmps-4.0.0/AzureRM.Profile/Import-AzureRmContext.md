---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: bf434b459e3bbd43f9c118c26b4ae2a29a2703c9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142242423"
---
# Import-AzureRmContext

## SYNOPSIS
Memuat informasi autentikasi Azure dari file.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### InMemoryProfile
```
Import-AzureRmContext [-AzureContext] <AzureRmProfile> [-WhatIf] [-Confirm]
```

### ProfilFromDisk
```
Import-AzureRmContext [-Path] <String> [-WhatIf] [-Confirm]
```

## DESCRIPTION
Cmdlet Import-AzureRmContext memuat informasi autentikasi dari file untuk mengatur lingkungan dan konteks Azure.
Cmdlet yang Anda jalankan dalam sesi saat ini menggunakan informasi ini untuk mengautentikasi permintaan ke Azure Resource Manager.

## EXAMPLES

### Contoh 1: Mengimpor konteks dari AzureRmProfile
```
PS C:\> Import-AzureRmContext -AzureContext (Add-AzureRmAccount)

Environment           : AzureCloud
Account               : test@outlook.com
TenantId              : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SubscriptionId        : yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy
SubscriptionName      : Test Subscription
CurrentStorageAccount :
```

Contoh ini mengimpor konteks dari PSAzureProfile yang diteruskan ke cmdlet.

### Contoh 2: Mengimpor konteks dari file JSON
```
PS C:\> Import-AzureRmContext -Path C:\test.json

Environment           : AzureCloud
Account               : test@outlook.com
TenantId              : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SubscriptionId        : yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy
SubscriptionName      : Test Subscription
CurrentStorageAccount :
```

Contoh ini memilih konteks dari file JSON yang diteruskan ke cmdlet.
File JSON ini dapat dibuat dari Import-AzureRmContext.

## PARAMETERS

### -AzureContext
Menentukan konteks Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan konteks, cmdlet ini akan dibaca dari konteks default lokal.

```yaml
Type: AzureRmProfile
Parameter Sets: InMemoryProfile
Aliases: Profile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Jalur
Menentukan jalur ke informasi konteks yang disimpan menggunakan Save-AzureRMContext.

```yaml
Type: String
Parameter Sets: ProfileFromDisk
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Azure.Commands.Common.Authentication.Models.AzureRMProfile
System.String

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.PSAzureProfile

## CATATAN

## RELATED LINKS

