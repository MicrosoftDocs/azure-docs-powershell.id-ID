---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RedisCache.dll-Help.xml
Module Name: Az.RedisCache
ms.assetid: ACB53C23-99E0-4A0A-A44E-0D3FDB12450B
online version: https://docs.microsoft.com/powershell/module/az.rediscache/new-azrediscachescheduleentry
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/New-AzRedisCacheScheduleEntry.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/New-AzRedisCacheScheduleEntry.md
ms.openlocfilehash: c0e035799d9274eb641616ec04f3ae82d5e10433
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142935749"
---
# New-AzRedisCacheScheduleEntry

## SYNOPSIS
Membuat entri jadwal.

## SYNTAX

```
New-AzRedisCacheScheduleEntry -DayOfWeek <String> -StartHourUtc <Int32> [-MaintenanceWindow <TimeSpan>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRedisCacheScheduleEntry** membuat objek **PSScheduleEntry** .
Cmdlet jadwal singgahan Azure Redis Cache, seperti cmdlet New-AzRedisCachePatchSchedule, memerlukan objek entri jadwal.

## EXAMPLES

### Contoh 1: Membuat entri jadwal untuk akhir pekan
```powershell
New-AzRedisCacheScheduleEntry -DayOfWeek "Weekend" -StartHourUtc 2 -MaintenanceWindow "06:00:00"
```

Perintah ini membuat objek **PSScheduleEntry** yang menunjukkan jadwal akhir pekan yang memiliki waktu mulai dan jendela yang ditentukan.

## PARAMETERS

### -DayOfWeek
Menentukan hari dalam seminggu untuk entri jadwal.
Nilai yang dapat diterima untuk parameter ini adalah:
- Everyday 
- Akhir pekan 
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
Menentukan jumlah waktu jendela yang diperbolehkan untuk pembaruan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Int32

### System.Nullable'1[[System.TimeSpan, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.RedisCache.Models.PSScheduleEntry

## NOTES
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, redis, cache, web, webapp, situs web

## RELATED LINKS

[Get-AzRedisCachePatchSchedule](./Get-AzRedisCachePatchSchedule.md)

[New-AzRedisCachePatchSchedule](./New-AzRedisCachePatchSchedule.md)

[Remove-AzRedisCachePatchSchedule](./Remove-AzRedisCachePatchSchedule.md)


