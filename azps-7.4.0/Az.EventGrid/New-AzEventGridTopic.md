---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/new-azeventgridtopic
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridTopic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridTopic.md
ms.openlocfilehash: 9ca019368767e6def9d8537ef70a1040dab090c8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142808992"
---
# New-AzEventGridTopic

## SYNOPSIS
Membuat Topik Azure Event Grid baru.

## SYNTAX

```
New-AzEventGridTopic [-ResourceGroupName] <String> [-Name] <String> [-Location] <String> [-Tag <Hashtable>]
 [-InputSchema <String>] [-InputMappingField <Hashtable>] [-InputMappingDefaultValue <Hashtable>]
 [-InboundIpRule <Hashtable>] [-PublicNetworkAccess <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat Topik Azure Event Grid baru. Setelah topik dibuat, aplikasi dapat menerbitkan acara ke titik akhir topik.

## EXAMPLES

### Contoh 1
```powershell
New-AzEventGridTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Location westus2
```

Membuat topik \`Kisi Kejadian1\` di lokasi \`geografis yang ditentukan westus2\`, dalam grup \`sumber daya MyResourceGroupName\`.

### Contoh 2
```powershell
New-AzEventGridTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Location westus2 -Tag @{ Department="Finance"; Environment="Test" }
```

Membuat topik \`Kisi Kejadian1\` di lokasi \`geografis yang ditentukan westus2\`, dalam grup \`sumber daya MyResourceGroupName\` dengan tag tertentu "Departemen" dan "Lingkungan".

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

### -InboundIpRule
Hashtable yang mewakili daftar aturan IP masuk. Setiap aturan menentukan Alamat IP dalam notasi CIDR misalnya, 10.0.0.0/8 bersama dengan Tindakan terkait yang akan dilakukan berdasarkan kecocokan atau tidak ada kecocokan IpMask. Nilai Tindakan yang Mungkin menyertakan Perbolehkan saja

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
Hashtable yang mewakili bidang pemetaan input dengan nilai default dalam spasi yang dipisahkan kunci = format nilai. Nama kunci yang diizinkan adalah: subjek, tipe kejadian, dan dataversi. Ini digunakan ketika InputSchemaHelp hanya merupakan customeventschema.

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
Hashtable yang mewakili bidang pemetaan input dalam spasi yang dipisahkan kunci = format nilai. Nama kunci yang diizinkan adalah: id, topik, waktu kejadian, subjek, tipe kejadian, dan dataversi. Ini digunakan ketika InputSchemaHelp hanya merupakan customeventschema.

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
Skema kejadian input untuk topik tersebut. Nilai yang diizinkan adalah: eventgridschema, customeventschema, atau cloudeventv01Schema. Nilai defaultnya adalah eventgridschema. Perhatikan bahwa jika customeventschema ditentukan, parameter InputMappingField atau/dan InputMappingDefaultValue perlu ditentukan juga.

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

### -Nama
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
Ini menentukan apakah lalu lintas diperbolehkan melalui jaringan publik. Secara default diaktifkan. Anda dapat membatasi lebih lanjut ke IP tertentu dengan mengonfigurasi parameter InboundIpRule. Nilai yang diperbolehkan dinonaktifkan dan diaktifkan.

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

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSTopic

## NOTES

## RELATED LINKS
