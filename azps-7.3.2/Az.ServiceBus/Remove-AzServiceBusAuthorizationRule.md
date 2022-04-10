---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.dll-Help.xml
Module Name: Az.ServiceBus
online version: https://docs.microsoft.com/powershell/module/az.servicebus/remove-azservicebusauthorizationrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/Remove-AzServiceBusAuthorizationRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceBus/ServiceBus/help/Remove-AzServiceBusAuthorizationRule.md
ms.openlocfilehash: c8a82fd285d1fc358d3d36eb2854a317feef9d30
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140554519"
---
# Remove-AzServiceBusAuthorizationRule

## SYNOPSIS
Menghapus aturan otorisasi ruang nama Bus Layanan atau antrean atau topik dari grup sumber daya yang ditentukan.

## SYNTAX

### NamespaceAuthorizationRuleSet (Default)
```
Remove-AzServiceBusAuthorizationRule [-ResourceGroupName] <String> [-Namespace] <String> [-Name] <String>
 [[-InputObject] <PSSharedAccessAuthorizationRuleAttributes>] [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### QueueAuthorizationRuleSet
```
Remove-AzServiceBusAuthorizationRule [-ResourceGroupName] <String> [-Namespace] <String> [-Queue] <String>
 [-Name] <String> [[-InputObject] <PSSharedAccessAuthorizationRuleAttributes>] [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TopicAuthorizationRuleSet
```
Remove-AzServiceBusAuthorizationRule [-ResourceGroupName] <String> [-Namespace] <String> [-Topic] <String>
 [-Name] <String> [[-InputObject] <PSSharedAccessAuthorizationRuleAttributes>] [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzServiceBusAuthorizationRule** menghapus aturan otorisasi ruang nama Bus Layanan atau antrean atau topik untuk grup sumber daya yang ditentukan.

## EXAMPLES

### Contoh 1
```
PS C:\> Remove-AzServiceBusAuthorizationRule -ResourceGroup Default-ServiceBus-WestUS -Namespace SB-Example1 -Name AuthoRule1
```

Menghapus aturan otorisasi ruang nama `SBAuthoRule1` dari `SB-Example1` grup sumber daya yang ditentukan.

### Contoh 2
```
PS C:\> Remove-AzServiceBusAuthorizationRule -ResourceGroup Default-ServiceBus-WestUS -Namespace SB-Example1 -Queue SBQueue -Name AuthoRule1
```

Menghapus aturan otorisasi antrean `SBAuthoRule1` dari grup `SBQueue` sumber daya yang ditentukan.

### Contoh 3
```
PS C:\> Remove-AzServiceBusAuthorizationRule -ResourceGroup Default-ServiceBus-WestUS -Namespace SB-Example1 -Topic SBTopic -Name AuthoRule1
```

Menghapus aturan otorisasi topik `SBAuthoRule1` dari grup `SBTopic` sumber daya tertentu.

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

### -Force
Jangan minta konfirmasi.

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

### -InputObject
Objek ServiceBus AuthorizationRule

```yaml
Type: Microsoft.Azure.Commands.ServiceBus.Models.PSSharedAccessAuthorizationRuleAttributes
Parameter Sets: (All)
Aliases: AuthRuleObj

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama AuthorizationRule

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AuthorizationRuleName

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Nama Kumpulan Nama

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NamespaceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili item yang Anda kerjakan.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

### -Antrean
Nama Antrean

```yaml
Type: System.String
Parameter Sets: QueueAuthorizationRuleSet
Aliases: QueueName

Required: True
Position: 2
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

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Topic
Nama Topik

```yaml
Type: System.String
Parameter Sets: TopicAuthorizationRuleSet
Aliases: TopicName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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

### Microsoft.Azure.Commands.ServiceBus.Models.PSSharedAccessAuthorizationRuleAttributes

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
