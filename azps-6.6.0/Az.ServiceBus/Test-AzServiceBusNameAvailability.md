---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.dll-Help.xml
Module Name: Az.ServiceBus
online version: https://docs.microsoft.com/powershell/module/az.servicebus/test-azservicebusnameavailability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/Test-AzServiceBusNameAvailability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/Test-AzServiceBusNameAvailability.md
ms.openlocfilehash: de3c236f265e03e3e61e8fff86542d2517787744
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142299751"
---
# Test-AzServiceBusNameAvailability

## SYNOPSIS
Memeriksa Ketersediaan Nama Antrean atau Topik tertentu

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.servicebus/test-azservicebusnameavailability) untuk informasi terbaru.

## SYNTAX

### AntreanCheckNameAvailabilitySet (Default)
```
Test-AzServiceBusNameAvailability [-ResourceGroupName] <String> [-Namespace] <String> [-Name] <String> [-Queue]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### TopikCheckNameAvailabilitySet
```
Test-AzServiceBusNameAvailability [-ResourceGroupName] <String> [-Namespace] <String> [-Name] <String> [-Topic]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Test-AzServiceBusNameAvailability** Memeriksa Ketersediaan Nama Antrean atau Topik yang disediakan

## EXAMPLES

### Contoh 1
```powershell
Test-AzServiceBusNameAvailability -ResourceGroupName $resourceGroupName -Namespace $namespaceName -Name $nameQueue -Queue
True
```

Mengembalikan True jika nama $nameQueue yang Disediakan adalah Availabile atau mengembalikan False jika Nama $nameQueue disediakan tidak tersedia

### Contoh 2
```powershell
Test-AzServiceBusNameAvailability -ResourceGroupName $resourceGroupName -Namespace $namespaceName -Name $nameTopic -Topic
True
```

Mengembalikan True jika nama $nameTopic yang Disediakan adalah Availabile atau mengembalikan False jika Nama $nameTopic disediakan tidak tersedia

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

### -Nama
Nama Antrean untuk memeriksa Ketersediaan Nama

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Nama Ruang Nama Servicebus

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

### -Antrean
Untuk Memeriksa Ketersediaan Nama untuk Nama Antrean

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QueueCheckNameAvailabilitySet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceGroup

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Topik
Untuk Memeriksa Ketersediaan Nama untuk Nama Topik

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TopicCheckNameAvailabilitySet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
