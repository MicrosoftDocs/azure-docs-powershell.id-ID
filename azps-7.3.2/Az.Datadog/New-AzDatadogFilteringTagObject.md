---
external help file: ''
Module Name: Az.Datadog
online version: https://docs.microsoft.com/powershell/module/az.Datadog/new-AzDatadogFilteringTagObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/New-AzDatadogFilteringTagObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/New-AzDatadogFilteringTagObject.md
ms.openlocfilehash: ce7abf700731a3f217ff3892a5dd5c16847c9a7d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142955423"
---
# New-AzDatadogFilteringTagObject

## SYNOPSIS
Membuat objek dalam memori untuk FilteringTag

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datadog/new-azdatadogfilteringtagobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDatadogFilteringTagObject [-Action <TagAction>] [-Name <String>] [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk FilteringTag

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk FilteringTag
```powershell
PS C:\> New-AzDatadogFilteringTagObject -Action "Include" -Value "Prod" -Name "Environment"

```

Perintah ini Membuat objek dalam memori untuk FilteringTag.

## PARAMETERS

### -Tindakan
Tindakan valid untuk tag pemfilteran.
Pengecualian lebih diprioritaskan daripada penyertaan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Datadog.Support.TagAction
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama (juga dikenal sebagai kunci) tag.

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

### -Value
Nilai tag.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.Api20210301.FilteringTag

## NOTES

ALIAS

## RELATED LINKS

