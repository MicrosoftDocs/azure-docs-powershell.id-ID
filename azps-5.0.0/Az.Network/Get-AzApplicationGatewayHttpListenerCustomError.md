---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/get-azapplicationgatewayhttplistenercustomerror
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzApplicationGatewayHttpListenerCustomError.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzApplicationGatewayHttpListenerCustomError.md
ms.openlocfilehash: 34f92bfa7566679c4cee9f7a4281ac15c55676b4
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132410550"
---
# Get-AzApplicationGatewayHttpListenerCustomError

## SYNOPSIS
Mendapatkan kesalahan kustom dari pendengar http gateway aplikasi.

## SINTAKS

```
Get-AzApplicationGatewayHttpListenerCustomError [-StatusCode <String>]
 -HttpListener <PSApplicationGatewayHttpListener> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzApplicationGatewayCustomError** mendapatkan kesalahan kustom dari http pendengar gateway aplikasi.

## CONTOH

### Contoh 1: Mendapatkan kesalahan kustom pada pendengar http
```powershell
PS C:\> $ce = Get-AzApplicationGatewayCustomError -HttpListener $listener01 -StatusCode HttpStatus502
```

Perintah ini mendapatkan dan mengembalikan kesalahan kustom kode status http 502 dari pendengar http $listener 01.

### Contoh 2: Mendapatkan daftar semua kesalahan kustom pada pendengar http
```powershell
PS C:\> $ces = Get-AzApplicationGatewayCustomError -HttpListener $listener01
```

Perintah ini akan mendapatkan dan mengembalikan daftar semua kesalahan kustom dari pendengar http $listener 01.

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

### -httpListener
Gateway Aplikasi http Pendengar

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayHttpListener
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayHttpListener

## OUTPUT

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayCustomError

## CATATAN

## LINK TERKAIT

[Add-AzApplicationGatewayhttpListenerCustomError](./Add-AzApplicationGatewayHttpListenerCustomError.md)

[Remove-AzApplicationGatewayhttpListenerCustomError](./Remove-AzApplicationGatewayHttpListenerCustomError.md)

[Set-AzApplicationGatewayhttpListenerCustomError](./Set-AzApplicationGatewayHttpListenerCustomError.md)
