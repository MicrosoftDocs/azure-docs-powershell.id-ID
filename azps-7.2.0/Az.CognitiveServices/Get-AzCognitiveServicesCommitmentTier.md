---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CognitiveServices.dll-Help.xml
Module Name: Az.CognitiveServices
online version: https://docs.microsoft.com/powershell/module/az.cognitiveservices/get-azcognitiveservicescommitmenttier
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CognitiveServices/CognitiveServices/help/Get-AzCognitiveServicesCommitmentTier.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CognitiveServices/CognitiveServices/help/Get-AzCognitiveServicesCommitmentTier.md
ms.openlocfilehash: 93fd73714bc0cbd264ee88c42d61ef772f9516fc
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140273351"
---
# Get-AzCognitiveServicesCommitmentTier

## SYNOPSIS
Dapatkan CommitmentTier dari Layanan Kognitif

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.cognitiveservices/get-azcognitiveservicescommitmenttier) untuk informasi terkini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Management.CognitiveServices.Models.CommitmentTier

## CATATAN

## RELATED LINKS
