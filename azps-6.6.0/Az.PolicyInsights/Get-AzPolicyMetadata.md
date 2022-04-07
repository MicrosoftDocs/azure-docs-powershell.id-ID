---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/powershell/module/az.policyinsights/get-azpolicymetadata
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyMetadata.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyMetadata.md
ms.openlocfilehash: e290fc7ef8d2e50a233052ec09022f30f9dd49e5
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140133153"
---
# Get-AzPolicyMetadata

## SYNOPSIS
Mendapatkan sumber daya Metadata Kebijakan

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.policyinsights/get-azpolicymetadata) untuk informasi terkini.

## SYNTAX

```
Get-AzPolicyMetadata [-Name <String>] [-Top <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzPolicyRemediation** mendapatkan semua sumber daya metadata kebijakan atau sumber daya metadata kebijakan tertentu.

## EXAMPLES

### Contoh 1: Dapatkan semua sumber daya metadata kebijakan
```powershell
PS C:\> Get-AzPolicyMetadata
```

Perintah ini mendapatkan semua sumber daya metadata kebijakan

### Contoh 2: Dapatkan kumpulan 10 sumber daya metadata kebijakan
```powershell
PS C:\> Get-AzPolicyMetadata -Top 10
```

Perintah ini mendapatkan kumpulan 10 sumber daya metadata kebijakan

### Contoh 3: Dapatkan sumber daya metadata kebijakan tunggal dengan nama 'ACF1348'
```powershell
PS C:\> Get-AzPolicyMetadata -Name ACF1348
```

Perintah ini mendapatkan sumber daya metadata kebijakan tunggal dengan nama 'ACF1348'

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

### -Nama
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

### -Top
Jumlah maksimum sumber daya metadata kebijakan untuk dikembalikan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.PolicyInsights.Models.PSPolicyMetadata

## CATATAN

## RELATED LINKS
