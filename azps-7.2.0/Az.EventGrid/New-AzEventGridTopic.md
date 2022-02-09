---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/new-azeventgridtopic
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridTopic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridTopic.md
ms.openlocfilehash: 84771450bd7c7bbf3840e11a30adc2aaec335197
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138311516"
---
# New-AzEventGridTopic

## SYNOPSIS
Membuat Topik Kisi Acara Azure yang baru.

## SYNTAX

```
New-AzEventGridTopic [-ResourceGroupName] <String> [-Name] <String> [-Location] <String> [-Tag <Hashtable>]
 [-InputSchema <String>] [-InputMappingField <Hashtable>] [-InputMappingDefaultValue <Hashtable>]
 [-InboundIpRule <Hashtable>] [-PublicNetworkAccess <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat Topik Kisi Acara Azure yang baru. Setelah topik dibuat, aplikasi dapat menerbitkan kejadian ke titik akhir topik.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzEventGridTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Location westus2
```

Membuat topik Kisi Acara Topic1 \`\` di lokasi geografis tertentu \`westus2\`, di grup sumber daya \`MyResourceGroupName\`.

### Contoh 2
```powershell
PS C:\> New-AzEventGridTopic -ResourceGroupName MyResourceGroupName -Name Topic1 -Location westus2 -Tag @{ Department="Finance"; Environment="Test" }
```

Membuat topik Kisi Acara \`Topic1\` \`di lokasi geografis tertentu westus2\`, \`di grup sumber daya MyResourceGroupName\` dengan tag "Departemen" dan "Lingkungan" yang ditentukan.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Hashtable yang mewakili daftar aturan IP masuk. Setiap aturan menentukan Alamat IP dalam notasi CIDR, misalnya 10.0.0.0/8 beserta Tindakan terkait yang akan dijalankan berdasarkan kecocokan atau tidak ada kecocokan ipMask. Nilai Tindakan yang Mungkin menyertakan Hanya perbolehkan

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
Hashtable mewakili bidang pemetaan input dengan nilai default dalam format tombol yang dipisahkan spasi = nilai. Nama kunci yang diperbolehkan adalah: subjek, tipedata, dan versidata. Ini digunakan saat InputSchemaHelp adalah customeventschema saja.

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
Hashtable yang menyatakan bidang pemetaan input dalam format nilai kunci yang dipisahkan spasi. Nama kunci yang diperbolehkan adalah: id, topik, waktu acara, subjek, tipedata, danversi data. Ini digunakan saat InputSchemaHelp adalah customeventschema saja.

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
Skema kejadian input untuk topik. Nilai yang diperbolehkan adalah: eventgridschema, customeventschema, atau cloudeventv01Schema. Nilai default adalah eventgridschema. Perlu diperhatikan bahwa jika customeventschema ditentukan, maka parameter InputMappingField atau/dan InputMappingDefaultValue juga perlu ditentukan.

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
Ini menentukan jika lalu lintas diperbolehkan melalui jaringan publik. Secara default fitur ini diaktifkan. Anda bisa selanjutnya membatasi untuk IP tertentu dengan mengonfigurasi parameter InboundIpRule. Nilai yang diperbolehkan akan dinonaktifkan dan diaktifkan.

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
Grup sumber daya di mana topik harus dibuat.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSTopic

## CATATAN

## RELATED LINKS
