---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azcapacityreservation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzCapacityReservation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzCapacityReservation.md
ms.openlocfilehash: 01e6e42e8d60ccbba4684b76335eea71e3cc8dbd
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136194371"
---
# New-AzCapacityReservation

## SYNOPSIS
Membuat sumber daya Reservasi Kapasitas dalam Grup Reservasi Kapasitas

## SYNTAX

```
New-AzCapacityReservation -ResourceGroupName <String> -ReservationGroupName <String> -Name <String>
 -Location <String> -CapacityToReserve <Int32> -Sku <String> [-AsJob] [-Tag <Hashtable>] [-Zone <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzCapacityReservation** membuat sumber daya Reservasi Kapasitas di Grup Reservasi Kapasitas

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzCapacityReservation -ResourceGroupName "myRG" -Location "eastus" -ReservationGroupName "myCapacityReservationGroup" -Name "myCapacityReservation" -Sku "Standard_DS1_v2" -CapacityToReserve 4
```

Perintah ini akan membuat sumber daya Reservasi Kapasitas dengan sku dan kapasitas yang disediakan dalam Grup Reservasi Kapasitas bernama "myCapacityReservationGroup".

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CapacityToReserve
Menentukan jumlah mesin virtual dalam kumpulan skala.

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

### -Lokasi
Menentukan lokasi.

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

### -Nama
Menentukan nama sumber daya reservasi kapasitas.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CapacityReservationName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReservationGroupName
Menentukan nama grup reservasi kapasitas.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CapacityReservationGroupName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

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

### -Sku
SKU sumber daya yang memerlukan kapasitas terlebih dahulu.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Size

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Menentukan bahwa sumber daya dan grup sumber daya dapat ditandai dengan kumpulan pasangan nama nilai. Menambahkan tag ke sumber daya memungkinkan Anda mengelompokkan sumber daya bersama-sama di seluruh grup sumber daya dan untuk membuat tampilan Anda sendiri. Setiap grup sumber daya atau sumber daya dapat memiliki maksimal 15 tag.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
Zona Ketersediaan untuk digunakan untuk pemesanan kapasitas ini.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Int32

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSCapacityReservation

## CATATAN

## RELATED LINKS
