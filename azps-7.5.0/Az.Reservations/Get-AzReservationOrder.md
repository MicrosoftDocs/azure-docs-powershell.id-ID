---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Reservations.dll-Help.xml
Module Name: Az.Reservations
online version: https://docs.microsoft.com/powershell/module/az.reservations/get-azreservationorder
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Reservations/Reservations/help/Get-AzReservationOrder.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Reservations/Reservations/help/Get-AzReservationOrder.md
ms.openlocfilehash: d9d23312157a28ecfdcd272cb62f8bc1f15128dd
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144230646"
---
# Get-AzReservationOrder

## SYNOPSIS
Dapatkan`ReservationOrder`

## SYNTAX

```
Get-AzReservationOrder [-ReservationOrderId <Guid>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Daftar semua `ReservationOrder`yang dapat diakses pengguna di penyewa saat ini. Jika parameter ReservationOrderId diatur, dapatkan ReservationOrder tertentu.

## EXAMPLES

### Contoh 1
```powershell
Get-AzReservationOrder
```

Mencantumkan semua `ReservationOrder` yang dapat diakses pengguna di penyewa saat ini

### Contoh 2
```powershell
Get-AzReservationOrder -ReservationOrderId "00000000-ffff-ffff-0000-00000fffff"
```

Dapatkan `ReservationOrder` dengan ReservationOrderId yang ditentukan

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

### -ReservationOrderId
Id ReservationOrder tertentu yang ingin dilihat pengguna

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Reservations.Models.PSReservationOrderPage

### Microsoft.Azure.Commands.Reservations.Models.PSReservationOrder

## NOTES

## RELATED LINKS
