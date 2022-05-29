---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: D5E928C3-26B6-4B7C-8A9C-F1F602BABF75
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewaybackendhealth
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayBackendHealth.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewayBackendHealth.md
ms.openlocfilehash: 29de0102b4709c158c80ebd3f1e0f78995e0802c
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145775981"
---
# Get-AzApplicationGatewayBackendHealth

## SYNOPSIS
Mendapatkan kesehatan backend gateway aplikasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azapplicationgatewaybackendhealth) untuk informasi terbaru.

## SYNTAX

```
Get-AzApplicationGatewayBackendHealth -Name <String> -ResourceGroupName <String> [-ExpandResource <String>]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzApplicationGatewayBackendHealth mendapatkan kesehatan backend gateway aplikasi.

## EXAMPLES

### Contoh 1: Mendapatkan kesehatan backend tanpa sumber daya yang diperluas.
```powershell
$BackendHealth = Get-AzApplicationGatewayBackendHealth -Name ApplicationGateway01 -ResourceGroupName ResourceGroup01
```

Perintah ini mendapatkan kesehatan backend gateway aplikasi bernama ApplicationGateway01 yang termasuk dalam grup sumber daya bernama ResourceGroup01 dan menyimpannya dalam variabel $BackendHealth.

### Contoh 2: Mendapatkan kesehatan backend dengan sumber daya yang diperluas.
```powershell
$BackendHealth = Get-AzApplicationGatewayBackendHealth -Name ApplicationGateway01 -ResourceGroupName ResourceGroup01 -ExpandResource "backendhealth/applicationgatewayresource"
```

Perintah ini mendapatkan kesehatan backend (dengan sumber daya yang diperluas) gateway aplikasi bernama ApplicationGateway01 yang termasuk dalam grup sumber daya bernama ResourceGroup01 dan menyimpannya dalam variabel $BackendHealth.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -ExpandResource
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

### -Name
Menentukan nama gateway aplikasi yang didapat cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi gateway aplikasi.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHealth

## NOTES
Kata kunci: azure, azurerm, arm, sumber daya, manajemen, manajer, jaringan, jaringan

## RELATED LINKS

[Get-AzApplicationGateway](./Get-AzApplicationGateway.md)

