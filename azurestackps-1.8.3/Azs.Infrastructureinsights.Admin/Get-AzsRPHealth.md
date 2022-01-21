---
external help file: Azs.InfrastructureInsights.Admin-help.xml
Module Name: Azs.Infrastructureinsights.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 752bd7f183bf5a5bdad7950e6567024cbe5b8dec
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136580538"
---
# Get-AzsRPHealth

## SYNOPSIS
Mengembalikan daftar dari setiap kesehatan layanan.

## SYNTAX

### Daftar (Default)
```
Get-AzsRPHealth [-Location <String>] [-ResourceGroupName <String>] [-Filter <String>] [-Skip <Int32>]
 [-Top <Int32>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzsRPHealth [-Name] <String> [-Location <String>] [-ResourceGroupName <String>] [<CommonParameters>]
```

### ResourceId
```
Get-AzsRPHealth -ResourceId <String> [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan daftar dari setiap kesehatan layanan. Properti AlertSummary mencakup detail tentang jumlah peringatan/kesalahan.

## EXAMPLES

### CONTOH 1
```
Get-AzsRPHealth
```

Mengembalikan daftar dari setiap kesehatan layanan.

### CONTOH 2
```
Get-AzsRPHealth -Name "e56bc7b8-c8b5-4e25-b00c-4f951effb22c"
```

Mengembalikan kesehatan layanan.

## PARAMETERS

### -Nama
Nama Kesehatan Layanan.

```yaml
Type: String
Parameter Sets: Get
Aliases: ServiceHealth

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Nama kawasan

```yaml
Type: String
Parameter Sets: List, Get
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya, opsional.

```yaml
Type: String
Parameter Sets: List, Get
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya.

```yaml
Type: String
Parameter Sets: ResourceId
Aliases: id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Filter
Parameter filter OData.

```yaml
Type: String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lewati
Lewati item N pertama seperti yang ditentukan oleh nilai parameter.

```yaml
Type: Int32
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Top
Mengembalikan item N teratas seperti yang ditentukan oleh nilai parameter.
Berlaku setelah parameter -Skip.

```yaml
Type: Int32
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.InfrastructureInsights.Admin.Models.ServiceHealth

## CATATAN

## RELATED LINKS
