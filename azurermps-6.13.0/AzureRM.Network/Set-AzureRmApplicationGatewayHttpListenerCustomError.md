---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/set-azurermapplicationgatewayhttplistenercustomerror
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmApplicationGatewayHttpListenerCustomError.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Set-AzureRmApplicationGatewayHttpListenerCustomError.md
ms.openlocfilehash: 36828bf6b1240b6eebb4fa0dd7614c35acc0b1b3490eadb96c30965caed05e63
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140850336"
---
# Set-AzureRmApplicationGatewayHttpListenerCustomError

## SYNOPSIS
Memperbarui kesalahan kustom pada pendengar http gateway aplikasi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmApplicationGatewayHttpListenerCustomError -HttpListener <PSApplicationGatewayHttpListener>
 -StatusCode <String> -CustomErrorPageUrl <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmApplicationGatewayCustomError** memperbarui kesalahan kustom pada http pendengar gateway aplikasi.

## EXAMPLES

### Contoh 1: Memperbarui kesalahan kustom dari pendengar http
```powershell
PS C:\> $customError502Url = "https://mycustomerrorpages.blob.core.windows.net/errorpages/502.htm"
PS C:\> $updatedlistener = Set-AzureRmApplicationGatewayCustomError -HttpListener $listener01 -StatusCode HttpStatus502 -CustomErrorPageUrl $customError502Url
```

Perintah ini memperbarui kesalahan kustom kode status http 502 pada pendengar http $listener 01, dan mengembalikan pendengar yang diperbarui.

## PARAMETERS

### -CustomErrorPageUrl
URL halaman kesalahan kesalahan aplikasi gateway kesalahan pelanggan.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -httpListener
Gateway Aplikasi http Pendengar

```yaml
Type: PSApplicationGatewayHttpListener
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StatusCode
Kode status kesalahan pelanggan gateway aplikasi.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable.
Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayHttpListener

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayHttpListener

## CATATAN

## RELATED LINKS
