---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RedisCache.dll-Help.xml
Module Name: Az.RedisCache
ms.assetid: DA180A4A-88B6-4359-94E0-CF72F66D1FE4
online version: https://docs.microsoft.com/en-us/powershell/module/az.rediscache/get-azrediscachepatchschedule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/RedisCache/RedisCache/help/Get-AzRedisCachePatchSchedule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/RedisCache/RedisCache/help/Get-AzRedisCachePatchSchedule.md
ms.openlocfilehash: 0e63f8e5f427a251db13c76f915dc615f259defc
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132408107"
---
# Get-AzRedisCachePatchSchedule

## SYNOPSIS
Mendapatkan jadwal patch.

## SINTAKS

```
Get-AzRedisCachePatchSchedule [-ResourceGroupName <String>] -Name <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzRedisCachePatchSchedule** mendapatkan jadwal patch untuk singgahan di Cache Azure Redis.

## CONTOH

### Contoh 1: Dapatkan jadwal patch
```
PS C:\>Get-AzRedisCachePatchSchedule -ResourceGroupName "ResourceGroup13" -Name "RedisCache06"
```

Perintah ini mendapatkan jadwal patch dari singgahan bernama RedisCache06.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Menentukan nama singgahan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi cache.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.RedisCache.Models.PSScheduleEntry

## CATATAN
* Kata kunci: azure, azurerm, arm, resource, management, manager, redis, cache, web, webapp, website

## LINK TERKAIT

[New-AzRedisCachePatchSchedule](./New-AzRedisCachePatchSchedule.md)

[New-AzRedisCacheScheduleEntry](./New-AzRedisCacheScheduleEntry.md)

[Remove-AzRedisCachePatchSchedule](./Remove-AzRedisCachePatchSchedule.md)


