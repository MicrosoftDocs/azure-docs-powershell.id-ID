---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermapplicationgatewaysslpredefinedpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmApplicationGatewaySslPredefinedPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmApplicationGatewaySslPredefinedPolicy.md
ms.openlocfilehash: 82713c41d6f2e3882c50ffbd5ab6b276a90dc2e1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142062973"
---
# Get-AzureRmApplicationGatewaySslPredefinedPolicy

## SYNOPSIS
Mendapatkan Kebijakan SSL yang Sudah Ditentukan sebelumnya yang disediakan oleh Application Gateway.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmApplicationGatewaySslPredefinedPolicy [-Name <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmApplicationGatewaySslPredefinedPolicy** mendapatkan Kebijakan SSL yang Sudah Ditentukan sebelumnya yang disediakan oleh Application Gateway.

## EXAMPLES

### Contoh 1
```
PS C:\>$policies = Get-AzureRmApplicationGatewaySslPredefinedPolicy
```

Perintah ini mengembalikan semua kebijakan SSL yang sudah ditentukan sebelumnya.

### Contoh 2
```
PS C:\>$policy = Get-AzureRmApplicationGatewaySslPredefinedPolicy -Name AppGwSslPolicy20170401
```

Perintah ini mengembalikan kebijakan yang sudah ditentukan sebelumnya dengan nama AppGwSslPolicy20170401.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Nama kebijakan ssl yang sudah ditentukan sebelumnya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslPredefinedPolicy

## CATATAN

## RELATED LINKS
