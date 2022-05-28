---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Update-AzEventGridSystemTopic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Update-AzEventGridSystemTopic.md
ms.openlocfilehash: 48c35b0b5d8b43522a32fec3407e4e4fc3b68e91
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145522414"
---
# Update-AzEventGridSystemTopic

## SYNOPSIS
Memperbarui properti topik Sistem Event Grid.

## SYNTAX

### TopicNameParameterSet (Default)
```
Update-AzEventGridSystemTopic [-IdentityId <String[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SystemTopicNameParameterSet
```
Update-AzEventGridSystemTopic -ResourceGroupName <String> -Name <String> [-IdentityType <String>]
 [-IdentityId <String[]>] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Memperbarui properti topik Sistem Event Grid. Dapat digunakan untuk memperbarui identitas dan tag topik sistem

## EXAMPLES

### Contoh 1
```powershell
Update-AzEventGridSystemTopic -ResourceGroup MyResourceGroupName -Name Topic1 -Tag @{ Department="Finance"; Environment="Test" }
```

Mengatur properti topik \`Sistem Event Grid Topic1\` dalam grup \`sumber daya MyResourceGroupName\` untuk mengganti tag dengan tag "Departemen" dan "Lingkungan" yang ditentukan.

### Contoh 2
```powershell
Update-AzEventGridSystemTopic -ResourceGroup MyResourceGroupName -Name Topic1 -IdentityType "SystemAssigned"
```

Mengatur properti topik \`Sistem Event Grid Topik1\` dalam grup \`sumber daya MyResourceGroupName\` untuk mengubah jenis identitas ke \`SystemAssigned\`.

### Contoh: 3
```powershell
$id1 = '/subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName'
$id2 = '/subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName'

Update-AzEventGridSystemTopic -ResourceGroup MyResourceGroupName -Name Topic1 -IdentityType "UserAssigned" -IdentityId $id1,$id2
```

Mengatur properti topik \`Sistem Event Grid Topic1\` dalam grup \`sumber daya MyResourceGroupName\` untuk mengubah jenis identitas menjadi \`UserAssigned\` dengan id identitas yang diberikan.

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
Daftar Id Identitas yang ditetapkan pengguna

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityType
Hashtable yang mewakili Tag sumber daya.

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

### -Name
Nama topik EventGrid.

```yaml
Type: System.String
Parameter Sets: SystemTopicNameParameterSet
Aliases: SystemTopicName

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
