---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azfrontdoorcdnrulecondition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnRuleCondition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnRuleCondition.md
ms.openlocfilehash: afada0453e5b49c5b495bcb80404dfcf02021df4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141872078"
---
# New-AzFrontDoorCdnRuleCondition

## SYNOPSIS
Membuat kondisi aturan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cdn/new-azfrontdoorcdnrulecondition) untuk informasi terbaru.

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
PS C:\> New-AzFrontDoorCdnRuleCondition -MatchVariable RequestMethod -MatchValue "PUT" 
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
Mencocokkan nilai untuk dicocokkan dengan.
Operator akan berlaku untuk setiap nilai di sini dengan semantik OR.
Jika salah satunya cocok dengan variabel dengan operator tertentu, kondisi kecocokan ini dianggap cocok.

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
Menjelaskan jika hasil dari kondisi ini harus dinegasikan.

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

### -Selector
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
Transformasi untuk diterapkan sebelum mencocokkan.
Nilai yang memungkinkan adalah Huruf Kecil dan Huruf Besar.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdRuleCondition

## CATATAN

## RELATED LINKS
