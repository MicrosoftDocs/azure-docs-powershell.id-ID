---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RedisCache.dll-Help.xml
Module Name: Az.RedisCache
ms.assetid: ACB53C23-99E0-4A0A-A44E-0D3FDB12450B
online version: https://docs.microsoft.com/powershell/module/az.rediscache/new-azrediscachescheduleentry
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/New-AzRedisCacheScheduleEntry.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/New-AzRedisCacheScheduleEntry.md
ms.openlocfilehash: def389f83a92d2cda42977397caa9327ced0b73b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140132289"
---
# New-AzRedisCacheScheduleEntry

## SYNOPSIS
Membuat entri jadwal.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.rediscache/new-azrediscachescheduleentry) untuk informasi terkini.

## SYNTAX

```
New-AzRedisCacheScheduleEntry -DayOfWeek <String> -StartHourUtc <Int32> [-MaintenanceWindow <TimeSpan>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRedisCacheScheduleEntry** membuat objek **PSScheduleEntry** .
Cmdlet jadwal patch Cache Azure Redis, seperti cmdlet New-AzRedisCachePatchSchedule, memerlukan objek entri jadwal.

## EXAMPLES

### Contoh 1: Buat entri jadwal untuk akhir pekan
```
PS C:\>New-AzRedisCacheScheduleEntry -DayOfWeek "Weekend" -StartHourUtc 2 -MaintenanceWindow "06:00:00"
```

Perintah ini membuat objek **PSScheduleEntry** yang mewakili jadwal akhir pekan yang memiliki waktu mulai dan jendela yang ditentukan.

## PARAMETERS

### -DayOfWeek
Menentukan hari dalam seminggu untuk entri jadwal.
Nilai yang dapat diterima untuk parameter ini adalah:
- Sehari-hari 
- Weekend 
- Senin 
- Selasa 
- Rabu 
- Kamis 
- Jumat 
- Sabtu 
- Minggu

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

### -MaintenanceWindow
Menentukan jumlah jendela waktu yang diperbolehkan untuk pembaruan.

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
Menentukan satu jam dari hari ketika jadwal dimulai.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Int32

### System.Nullable'1[[System.TimeSpan, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.RedisCache.Models.PSScheduleEntry

## CATATAN
* Kata kunci: azure, azurerm, arm, resource, management, manager, redis, cache, web, webapp, website

## RELATED LINKS

[Get-AzRedisCachePatchSchedule](./Get-AzRedisCachePatchSchedule.md)

[New-AzRedisCachePatchSchedule](./New-AzRedisCachePatchSchedule.md)

[Remove-AzRedisCachePatchSchedule](./Remove-AzRedisCachePatchSchedule.md)


