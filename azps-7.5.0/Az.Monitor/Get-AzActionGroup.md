---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: 1CA26790-C791-4BFD-B986-70F28E3B095B
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azactiongroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzActionGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzActionGroup.md
ms.openlocfilehash: 325ad03bc18af74a23d824af2952f876a9c1e457
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144242980"
---
# Get-AzActionGroup

## SYNOPSIS
Mendapatkan grup tindakan.

## SYNTAX

### BySubscriptionOrResourceGroup (Default)
```
Get-AzActionGroup [-ResourceGroupName <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByName
```
Get-AzActionGroup -ResourceGroupName <String> -Name <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzActionGroup** mendapatkan satu atau beberapa grup tindakan.

## EXAMPLES

### Contoh 1: Mendapatkan grup tindakan menurut ID langganan
```powershell
Get-AzActionGroup
```

Perintah ini mencantumkan semua grup tindakan untuk langganan saat ini.

### Contoh 2: Mendapatkan grup tindakan untuk grup sumber daya yang diberikan
```powershell
Get-AzActionGroup -ResourceGroup "Default-activityLogAlerts"
```

Perintah ini mencantumkan grup tindakan untuk grup sumber daya yang diberikan.

### Contoh 3: Mendapatkan grup tindakan.
```powershell
Get-AzActionGroup -ResourceGroup "Default-activityLogAlerts" -Name "actionGroup1"
```

Perintah ini mencantumkan satu (daftar dengan satu elemen) grup tindakan.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Name
Nama grup tindakan.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya

```yaml
Type: System.String
Parameter Sets: BySubscriptionOrResourceGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: ByName
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

### Microsoft.Azure.Commands. Insights. OutputClasses.PSActionGroupResource

## NOTES

## RELATED LINKS

[Set-AzActionGroup](./Set-AzActionGroup.md)
 [Remove-AzActionGroup](./Remove-AzActionGroup.md)
 [New-AzActionGroupReceiver](./New-AzActionGroupReceiver.md)
