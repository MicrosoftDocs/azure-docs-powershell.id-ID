---
external help file: Azs.Subscriptions.Admin-help.xml
Module Name: Azs.Subscriptions.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 02baf67cc13269d9d53c0adb40337adbd9929641
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142333691"
---
# Get-AzsPlan

## SYNOPSIS
Cantumkan semua paket di semua langganan.

## SYNTAX

### ListAll (Default)
```
Get-AzsPlan [-Skip <Int32>] [-Top <Int32>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzsPlan -Name <String> -ResourceGroupName <String> [<CommonParameters>]
```

### Daftar
```
Get-AzsPlan -ResourceGroupName <String> [-Skip <Int32>] [-Top <Int32>] [<CommonParameters>]
```

### ResourceId
```
Get-AzsPlan -ResourceId <String> [<CommonParameters>]
```

## DESCRIPTION
Cantumkan semua paket di semua langganan.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Get-AzsPlan -ResourceGroupName rg1 -Name plan1
```

Dapatkan paket spekifk di bawah langganan ini.

## PARAMETERS

### -Nama
Nama rencana.

```yaml
Type: String
Parameter Sets: Get
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya berada di bawah.

```yaml
Type: String
Parameter Sets: Get, List
Aliases: 

Required: True
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

### -Lewati
Lewati item N pertama seperti yang ditentukan oleh nilai parameter.

```yaml
Type: Int32
Parameter Sets: ListAll, List
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
Parameter Sets: ListAll, List
Aliases: 

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Subscriptions.Admin.Models.Plan

## CATATAN

## RELATED LINKS

