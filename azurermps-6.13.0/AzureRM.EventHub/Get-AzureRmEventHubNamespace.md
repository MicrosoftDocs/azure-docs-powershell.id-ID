---
external help file: Microsoft.Azure.Commands.EventHub.dll-Help.xml
Module Name: AzureRM.EventHub
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.eventhub/get-azurermeventhubnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/EventHub/Commands.EventHub/help/Get-AzureRmEventHubNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/EventHub/Commands.EventHub/help/Get-AzureRmEventHubNamespace.md
ms.openlocfilehash: 35f9342fa66b46cfd029d6440d8d82134a6822a8
ms.sourcegitcommit: ea4f0db405efec935ac72601b51807dbb45674c9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/28/2022
ms.locfileid: "140864648"
---
# Get-AzureRmEventHubNamespace

## SYNOPSIS
Mendapatkan detail ruang nama Hub Acara, atau mendapatkan daftar semua ruang hub acara di langganan Azure saat ini.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmEventHubNamespace [[-ResourceGroupName] <String>] [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzureRmEventHubNamespace mendapatkan detail dari ruang nama Hub Kejadian yang ditentukan, atau daftar semua ruang nama Hub Acara di langganan Azure saat ini.
Jika nama ruang nama disediakan, rincian dari sebuah ruang nama Hub Acara dikembalikan.
Jika nama ruang nama tidak disediakan, daftar nama ruang nama dikembalikan.

## EXAMPLES

### Contoh 1
```
PS C:\> Get-AzureRmEventHubNamespace -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName
```

Mendapatkan detail ruang nama \`MyNamespaceName di\` grup sumber daya \`MyResourceGroupName\`.

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
Nama Kumpulan Nama EventHub

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NamespaceName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes

## CATATAN

## RELATED LINKS
