---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RedisCache.dll-Help.xml
Module Name: Az.RedisCache
online version: https://docs.microsoft.com/powershell/module/az.rediscache/get-azrediscachelink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/Get-AzRedisCacheLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/Get-AzRedisCacheLink.md
ms.openlocfilehash: 9cdb6969e6799be2e0b7507b70ffc6ef97915e5d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142935893"
---
# Get-AzRedisCacheLink

## SYNOPSIS
Dapatkan tautan replikasi geografis untuk Redis Cache.

## SYNTAX

### AllLinksForCache (Default)
```
Get-AzRedisCacheLink -Name <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AllLinksForPrimaryCache
```
Get-AzRedisCacheLink -PrimaryServerName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SingleLink
```
Get-AzRedisCacheLink -PrimaryServerName <String> -SecondaryServerName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AllLinksForSecondaryCache
```
Get-AzRedisCacheLink -SecondaryServerName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Ada empat cara berbeda untuk mendapatkan detail tautan geo-replikasi. Berikan nama parameter atau PrimaryServerName dan/atau SecondaryServerName. Nama diberikan lalu semua tautan tempat cache ada akan dikembalikan. Jika hanya PrimaryServerName yang diberikan, maka semua link di mana cache utama akan dikembalikan. Jika hanya SecondaryServerName yang diberikan, maka semua link di mana cache adalah sekunder akan dikembalikan. Jika PrimaryServerName dan SecondaryServerName keduanya diberikan, tautan tertentu dengan peran yang benar akan dikembalikan. 

## EXAMPLES

### Contoh 1: Menggunakan kumpulan parameter AllLinksForCache
```powershell
Get-AzRedisCacheLink -Name "mycache1"
```

```output
        PrimaryServerName   : mycache1
        SecondaryServerName : mycache2
        ProvisioningState   : Succeeded
```

Perintah ini mendapatkan semua tautan geo-replikasi untuk Redis Cache bernama mycache1.

### Contoh 2: Menggunakan kumpulan parameter AllLinksForPrimaryCache
```powershell
Get-AzRedisCacheLink -PrimaryServerName "mycache1"
```

```output
        PrimaryServerName   : mycache1
        SecondaryServerName : mycache2
        ProvisioningState   : Succeeded
```

Perintah ini mendapatkan tautan geo-replikasi di mana Redis Cache bernama mycache1 adalah yang utama.

### Contoh 3: Menggunakan kumpulan parameter AllLinksForSecondaryCache
```powershell
Get-AzRedisCacheLink -SecondaryServerName "mycache2"
```

```output
        PrimaryServerName   : mycache1
        SecondaryServerName : mycache2
        ProvisioningState   : Succeeded
```

Perintah ini mendapatkan tautan geo-replikasi di mana Redis Cache bernama mycache2 adalah sekunder.

### Contoh 4: Menggunakan kumpulan parameter SingleLink
```powershell
Get-AzRedisCacheLink -PrimaryServerName "mycache1" -SecondaryServerName "mycache2"
```

```output
        PrimaryServerName   : mycache1
        SecondaryServerName : mycache2
        ProvisioningState   : Succeeded
```

Perintah ini mendapatkan satu link geo-replikasi di mana Redis Cache bernama mycache1 adalah utama dan Redis Cache bernama mycache2 adalah sekunder.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama singgahan redis.

```yaml
Type: System.String
Parameter Sets: AllLinksForCache
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrimaryServerName
Nama cache redis utama dalam tautan.

```yaml
Type: System.String
Parameter Sets: AllLinksForPrimaryCache, SingleLink
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecondaryServerName
Nama cache redis sekunder dalam tautan.

```yaml
Type: System.String
Parameter Sets: SingleLink, AllLinksForSecondaryCache
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RedisCache.Models.PSRedisLinkedServer

## NOTES

## RELATED LINKS

[New-AzRedisCacheLink](./New-AzRedisCacheLink.md)

[Remove-AzRedisCacheLink](./Remove-AzRedisCacheLink.md)

[Get-AzRedisCache](./Get-AzRedisCache.md)

[New-AzRedisCache](./New-AzRedisCache.md)

[Hapus-AzRedisCache](./Remove-AzRedisCache.md)

[Set-AzRedisCache](./Set-AzRedisCache.md)