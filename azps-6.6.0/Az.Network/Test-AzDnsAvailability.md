---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 556A9F12-DF72-468F-9C3F-A747CC70BD2F
online version: https://docs.microsoft.com/powershell/module/az.network/test-azdnsavailability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Test-AzDnsAvailability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Test-AzDnsAvailability.md
ms.openlocfilehash: bdcb1e6ea43bdc3b3419a5b866f202bb94723fce
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140248885"
---
# Test-AzDnsAvailability

## SYNOPSIS
Memeriksa apakah nama domain dalam zona cloudapp.azure.com tersedia untuk digunakan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.network/test-azdnsavailability) untuk informasi terkini.

## SYNTAX

```
Test-AzDnsAvailability -DomainNameLabel <String> -Location <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Memeriksa apakah nama domain dalam zona cloudapp.azure.com tersedia untuk digunakan.

## EXAMPLES

### Contoh 1: Periksa apakah contoso.westus.cloudapp.azure.com tersedia untuk digunakan.
```
Test-AzDnsAvailability -DomainNameLabel contoso -Location westus
```

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

### -DomainNameLabel
```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DomainQualifiedName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
