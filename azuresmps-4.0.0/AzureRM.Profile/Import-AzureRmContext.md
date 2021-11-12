---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: 41cca60b8f2f22a54b990cab20a12ddb6dfa2afb55e8e0b6b39c6f9fb120e7b3
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417637"
---
# Import-AzureRmContext

## SYNOPSIS
Memuat informasi autentikasi Azure dari file.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### InFileProfile
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

Contoh ini mengimpor konteks dari PSAzureProfile yang disampaikan ke cmdlet.

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

Contoh ini memilih konteks dari file JSON yang disampaikan melalui cmdlet.
File JSON ini dapat dibuat dari Import-AzureRmContext.

## PARAMETERS

### -AzureContext
Menentukan konteks Azure yang dibaca cmdlet ini.
Jika Anda tidak menentukan konteksnya, cmdlet ini akan membaca dari konteks default lokal.

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

### -Path
Menentukan jalur untuk informasi konteks yang disimpan menggunakan Simpan-AzureRMContext.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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

