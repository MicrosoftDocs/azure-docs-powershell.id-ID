---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.dll-Help.xml
Module Name: Az.ServiceBus
online version: https://docs.microsoft.com/powershell/module/az.servicebus/remove-azservicebussubscription
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/Remove-AzServiceBusSubscription.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/Remove-AzServiceBusSubscription.md
ms.openlocfilehash: 794f8046d61ca80d4be8988c5952c49c6b12ea19
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145632608"
---
# Remove-AzServiceBusSubscription

## SYNOPSIS
Menghapus langganan ke topik dari namespace Bus Layanan yang ditentukan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.servicebus/remove-azservicebussubscription) untuk informasi terbaru.

## SYNTAX

### SubscriptionPropertiesSet (Default)
```
Remove-AzServiceBusSubscription [-ResourceGroupName] <String> [-Namespace] <String> [-Topic] <String>
 [-Name] <String> [-PassThru] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SubscriptionInputObjectSet
```
Remove-AzServiceBusSubscription [-InputObject] <PSSubscriptionAttributes> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SubscriptionResourceIdSet
```
Remove-AzServiceBusSubscription [-ResourceId] <String> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzServiceBusSubscription** menghapus langganan ke topik dari namespace Bus Layanan yang ditentukan.

## EXAMPLES

### Contoh 1
```powershell
Remove-AzServiceBusSubscription -ResourceGroup Default-ServiceBus-WestUS -NamespaceName SB-Example1 -TopicName SB-Topic_exampl1 -SubscriptionName SB-TopicSubscription-Example1
```

Menghapus langganan `SB-TopicSubscription-Example1` ke topik `SB-Topic_exampl1` di namespace `SB-Example1`Bus Layanan yang ditentukan .

### Contoh 2: InputObject - Menggunakan Variabel:
```powershell
$inputobject = Get-AzServiceBusSubscription <params>
Remove-AzServiceBusSubscription -InputObject $inputobject
```

### Contoh 3: InputObject - Menggunakan Piping:
```powershell
Get-AzServiceBusSubscription <params> |Remove-AzServiceBusSubscription
```

### Contoh 4: ResourceId - Menggunakan Variabel:
```powershell
$resourceid = Get-AzServiceBusSubscription <params>
Remove-AzServiceBusSubscription -ResourceId $resourceid.Id
```

### Contoh 5: ResourceId - Menggunakan nilai string:
```powershell
Remove-AzServiceBusSubscription -ResourceId "/subscriptions/Subscriptionid/resourceGroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/NamespaceName/topics/TopicName/subscriptions/SubscriptionName"
```

Menghapus langganan yang disediakan melalui ID ARM di $resourceid/string untuk parameter -ResourceId 

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

### -InputObject
Objek Langganan Bus Layanan

```yaml
Type: Microsoft.Azure.Commands.ServiceBus.Models.PSSubscriptionAttributes
Parameter Sets: SubscriptionInputObjectSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama langganan

```yaml
Type: System.String
Parameter Sets: SubscriptionPropertiesSet
Aliases: SubscriptionName

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Nama Namespace

```yaml
Type: System.String
Parameter Sets: SubscriptionPropertiesSet
Aliases: NamespaceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Menentukan ini akan mengembalikan true jika perintah berhasil.

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

### -ResourceGroupName
Nama grup sumber daya

```yaml
Type: System.String
Parameter Sets: SubscriptionPropertiesSet
Aliases: ResourceGroup

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ID Sumber Daya Langganan Bus Layanan

```yaml
Type: System.String
Parameter Sets: SubscriptionResourceIdSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Topik
Nama Topik

```yaml
Type: System.String
Parameter Sets: SubscriptionPropertiesSet
Aliases: TopicName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.ServiceBus.Models.PSSubscriptionAttributes

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
