---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/new-azeventgriddomain
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridDomain.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridDomain.md
ms.openlocfilehash: 930e2255df669e194f2fa0251637d8dbfcec4203
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145769718"
---
# New-AzEventGridDomain

## SYNOPSIS
Membuat Domain Azure Event Grid baru.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.eventgrid/new-azeventgriddomain) untuk informasi terbaru.

## SYNTAX

```
New-AzEventGridDomain [-ResourceGroupName] <String> [-Name] <String> [-Location] <String> [-Tag <Hashtable>]
 [-InputSchema <String>] [-InputMappingField <Hashtable>] [-InputMappingDefaultValue <Hashtable>]
 [-InboundIpRule <Hashtable>] [-PublicNetworkAccess <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat Domain Azure Event Grid baru. Setelah domain dibuat, aplikasi dapat menerbitkan peristiwa ke titik akhir topik.

## EXAMPLES

### Contoh 1

Membuat domain \`Event Grid Domain1\` di lokasi \`geografis yang ditentukan westus2\`, dalam grup \`sumber daya MyResourceGroupName\`.

```powershell
New-AzEventGridDomain -ResourceGroupName MyResourceGroupName -Name Domain1 -Location westus2
```

```output
ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/domain1
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain1.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              :
```

### Contoh 2

Membuat domain \`Event Grid Domain1\` di lokasi \`geografis yang ditentukan westus2\`, dalam grup \`sumber daya MyResourceGroupName\` dengan tag "Departemen" dan "Lingkungan" yang ditentukan.

```powershell
New-AzEventGridDomain -ResourceGroupName MyResourceGroupName -Name Domain1 -Location westus2 -Tag @{ Department="Finance"; Environment="Test" }
```

```output
ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/domain1
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain1.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              : {[Department, Finance], [Environment, Test]}
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

### -InboundIpRule
Hashtable yang mewakili daftar aturan IP masuk. Setiap aturan menentukan Alamat IP dalam notasi CIDR misalnya, 10.0.0.0/8 bersama dengan Tindakan yang sesuai yang akan dilakukan berdasarkan kecocokan atau tidak ada kecocokan IpMask. Kemungkinan nilai Tindakan termasuk Izinkan saja

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
Hashtable yang mewakili bidang pemetaan input dengan nilai default dalam kunci yang dipisahkan spasi = format nilai. Nama kunci yang diizinkan adalah: subjek, jenis peristiwa, dan dataversi. Ini digunakan ketika InputSchemaHelp hanya customeventschema.

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
Lokasi domain.

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
Nama domain EventGrid.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DomainName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicNetworkAccess
Ini menentukan apakah lalu lintas diizinkan melalui jaringan publik. Secara default diaktifkan. Anda dapat membatasi lebih lanjut ke IP tertentu dengan mengonfigurasi parameter InboundIpRule. Nilai yang diizinkan dinonaktifkan dan diaktifkan.

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
Nama grup sumber daya.

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

### Microsoft.Azure.Commands.EventGrid.Models.PSDomain

## NOTES

## RELATED LINKS
