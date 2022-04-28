---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/powershell/module/az.policyinsights/get-azpolicymetadata
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyMetadata.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyMetadata.md
ms.openlocfilehash: 3d50adbd9b96fc1cd8a9767cfffa0e6549d442c0
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144210290"
---
# Get-AzPolicyMetadata

## SYNOPSIS
Mendapatkan sumber daya Metadata Kebijakan

## SYNTAX

```
Get-AzPolicyMetadata [-Name <String>] [-Top <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzPolicyRemediation** mendapatkan semua sumber daya metadata kebijakan atau sumber daya metadata kebijakan tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan semua sumber daya metadata kebijakan
```powershell
Get-AzPolicyMetadata
```

Perintah ini mendapatkan semua sumber daya metadata kebijakan

### Contoh 2: Mendapatkan kumpulan 10 sumber daya metadata kebijakan
```powershell
Get-AzPolicyMetadata -Top 10
```

Perintah ini mendapatkan kumpulan 10 sumber daya metadata kebijakan

### Contoh 3: Dapatkan satu sumber daya metadata kebijakan dengan nama 'ACF1348'
```powershell
Get-AzPolicyMetadata -Name ACF1348
```

Perintah ini mendapatkan satu sumber daya metadata kebijakan dengan nama 'ACF1348'

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

### -Name
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Atas
Jumlah maksimum sumber daya metadata kebijakan yang akan dikembalikan.

```yaml
Type: System.Int32
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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.PolicyInsights.Models.PSPolicyMetadata

## NOTES

## RELATED LINKS
