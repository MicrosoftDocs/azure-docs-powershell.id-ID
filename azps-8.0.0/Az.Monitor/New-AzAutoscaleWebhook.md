---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: 674A11E4-36B9-4075-9F4E-952BD9FF07A7
online version: https://docs.microsoft.com/powershell/module/az.monitor/new-azautoscalewebhook
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzAutoscaleWebhook.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzAutoscaleWebhook.md
ms.openlocfilehash: 5a11fc5685fb9a37064cd3cd67bd894b30a66229
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145979761"
---
# New-AzAutoscaleWebhook

## SYNOPSIS
Membuat webhook Skala Otomatis.

## SYNTAX

```
New-AzAutoscaleWebhook [-ServiceUri] <String> [[-Property] <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzAutoscaleWebhook** membuat webhook Autoscale.

## EXAMPLES

### Contoh 1

Membuat webhook Skala Otomatis. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
New-AzAutoscaleWebhook -ServiceUri 'https://contoso.com'
```

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

### -Properti
Menentukan daftar properti dalam format @(property1 = 'value1',....).

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceUri
Menentukan URI layanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Management.Monitor.Management.Models.WebhookNotification

## NOTES

## RELATED LINKS

[New-AzAlertRuleWebhook](./New-AzAlertRuleWebhook.md)


