---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewayavailableservervariableandheader
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayAvailableServerVariableAndHeader.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayAvailableServerVariableAndHeader.md
ms.openlocfilehash: 090e2096222a4da3ba6d593094fb9ee4c4e1c44d
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145509043"
---
# Get-AzApplicationGatewayAvailableServerVariableAndHeader

## SYNOPSIS
Dapatkan variabel server yang didukung dan header permintaan dan respons yang tersedia.

## SYNTAX

```
Get-AzApplicationGatewayAvailableServerVariableAndHeader [-DefaultProfile <IAzureContextContainer>]
 [-ServerVariable] [-RequestHeader] [-ResponseHeader] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApplicationGatewayAvailableServerVariableAndHeader** mendapatkan variabel server yang didukung dan header permintaan dan respons yang tersedia. Parameter dapat digunakan untuk mendapatkan variabel atau daftar header.

## EXAMPLES

### Contoh 1
```powershell
Get-AzApplicationGatewayAvailableServerVariableAndHeader -ServerVariable
```

Perintah ini mengembalikan semua variabel server yang tersedia.

### Contoh 2
```powershell
Get-AzApplicationGatewayAvailableServerVariableAndHeader -RequestHeader
```

Perintah ini mengembalikan semua header permintaan yang tersedia.

### Contoh: 3
```powershell
Get-AzApplicationGatewayAvailableServerVariableAndHeader -ResponseHeader
```

Perintah ini mengembalikan semua header respons yang tersedia.

### Contoh 4
```powershell
Get-AzApplicationGatewayAvailableServerVariableAndHeader -ServerVariable -RequestHeader -ResponseHeader
```

Perintah ini mengembalikan semua variabel server, header permintaan, dan respons yang tersedia.

### Contoh 5
```powershell
Get-AzApplicationGatewayAvailableServerVariableAndHeader
```

Perintah ini mengembalikan semua variabel server, header permintaan, dan respons yang tersedia.

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

### -RequestHeader
Application Gateway header permintaan yang tersedia.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResponseHeader
Application Gateway header respons yang tersedia.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerVariable
Application Gateway variabel server yang tersedia.

```yaml
Type: System.Management.Automation.SwitchParameter
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAvailableServerVariableAndRequestHeaderResult

## NOTES
**List-AzApplicationGatewayAvailableServerVariableAndHeader** adalah alias untuk **cmdlet Get-AzApplicationGatewayAvailableServerVariableAndHeader** .

## RELATED LINKS
