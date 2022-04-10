---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermserviceendpointpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmServiceEndpointPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmServiceEndpointPolicy.md
ms.openlocfilehash: d307c223a692108aee04a9945661c090ac65942c290106128dd58b1f02915093
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140858477"
---
# Get-AzureRmServiceEndpointPolicy

## SYNOPSIS
{{Fill in the Synopsis}}

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmServiceEndpointPolicy -Name <String> -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmServiceEndpointPolicy** mendapatkan kebijakan titik akhir layanan.

## EXAMPLES

### Contoh 1
```
$policy = Get-AzureRmServiceEndpointPolicy -Name "ServiceEndpointPolicy1" -ResourceGroupName "ResourceGroup01"
```

Perintah ini mendapatkan kebijakan titik akhir layanan bernama ServiceEndpointPolicy1 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01 dan menyimpannya dalam $policy sumber daya tersebut.

### Contoh 2
```
$policyList = Get-AzureRmServiceEndpointPolicy -ResourceGroupName "ResourceGroup01"
```

Perintah ini mendapatkan daftar semua kebijakan titik akhir layanan dalam grup sumber daya yang bernama ResourceGroup01 dan menyimpannya di $policyList sumber daya.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kebijakan titik akhir layanan

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable.
Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String


## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSServiceEndpointPolicy


## CATATAN

## RELATED LINKS
