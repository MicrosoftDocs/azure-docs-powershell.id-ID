---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RedisCache.dll-Help.xml
Module Name: Az.RedisCache
ms.assetid: ACB53C23-99E0-4A0A-A44E-0D3FDB12450B
online version: https://docs.microsoft.com/powershell/module/az.rediscache/new-azrediscachescheduleentry
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/New-AzRedisCacheScheduleEntry.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/New-AzRedisCacheScheduleEntry.md
ms.openlocfilehash: b32d23c04f6bd4e13c48641c03788956aa038c89
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144661266"
---
# New-AzRedisCacheScheduleEntry

## SYNOPSIS
Membuat entri jadwal.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.rediscache/new-azrediscachescheduleentry) untuk informasi terbaru.

## SYNTAX

```
New-AzRedisCacheScheduleEntry -DayOfWeek <String> -StartHourUtc <Int32> [-MaintenanceWindow <TimeSpan>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRedisCacheScheduleEntry** membuat objek **PSScheduleEntry** .
Cmdlet jadwal patch Azure Redis Cache, seperti cmdlet New-AzRedisCachePatchSchedule, memerlukan objek entri jadwal.

## EXAMPLES

### Contoh 1: Membuat entri jadwal untuk akhir pekan
```powershell
New-AzRedisCacheScheduleEntry -DayOfWeek "Weekend" -StartHourUtc 2 -MaintenanceWindow "06:00:00"
```

Perintah ini membuat objek **PSScheduleEntry** yang mewakili jadwal akhir pekan yang memiliki waktu mulai dan jendela yang ditentukan.

## PARAMETERS

### -DayOfWeek
Menentukan hari dalam seminggu untuk entri jadwal.
Nilai yang dapat diterima untuk parameter ini adalah:
- Setiap hari 
- Akhir pekan 
- Senin 
- Selasa 
- Rabu 
- Kamis 
- Jumat 
- Sabtu 
- Hari Minggu

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Everyday, Weekend, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -MaintenanceWindow
Menentukan jumlah jendela waktu yang diizinkan untuk pembaruan.

```yaml
Type: System.Nullable`1[System.TimeSpan]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartHourUtc
Menentukan satu jam hari ketika jadwal dimulai.

```yaml
Type: System.Int32
Parameter Sets: (All)
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

### System.Int32

### System.Nullable'1[[System.TimeSpan, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.RedisCache.Models.PSScheduleEntry

## NOTES
* Kata kunci: azure, azurerm, arm, sumber daya, manajemen, manajer, redis, cache, web, webapp, situs web

## RELATED LINKS

[Get-AzRedisCachePatchSchedule](./Get-AzRedisCachePatchSchedule.md)

[New-AzRedisCachePatchSchedule](./New-AzRedisCachePatchSchedule.md)

[Remove-AzRedisCachePatchSchedule](./Remove-AzRedisCachePatchSchedule.md)


