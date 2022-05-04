---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RedisCache.dll-Help.xml
Module Name: Az.RedisCache
online version: https://docs.microsoft.com/powershell/module/az.rediscache/get-azrediscachelink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/Get-AzRedisCacheLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/Get-AzRedisCacheLink.md
ms.openlocfilehash: a1258f6316674903f84dd5b268cfff59c4ed7be9
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144728816"
---
# Get-AzRedisCacheLink

## SYNOPSIS
Dapatkan tautan replikasi geografis untuk Redis Cache.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.rediscache/get-azrediscachelink) untuk informasi terbaru.

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
Ada empat cara berbeda untuk mendapatkan detail tautan replikasi geografis. Berikan nama parameter atau PrimaryServerName dan/atau SecondaryServerName. Nama diberikan maka semua tautan di mana cache ada akan dikembalikan. Jika hanya PrimaryServerName yang diberikan maka semua tautan di mana cache adalah primer akan dikembalikan. Jika hanya SecondaryServerName yang diberikan maka semua tautan di mana cache sekunder akan dikembalikan. Jika PrimaryServerName dan SecondaryServerName keduanya diberikan, tautan tertentu dengan peran yang benar akan dikembalikan. 

## EXAMPLES

### Contoh 1: Menggunakan set parameter AllLinksForCache
```powershell
Get-AzRedisCacheLink -Name "mycache1"
```

```output
        PrimaryServerName   : mycache1
        SecondaryServerName : mycache2
        ProvisioningState   : Succeeded
```

Perintah ini mendapatkan semua tautan replikasi geografis untuk Redis Cache bernama mycache1.

### Contoh 2: Menggunakan set parameter AllLinksForPrimaryCache
```powershell
Get-AzRedisCacheLink -PrimaryServerName "mycache1"
```

```output
        PrimaryServerName   : mycache1
        SecondaryServerName : mycache2
        ProvisioningState   : Succeeded
```

Perintah ini mendapatkan tautan replikasi geografis di mana Redis Cache bernama mycache1 adalah primer.

### Contoh 3: Menggunakan set parameter AllLinksForSecondaryCache
```powershell
Get-AzRedisCacheLink -SecondaryServerName "mycache2"
```

```output
        PrimaryServerName   : mycache1
        SecondaryServerName : mycache2
        ProvisioningState   : Succeeded
```

Perintah ini mendapatkan tautan replikasi geografis di mana Redis Cache bernama mycache2 adalah sekunder.

### Contoh 4: Menggunakan set parameter SingleLink
```powershell
Get-AzRedisCacheLink -PrimaryServerName "mycache1" -SecondaryServerName "mycache2"
```

```output
        PrimaryServerName   : mycache1
        SecondaryServerName : mycache2
        ProvisioningState   : Succeeded
```

Perintah ini mendapatkan satu tautan replikasi geografis di mana Redis Cache bernama mycache1 adalah primer dan Redis Cache bernama mycache2 adalah sekunder.

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

### -Name
Nama cache redis.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

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

[Remove-AzRedisCache](./Remove-AzRedisCache.md)

[Set-AzRedisCache](./Set-AzRedisCache.md)
