---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CognitiveServices.dll-Help.xml
Module Name: Az.CognitiveServices
online version: https://docs.microsoft.com/powershell/module/az.cognitiveservices/get-azcognitiveservicescommitmenttier
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CognitiveServices/CognitiveServices/help/Get-AzCognitiveServicesCommitmentTier.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CognitiveServices/CognitiveServices/help/Get-AzCognitiveServicesCommitmentTier.md
ms.openlocfilehash: aeb56f4af22b5b989df244e3f02f8e91effca5e7
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136707271"
---
# Get-AzCognitiveServicesCommitmentTier

## SYNOPSIS
Dapatkan CommitmentTier dari Layanan Kognitif

## SYNTAX

```
Get-AzCognitiveServicesCommitmentTier [-Location] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan CommitmentTier dari Layanan Kognitif

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzCognitiveServicesCommitmentTier -Location 'WestUS'
```

Dapatkan CommitmentTier dari Layanan Kognitif

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

### -Lokasi
Lokasi Akun Layanan Kognitif.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Management.CognitiveServices.Models.CommitmentTier

## CATATAN

## RELATED LINKS
