---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azfrontdoorcdnrulecondition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnRuleCondition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnRuleCondition.md
ms.openlocfilehash: 013c220f39c3493ea68bf0c488d7e6954cb62def
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144214154"
---
# New-AzFrontDoorCdnRuleCondition

## SYNOPSIS
Membuat kondisi aturan.

## SYNTAX

```
New-AzFrontDoorCdnRuleCondition -MatchVariable <String>
 -MatchValue <System.Collections.Generic.List`1[System.String]> [-Operator <String>] [-Selector <String>]
 [-Transform <System.Collections.Generic.List`1[System.String]>] [-NegateCondition]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat kondisi aturan.

## EXAMPLES

### Contoh 1
```powershell
New-AzFrontDoorCdnRuleCondition -MatchVariable RequestMethod -MatchValue "PUT" 
```

Membuat kondisi aturan.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchValue
Cocokkan nilai untuk dicocokkan.
Operator akan berlaku untuk setiap nilai di sini dengan semantik OR.
Jika salah satu dari mereka cocok dengan variabel dengan operator yang diberikan, kondisi kecocokan ini dianggap cocok.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchVariable
Daftar kondisi yang harus dicocokkan agar tindakan dijalankan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NegateCondition
Menjelaskan apakah hasil kondisi ini harus dinegasikan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Operator
Menjelaskan operator yang akan dicocokkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pemilih
Nama Pemilih yang akan dicocokkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transformasi
Transformasi untuk diterapkan sebelum pencocokan.
Nilai yang mungkin adalah Huruf Kecil dan Huruf Besar.

```yaml
Type: System.Collections.Generic.List`1[System.String]
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

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdRuleCondition

## NOTES

## RELATED LINKS
