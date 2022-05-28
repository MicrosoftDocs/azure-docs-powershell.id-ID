---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventHub.dll-Help.xml
Module Name: Az.EventHub
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/Get-AzEventHubSchemaGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/Get-AzEventHubSchemaGroup.md
ms.openlocfilehash: f66dde3f555ac2658b18691f2216ab38a2c39c9b
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145551416"
---
# Get-AzEventHubSchemaGroup

## SYNOPSIS
Mendapatkan grup skema tertentu dari namespace layanan atau mencantumkan semua grup skema dalam namespace layanan.

## SYNTAX

### NamespaceSchemaGroupParameterSet (Default)
```
Get-AzEventHubSchemaGroup [-ResourceGroupName] <String> [-Namespace] <String> [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SchemaGroupResourceIdParameterSet
```
Get-AzEventHubSchemaGroup [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Get-AzEventHubSchemaGroup mendapatkan grup skema tertentu dari namespace layanan atau mencantumkan semua grup skema di namespace.

## EXAMPLES

### Contoh 1
```powershell
Get-AzEventHubSchemaGroup -ResourceGroupName myresourcegroup -Namespace mynamespace -Name myschemagroup
```

```output
Id                  : /subscriptions/{subscriptionid}/resourceGroups/myresourcegroup/providers/Microsoft.EventHub/namespaces/mynamespace/schemagroups/myschemagroup
Name                : myschemagroup
Location            : East US
Type                : Microsoft.EventHub/Namespaces/SchemaGroups
SchemaCompatibility : Backward
SchemaType          : Avro
GroupProperties     : {key1:value1, name:name}
```

Mendapatkan detail grup skema myschemagroup di mynamespace\` di grup \`sumber daya myresourcegroup\`.\`\` \`

### Contoh 1
```powershell
Get-AzEventHubSchemaGroup -ResourceGroupName myresourcegroup -Namespace mynamespace
```

```output
Id                  : /subscriptions/{subscriptionid}/resourceGroups/myresourcegroup/providers/Microsoft.EventHub/namespaces/mynamespace/schemagroups/myschemagroup
Name                : myschemagroup
Location            : East US
Type                : Microsoft.EventHub/Namespaces/SchemaGroups
SchemaCompatibility : Backward
SchemaType          : Avro
GroupProperties     : {key1:value1, name:name}

Id                  : /subscriptions/{subscriptionid}/resourceGroups/myresourcegroup/providers/Microsoft.EventHub/namespaces/mynamespace/schemagroups/myschemagroup1
Name                : myschemagroup1
Location            : East US
Type                : Microsoft.EventHub/Namespaces/SchemaGroups
SchemaCompatibility : Backward
SchemaType          : Avro
GroupProperties     : {key1:value1, name:name}
```

Mendapatkan daftar semua grup skema di \`mynamespace\` di grup \`sumber daya myresourcegroup\`.

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

### -Name
Nama Grup Skema

```yaml
Type: System.String
Parameter Sets: NamespaceSchemaGroupParameterSet
Aliases: SchemaGroupName

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Nama Namespace

```yaml
Type: System.String
Parameter Sets: NamespaceSchemaGroupParameterSet
Aliases: NamespaceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: NamespaceSchemaGroupParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya Namespace

```yaml
Type: System.String
Parameter Sets: SchemaGroupResourceIdParameterSet
Aliases:

Required: True
Position: 0
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

## OUTPUTS

### Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes

## NOTES

## RELATED LINKS
