---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Reservations.dll-Help.xml
Module Name: Az.Reservations
online version: https://docs.microsoft.com/powershell/module/az.reservations/get-azreservationorderid
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Reservations/Reservations/help/Get-AzReservationOrderId.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Reservations/Reservations/help/Get-AzReservationOrderId.md
ms.openlocfilehash: 05dafecd0c76fa3901180401330695c77b12857f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142429964"
---
# Get-AzReservationOrderId

## SYNOPSIS
Dapatkan daftar Id yang berlaku `ReservationOrder` .

## SYNTAX

```
Get-AzReservationOrderId [-SubscriptionId <Guid>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan Id dari s yang dapat `ReservationOrder`diterapkan ke langganan ini.

## EXAMPLES

### Contoh 1
```powershell
Get-AzReservationOrderId
```

Dapatkan aplikasi `ReservationOrder` untuk langganan default

### Contoh 2
```powershell
Get-AzReservationOrderId -SubscriptionId "1111aaaa-b1b2-c0c2-d0d2-00000fffff"
```

Dapatkan aplikasi `ReservationOrder` untuk langganan tertentu

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

### -SubscriptionId
Id langganan untuk mendapatkan s yang diterapkan `ReservationOrder`

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Management.Reservations.Models.AppliedReservations

## CATATAN

## RELATED LINKS
