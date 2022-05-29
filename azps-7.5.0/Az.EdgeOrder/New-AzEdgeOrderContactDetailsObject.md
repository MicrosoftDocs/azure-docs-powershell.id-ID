---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderContactDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderContactDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderContactDetailsObject.md
ms.openlocfilehash: 8854f59a771f3d143cf6a3467b56df9e676b86a9
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145800692"
---
# New-AzEdgeOrderContactDetailsObject

## SYNOPSIS
Buat objek dalam memori untuk ContactDetails.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.edgeorder/new-azedgeordercontactdetailsobject) untuk informasi terbaru.

## SYNTAX

```
New-AzEdgeOrderContactDetailsObject -ContactName <String> -EmailList <String[]> -Phone <String>
 [-Mobile <String>] [-PhoneExtension <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk ContactDetails.

## EXAMPLES

### Contoh 1: Objek detail kontak
```powershell
$contactDetail = New-AzEdgeOrderContactDetailsObject -ContactName ContactName -EmailList @("emailId") -Phone Phone
```

```output
ContactName    : random
EmailList      : {"emailId"}
Mobile         :
Phone          : 1234567890
PhoneExtension :
```

Membuat objek detail kontak dalam memori

## PARAMETERS

### -ContactName
Nama kontak orang tersebut.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailList
Daftar Email-id yang akan diberi tahu tentang kemajuan pekerjaan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mobile
Nomor ponsel kontak.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Telepon
Telepon nomor kontak.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhoneExtension
Telepon nomor ekstensi kontak.

```yaml
Type: System.String
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.ContactDetails

## NOTES

ALIAS

## RELATED LINKS

