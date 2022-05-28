---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.dll-Help.xml
Module Name: Az.ServiceBus
online version: https://docs.microsoft.com/powershell/module/az.servicebus/test-azservicebusname
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/Test-AzServiceBusName.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/Test-AzServiceBusName.md
ms.openlocfilehash: a7a259cae0f5a20007034470d97333b5160cbad4
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145632050"
---
# Test-AzServiceBusName

## SYNOPSIS
Memeriksa Ketersediaan Nama NameSpace atau Alias yang diberikan (Nama Konfigurasi DR) 

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.servicebus/test-azservicebusname) untuk informasi terbaru.

## SYNTAX

### AliasCheckNameAvailabilitySet
```
Test-AzServiceBusName [-ResourceGroupName] <String> [-Namespace] <String> [-AliasName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### NamespaceCheckNameAvailabilitySet
```
Test-AzServiceBusName [-Namespace] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Test-AzServiceBusName** Memeriksa Ketersediaan Nama NameSpace atau Alias (Nama Konfigurasi DR)

## EXAMPLES

### Contoh 1
```powershell
Test-AzServiceBusName -Namespace MyNameSpaceName
```

Mengembalikan status pada ketersediaan nama namespace 'MyNameSpaceName' sebagai True

### Contoh 2
```powershell
Test-AzServiceBusName -Namespace MyNameSpaceName
```

Mengembalikan status ketersediaan nama namespace 'MyNameSpaceName' sebagai False dengan Alasan

### Contoh: 3
```powershell
Test-AzServiceBusName -ResourceGroupName MyResourceGroup -Namespace Test123 -AliasName myAliasName
```

## PARAMETERS

### -AliasName
Nama Konfigurasi DR - Nama Alias

```yaml
Type: System.String
Parameter Sets: AliasCheckNameAvailabilitySet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -Namespace
Nama Namespace Servicebus

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NamespaceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: AliasCheckNameAvailabilitySet
Aliases: ResourceGroup

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ServiceBus.Models.PSCheckNameAvailabilityResultAttributes

## NOTES

## RELATED LINKS
