---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationRuleObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationRuleObject.md
ms.openlocfilehash: 5f9758982ec4fc304515b7635a89cca86f73262e
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145521130"
---
# New-AzSecurityAutomationRuleObject

## SYNOPSIS
Membuat objek aturan otomatisasi keamanan

## SYNTAX

```
New-AzSecurityAutomationRuleObject -PropertyJPath <String> -Operator <String> -ExpectedValue <String>
 -PropertyType <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek aturan otomatisasi keamanan

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzSecurityAutomationRuleObject -PropertyJPath 'properties.metadata.severity'  -PropertyType 'String' -Operator 'Equals'  -ExpectedValue 'High'
```

Membuat objek aturan otomatisasi keamanan yang memfilter pesan dengan tingkat keparahan "Tinggi"

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

### -ExpectedValue
Nilai yang diharapkan

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

### -Operator
Operator pembanding yang valid untuk digunakan.
Perbandingan yang tidak peka huruf besar/kecil akan diterapkan untuk String PropertyType

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

### -PropertyJPath
JPath properti model entitas yang harus diperiksa

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

### -PropertyType
Jenis data dari operand yang dibandingkan (string, bilangan bulat, angka titik mengambang atau boolean \[true/false\]\]

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomationTriggeringRule

## NOTES

## RELATED LINKS
