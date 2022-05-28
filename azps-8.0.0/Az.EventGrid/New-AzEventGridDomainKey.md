---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/new-azeventgriddomainkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridDomainKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridDomainKey.md
ms.openlocfilehash: 639efaf3ab0452a5ca9533057919054936a3facf
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145537080"
---
# New-AzEventGridDomainKey

## SYNOPSIS
Meregenerasi kunci akses bersama untuk Domain Azure Event Grid.

## SYNTAX

### DomainNameParameterSet (Default)
```
New-AzEventGridDomainKey [-ResourceGroupName] <String> [-DomainName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DomainInputObjectParameterSet
```
New-AzEventGridDomainKey [-Name] <String> [-DomainInputObject] <PSDomain>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdEventSubscriptionParameterSet
```
New-AzEventGridDomainKey [-Name] <String> [-DomainResourceId] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Meregenerasi kunci akses bersama untuk Domain Azure Event Grid.

## EXAMPLES

### Contoh 1

Regenerasi kunci yang sesuai dengan key1 \''\ dari domain \`Event Grid Domain1\` dalam grup \`sumber daya MyResourceGroupName\`.

```powershell
New-AzEventGridDomainKey -ResourceGroupName MyResourceGroupName -DomainName Domain1 -Name key1
```

```output
Key1                                         Key2
----                                         ----
<New Value for Key1>                        <Old Value for Key2>
```

### Contoh 2

Regenerasi kunci yang sesuai dengan key1 \''\ dari domain \`Event Grid Domain1\` dalam grup \`sumber daya MyResourceGroupName\`.

```powershell
Get-AzEventGridDomain -ResourceGroupName MyResourceGroupName -Name Domain1 | New-AzEventGridTopicKey -KeyName "key1"
```

```output
Key1                                         Key2
----                                         ----
<New Value for Key1>                        <Old Value for Key2>
```

### Contoh: 3

Regenerasi kunci yang sesuai dengan key2 \''\ dari domain \`Event Grid Domain1\` dalam grup \`sumber daya MyResourceGroupName\` menggunakan Id sumber daya lengkapnya.

```powershell
New-AzEventGridDomainKey -DomainResourceId /subscriptions/$subscriptionId/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1 -KeyName Key2
```

```output
Key1                                         Key2
----                                         ----
<Old Value for Key1>                        <New Value for Key2>
```

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

### -DomainInputObject
Objek Domain EventGrid.

```yaml
Type: Microsoft.Azure.Commands.EventGrid.Models.PSDomain
Parameter Sets: DomainInputObjectParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DomainName
Nama domain EventGrid.

```yaml
Type: System.String
Parameter Sets: DomainNameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DomainResourceId
Pengidentifikasi Sumber Daya yang mewakili Domain Event Grid.

```yaml
Type: System.String
Parameter Sets: ResourceIdEventSubscriptionParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Nama kunci yang perlu diregenerasi

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: KeyName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: DomainNameParameterSet
Aliases: ResourceGroup

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

### Microsoft.Azure.Commands.EventGrid.Models.PSDomain

## OUTPUTS

### Microsoft.Azure.Management.EventGrid.Models.DomainSharedAccessKeys

## NOTES

## RELATED LINKS
