---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Update-AzEventGridSystemTopicEventSubscription.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Update-AzEventGridSystemTopicEventSubscription.md
ms.openlocfilehash: 901a25d1659ff38939b6e5d92188710bb76a01a0
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145550377"
---
# Update-AzEventGridSystemTopicEventSubscription

## SYNOPSIS
Perbarui properti langganan peristiwa topik Sistem Event Grid.

## SYNTAX

### TopicNameParameterSet (Default)
```
Update-AzEventGridSystemTopicEventSubscription [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SystemTopicEventSuscriptionParameterSet
```
Update-AzEventGridSystemTopicEventSubscription -EventSubscriptionName <String> -ResourceGroupName <String>
 -SystemTopicName <String> [-DeadLetterEndpoint <String>] [-DeliveryAttributeMapping <String[]>]
 [-Endpoint <String>] [-EndpointType <String>] [-Label <String[]>] [-StorageQueueMessageTtl <Int64>]
 [-AdvancedFilter <Hashtable[]>] [-AdvancedFilteringOnArray] [-IncludedEventType <String[]>]
 [-SubjectBeginsWith <String>] [-SubjectEndsWith <String>] [-SubjectCaseSensitive]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Perbarui properti langganan peristiwa topik Sistem Event Grid. Ini dapat digunakan untuk memperbarui filter, tujuan, atau label langganan peristiwa yang ada.

## EXAMPLES

### Contoh 1
```powershell
Update-AzEventGridSystemTopicEventSubscription -EventSubscriptionName ES1 -SystemTopicName Topic1 -ResourceGroup MyResourceGroupName -Endpoint https://requestb.in/1kxxoui1
```

Memperbarui titik akhir langganan \`peristiwa ES1\` untuk topik \`sistem Topic1\` di grup \`sumber daya MyResourceGroupName\` menjadi \`https://requestb.in/1kxxoui1\`

### Contoh 2
```powershell
$labels = "Finance", "HR"
Update-AzEventGridSystemTopicEventSubscription -EventSubscriptionName ES1 -SystemTopicName Topic1 -ResourceGroup MyResourceGroupName -Label $labels
```

Memperbarui properti langganan \`peristiwa ES1\` untuk topik \`sistem Topic1\` di \`MyResourceGroupName\` dengan label baru $labels.

### Contoh: 3
```powershell
Update-AzEventGridSystemTopicEventSubscription -EventSubscriptionName ES1 -SystemTopicName Topic1 -ResourceGroup MyResourceGroupName -Endpoint https://requestb.in/1kxxoui1 -SubjectEndsWith "jpg"
```

Memperbarui properti langganan \`peristiwa ES1\` untuk topik \`sistem Topic1\` di \`MyResourceGroupName\` dengan titikhttps://requestb.in/1kxxoui1\\` akhir baru ' dan filter SubjectEndsWith baru sebagai \`jpg\`

## PARAMETERS

### -AdvancedFilter
Filter tingkat lanjut yang menentukan array beberapa nilai Hashtable yang digunakan untuk pemfilteran berbasis atribut.
Setiap nilai Hashtable memiliki info kunci-nilai berikut: Operasi, Kunci, dan Nilai atau Nilai.
Operator dapat berupa salah satu nilai berikut: NumberIn, NumberNotIn, NumberLessThan, NumberGreaterThan, NumberLessThanOrEquals, NumberGreaterThanOrEquals, BoolEquals, StringIn, StringNotIn, StringBeginsWith, StringEndsWith atau StringContains.
Kunci mewakili properti payload tempat kebijakan pemfilteran lanjutan diterapkan.
Terakhir, Nilai atau Nilai mewakili nilai atau kumpulan nilai yang akan dicocokkan.
Ini bisa menjadi nilai tunggal dari jenis yang sesuai atau array nilai.
Sebagai contoh parameter filter tingkat lanjut: $AdvancedFilters=@($AdvFilter 1, $AdvFilter 2) di mana $AdvFilter 1=@{operator="NumberIn"; key="Data.Key1"; Values=@(1,2)} and $AdvFilter 2=@{operator="StringBringsWith"; key="Subject"; Nilai=@("SubjectPrefix1","SubjectPrefix2")}

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AdvancedFilteringOnArray
Kehadiran parameter ini menunjukkan bahwa pemfilteran tingkat lanjut pada array diaktifkan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeadLetterEndpoint
Titik akhir yang digunakan untuk menyimpan peristiwa yang tidak terkiror.
Tentukan ID sumber daya Azure dari kontainer blob Storage.
Misalnya: /subscriptions/\[SubscriptionId\]/resourceGroups/\[ResourceGroupName\]/providers/Microsoft.Storage /storageAccounts/\[StorageAccountName\]/blobServices/default/containers/\[ContainerName\].

```yaml
Type: System.String
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -DeliveryAttributeMapping
Pemetaan atribut pengiriman untuk langganan peristiwa topik sistem ini

```yaml
Type: System.String[]
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Titik akhir
Titik akhir tujuan langganan peristiwa.
Ini bisa berupa URL webhook, atau ID sumber daya Azure dari EventHub, antrean penyimpanan, hybridconnection, servicebusqueue, servicebustopic, atau azurefunction.
Misalnya, ID sumber daya untuk koneksi hibrid mengambil formulir berikut: /subscriptions/\[Azure Subscription ID\]/resourceGroups/\[ResourceGroupName\]/providers/Microsoft.Relay/namespaces/\[NamespaceName\]/hybridConnections/\[HybridConnectionName\].
Diharapkan bahwa titik akhir tujuan akan dibuat dan tersedia untuk digunakan sebelum menjalankan cmdlet Event Grid apa pun.

```yaml
Type: System.String
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndpointType
Jenis Titik Akhir.
Ini bisa berupa webhook, eventhub, storagequeue, hybridconnection, servicebusqueue, servicebustopic atau azurefunction.
Nilai defaultnya adalah webhook.

```yaml
Type: System.String
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EventSubscriptionName
Nama langganan peristiwa EventGrid.

```yaml
Type: System.String
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludedEventType
Filter yang menentukan daftar jenis peristiwa yang akan disertakan.
Jika tidak ditentukan, semua jenis peristiwa (untuk topik dan domain kustom) atau jenis peristiwa default (untuk jenis topik lain) akan disertakan.

```yaml
Type: System.String[]
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Label
Label untuk langganan peristiwa.

```yaml
Type: System.String[]
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

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
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageQueueMessageTtl
Waktu dalam milidetik untuk waktu hidup pesan antrean penyimpanan

```yaml
Type: System.Int64
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubjectBeginsWith
Filter yang menentukan bahwa hanya peristiwa yang cocok dengan awalan subjek yang ditentukan yang akan disertakan.
Jika tidak ditentukan, peristiwa dengan semua prefiks subjek akan disertakan.

```yaml
Type: System.String
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubjectCaseSensitive
Filter yang menentukan bahwa bidang subjek harus dibandingkan dengan cara yang peka huruf besar/kecil.
Jika tidak ditentukan, subjek akan dibandingkan dengan cara yang tidak peka huruf besar/kecil.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubjectEndsWith
Filter yang menentukan bahwa hanya peristiwa yang cocok dengan akhiran subjek yang ditentukan yang akan disertakan.
Jika tidak ditentukan, peristiwa dengan semua akhiran subjek akan disertakan.

```yaml
Type: System.String
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SystemTopicName
Nama topik EventGrid.

```yaml
Type: System.String
Parameter Sets: SystemTopicEventSuscriptionParameterSet
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

### System.Int64

### System.Collections.Hashtable[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSEventSubscription

## NOTES

## RELATED LINKS
