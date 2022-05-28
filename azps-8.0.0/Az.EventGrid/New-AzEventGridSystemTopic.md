---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridSystemTopic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridSystemTopic.md
ms.openlocfilehash: 34ca2e1486e4fe836bb46d2a3318ccbf309e602c
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145507363"
---
# New-AzEventGridSystemTopic

## SYNOPSIS
Membuat Topik Sistem Azure Event Grid baru.

## SYNTAX

### TopicNameParameterSet (Default)
```
New-AzEventGridSystemTopic [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SystemTopicNameParameterSet
```
New-AzEventGridSystemTopic -ResourceGroupName <String> -Name <String> -Source <String> -TopicType <String>
 [-Location <String>] [-IdentityType <String>] [-IdentityId <String[]>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat Topik Azure Event System Grid baru. Setelah topik sistem dibuat, aplikasi layanan azure dapat menerbitkan peristiwa ke topik sistem.

## EXAMPLES

### Contoh 1
```powershell
New-AzEventGridSystemTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Source ServiceBusNamespaceResourceId -TopicType 'Microsoft.ServiceBus.Namespaces' -Location westus2
```

Membuat topik \`Sistem Event Grid Topic1\`  untuk namespace Azure ServiceBus dengan id \`sumber daya ServiceBusNamespaceResourceId\`  di lokasi \`geografis yang ditentukan westus2\`, dalam grup \`sumber daya MyResourceGroupName\`.

### Contoh 2
```powershell
New-AzEventGridTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Source ServiceBusNamespaceResourceId -TopicType 'Microsoft.ServiceBus.Namespaces' -Location westus2 -Tag @{ Department="Finance"; Environment="Test" }
```

Membuat topik \`Sistem Event Grid Topic1\` untuk namespace Azure ServiceBus dengan id \`sumber daya ServiceBusNamespaceResourceId\` di lokasi \`geografis yang ditentukan westus2\`, dalam grup \`sumber daya MyResourceGroupName\` dengan tag "Departemen" dan "Lingkungan" yang ditentukan.

### Contoh: 3
```powershell
$id1 = '/subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName'
$id2 = '/subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName'

New-AzEventGridSystemTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Source ServiceBusNamespaceResourceId -TopicType 'Microsoft.ServiceBus.Namespaces' -Location westus2 -IdentityType "UserAssigned" -IdentityId $id1,$id2
```

Membuat topik \`Sistem Event Grid Topic1\`  untuk namespace Azure ServiceBus dengan id \`sumber daya ServiceBusNamespaceResourceId\`  di lokasi \`geografis yang ditentukan westus2\`, dalam grup \`sumber daya MyResourceGroupName\` dengan \`jenis identitas UserAssigned\` dengan id identitas tertentu.

### Contoh 4
```powershell
New-AzEventGridSystemTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Source ServiceBusNamespaceResourceId -TopicType 'Microsoft.ServiceBus.Namespaces' -Location westus2 -IdentityType "SystemAssigned"
```

Membuat topik \`Sistem Event Grid Topic1\`  untuk namespace Azure ServiceBus dengan id \`sumber daya ServiceBusNamespaceResourceId\`  di lokasi \`geografis yang ditentukan westus2\`, dalam grup \`sumber daya MyResourceGroupName\` dengan \`jenis identitas SystemAssigned\` .

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

### -IdentityId
Daftar identitas yang ditetapkan pengguna

```yaml
Type: System.String[]
Parameter Sets: SystemTopicNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityType
Jenis identitas yang berbeda.
Dapat berupa salah satu dari 'SystemAssigned' berikut, 'UserAssigned', 'SystemAssigned, UserAssigned', 'None'

```yaml
Type: System.String
Parameter Sets: SystemTopicNameParameterSet
Aliases:
Accepted values: SystemAssigned, UserAssigned, SystemAssigned, UserAssigned, None

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Lokasi topik.

```yaml
Type: System.String
Parameter Sets: SystemTopicNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Nama topik EventGrid.

```yaml
Type: System.String
Parameter Sets: SystemTopicNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: SystemTopicNameParameterSet
Aliases: ResourceGroup

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sumber
Sumber untuk topik sistem

```yaml
Type: System.String
Parameter Sets: SystemTopicNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Hashtable yang mewakili Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: SystemTopicNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TopicType
Nama jenis topik EventGrid.

```yaml
Type: System.String
Parameter Sets: SystemTopicNameParameterSet
Aliases:

Required: True
Position: Named
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.String[]

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSSystemTopic

## NOTES

## RELATED LINKS
