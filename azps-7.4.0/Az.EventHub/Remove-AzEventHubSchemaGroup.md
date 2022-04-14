---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventHub.dll-Help.xml
Module Name: Az.EventHub
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/Remove-AzEventHubSchemaGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/Remove-AzEventHubSchemaGroup.md
ms.openlocfilehash: 40de3eeb850698c9018561a57978c31ecc9cbe2a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141837248"
---
# Remove-AzEventHubSchemaGroup

## SYNOPSIS
Menghapus grup skema dari ruang nama.

## SYNTAX

### NamespaceSchemaGroupParameterSet
```
Remove-AzEventHubSchemaGroup [-ResourceGroupName] <String> [-Namespace] <String> [-Name] <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SchemaGroupInputObjectParameterSet
```
Remove-AzEventHubSchemaGroup [-InputObject] <PSEventHubsSchemaRegistryAttributes> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SchemaGroupResourceIdParameterSet
```
Remove-AzEventHubSchemaGroup [-ResourceId] <String> [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Removes-AzEventHubSchemaGroup menghapus grup skema dari ruang nama.

## EXAMPLES

### Contoh 1
```powershell
Remove-AzEventHubSchemaGroup -ResourceGroupName myresourcegroup -Namespace mynamespace -Name myschemagroup
```
Menghapus grup \`skema myschemagroup\` di ruang \`nama ruang\` saya di grup \`sumber daya myresourcegroup\`


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

### -InputObject
Objek Namespace

```yaml
Type: Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes
Parameter Sets: SchemaGroupInputObjectParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Grup Skema

```yaml
Type: System.String
Parameter Sets: NamespaceSchemaGroupParameterSet
Aliases: SchemaGroupName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Nama Ruang Nama

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

### -PassThru
{{ Fill PassThru Description }}

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
Id Sumber Daya Ruang Nama

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes

## OUTPUTS

### Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes

## CATATAN

## RELATED LINKS
