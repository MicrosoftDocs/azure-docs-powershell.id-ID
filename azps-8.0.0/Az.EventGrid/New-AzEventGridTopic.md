---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/new-azeventgridtopic
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridTopic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridTopic.md
ms.openlocfilehash: ada9f06d793c2e2ec60e895350b4e598b1a3dcd4
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145529350"
---
# New-AzEventGridTopic

## SYNOPSIS
Membuat Topik Azure Event Grid baru.

## SYNTAX

```
New-AzEventGridTopic [-ResourceGroupName] <String> [-Name] <String> [-Location] <String> [-Tag <Hashtable>]
 [-InputSchema <String>] [-InputMappingField <Hashtable>] [-InputMappingDefaultValue <Hashtable>]
 [-InboundIpRule <Hashtable>] [-IdentityType <String>] [-IdentityId <String[]>] [-PublicNetworkAccess <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat Topik Azure Event Grid baru. Setelah topik dibuat, aplikasi dapat menerbitkan peristiwa ke titik akhir topik.

## EXAMPLES

### Contoh 1
```powershell
New-AzEventGridTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Location westus2
```

Membuat topik \`Event Grid Topic1\` di lokasi \`geografis westus2\` yang ditentukan, dalam grup \`sumber daya MyResourceGroupName\`.

### Contoh 2
```powershell
New-AzEventGridTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Location westus2 -Tag @{ Department="Finance"; Environment="Test" }
```

Membuat topik \`Event Grid Topic1\` di lokasi \`geografis westus2\` yang ditentukan, dalam grup \`sumber daya MyResourceGroupName\` dengan tag "Departemen" dan "Lingkungan" yang ditentukan.

### Contoh: 3
```powershell
New-AzEventGridTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Location westus2 -IdentityType "SystemAssigned"
```

Membuat topik \`Event Grid Topic1\` di lokasi \`geografis westus2\` yang ditentukan, dalam grup \`sumber daya MyResourceGroupName\` dengan \`jenis identitas SystemAssigned\` .

### Contoh 4
```powershell
$id1 = '/subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName'
$id2 = '/subscriptions/{subscriptionId}/resourceGroups/{resourcegroup}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/MSIName'

New-AzEventGridTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Location westus2 -IdentityType "UserAssigned" -IdentityId $id1,$id2
```

Membuat topik \`Event Grid Topic1\` di lokasi \`geografis westus2\` yang ditentukan, dalam grup \`sumber daya MyResourceGroupName\` dengan \`jenis identitas UserAssigned\` dengan id identitas tertentu.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityType
Jenis identitas yang berbeda. Dapat berupa salah satu dari 'SystemAssigned' berikut, 'UserAssigned', 'SystemAssigned, UserAssigned', 'None'

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InboundIpRule
Hashtable yang mewakili daftar aturan IP masuk. Setiap aturan menentukan Alamat IP dalam notasi CIDR misalnya, 10.0.0.0/8 bersama dengan Tindakan yang sesuai untuk dilakukan berdasarkan kecocokan atau tidak ada kecocokan IpMask. Kemungkinan nilai Tindakan termasuk Izinkan saja

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

### -InputMappingDefaultValue
Hashtable yang mewakili bidang pemetaan input dengan nilai default dalam kunci yang dipisahkan spasi = format nilai. Nama kunci yang diizinkan adalah: subjek, jenis peristiwa, dan dataversion. Ini digunakan ketika InputSchemaHelp hanya customeventschema.

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

### -InputMappingField
Hashtable yang mewakili bidang pemetaan input dalam kunci yang dipisahkan spasi = format nilai. Nama kunci yang diizinkan adalah: id, topik, eventtime, subjek, eventtype, dan dataversion. Ini digunakan ketika InputSchemaHelp hanya customeventschema.

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

### -InputSchema
Skema peristiwa input untuk topik tersebut. Nilai yang diizinkan adalah: eventgridschema, customeventschema, atau cloudeventv01Schema. Nilai defaultnya adalah eventgridschema. Perhatikan bahwa jika customeventschema ditentukan, parameter InputMappingField atau/dan InputMappingDefaultValue juga perlu ditentukan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: EventGridSchema, CustomEventSchema, CloudEventSchemaV1_0

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Lokasi topik

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

### -Name
Nama topik.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TopicName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicNetworkAccess
Ini menentukan apakah lalu lintas diizinkan melalui jaringan publik. Secara default diaktifkan. Anda selanjutnya dapat membatasi IP tertentu dengan mengonfigurasi parameter InboundIpRule. Nilai yang diizinkan dinonaktifkan dan diaktifkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: enabled, disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya tempat topik harus dibuat.

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

### -Tag
Hashtable yang mewakili Tag sumber daya.

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

### Microsoft.Azure.Commands.EventGrid.Models.PSTopic

## NOTES

## RELATED LINKS
