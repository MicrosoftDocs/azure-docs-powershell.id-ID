---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventHub.dll-Help.xml
Module Name: Az.EventHub
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/New-AzEventHubSchemaGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/New-AzEventHubSchemaGroup.md
ms.openlocfilehash: b19ae8199bc4d667fb80a62244e3ca83c72d35ee
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144602816"
---
# New-AzEventHubSchemaGroup

## SYNOPSIS
Membuat grup skema di namespace.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.eventhub/new-azeventhubschemagroup) untuk informasi terbaru.

## SYNTAX

```
New-AzEventHubSchemaGroup [-ResourceGroupName] <String> [-Namespace] <String> [-Name] <String>
 -SchemaCompatibility <String> -SchemaType <String> [-GroupProperty <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzEventHubSchemaGroup membuat grup skema di namespace layanan.

## EXAMPLES

### Contoh 1
```powershell
New-AzEventHubSchemaGroup -ResourceGroupName myresourcegroup -Namespace mynamespace -Name myschemagroup -SchemaCompatibility Forward -SchemaType Avro -GroupProperty @{'key1'='value1';'key2'='value2'}
```

```output
Id                  : /subscriptions/{subscriptionid}/resourceGroups/myresourcegroup/providers/Microsoft.EventHub/namespaces/mynamespace/schemagroups/myschemagroup
Name                : myschemagroup
Location            : East US
Type                : Microsoft.EventHub/Namespaces/SchemaGroups
SchemaCompatibility : Forward
SchemaType          : Avro
GroupProperties     : {key1:value1, key2:value2}
```

Membuat grup \`skema myschemagroup\` di namespace \`mynamespace\` di grup \`sumber daya myresourcegroup\`

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

### -GroupProperty
Properti grup eventhub

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Nama Grup Skema

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SchemaGroupName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Nama Namespace

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

### -SchemaCompatibility
Kompatibilitas Skema.
Maju, Mundur

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: None, Forward, Backward

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SchemaType
Jenis Skema

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Avro

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

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes

## NOTES

## RELATED LINKS
