---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PolicyInsights.dll-Help.xml
Module Name: Az.PolicyInsights
online version: https://docs.microsoft.com/en-us/powershell/module/az.policyinsights/get-azpolicymetadata
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyMetadata.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/PolicyInsights/PolicyInsights/help/Get-AzPolicyMetadata.md
ms.openlocfilehash: cfd32e7ee70ffb387bd1d2a52fdbf5eb60f2e148
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132406587"
---
# Get-AzPolicyMetadata

## SYNOPSIS
Mendapatkan sumber daya Metadata Kebijakan

## SINTAKS

```
Get-AzPolicyMetadata [-Name <String>] [-Top <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzPolicyRemediation** mendapatkan semua sumber daya metadata kebijakan atau sumber daya metadata kebijakan tertentu.

## CONTOH

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

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.PolicyInsights.Models.PSPolicyMetadata

## CATATAN

## LINK TERKAIT
