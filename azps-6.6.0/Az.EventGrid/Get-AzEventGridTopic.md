---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/get-azeventgridtopic
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridTopic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridTopic.md
ms.openlocfilehash: d4d0312609e7c56f034de876e15dc4cc86c612ad
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139976487"
---
# Get-AzEventGridTopic

## SYNOPSIS
Mendapatkan detail topik Kisi Acara, atau mendapatkan daftar semua topik Kisi Acara di langganan Azure saat ini.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.eventgrid/get-azeventgridtopic) untuk informasi terkini.

## SYNTAX

### ResourceGroupNameParameterSet (Default)
```
Get-AzEventGridTopic [[-ResourceGroupName] <String>] [-ODataQuery <String>] [-Top <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### TopicNameParameterSet
```
Get-AzEventGridTopic [-ResourceGroupName] <String> [-Name] <String> [-ODataQuery <String>] [-Top <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdEventSubscriptionParameterSet
```
Get-AzEventGridTopic [-ResourceId] <String> [-ODataQuery <String>] [-Top <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### NextLinkParameterSet
```
Get-AzEventGridTopic [-NextLink <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzEventGridTopic mendapatkan detail Topik Kisi Kejadian yang ditentukan, atau daftar semua topik Kisi Acara di langganan Azure saat ini.
Jika nama topik disediakan, rincian dari satu Topik Kisi Acara dikembalikan.
Jika nama topik tidak tersedia, daftar topik akan dikembalikan. Jumlah elemen yang dikembalikan dalam daftar ini dikontrol oleh parameter Top. Jika nilai Teratas tidak ditentukan atau $null, daftar akan berisi semua item topik. Jika tidak, Atas akan menunjukkan jumlah maksimum elemen yang akan dikembalikan dalam daftar.
Jika masih ada topik lain, nilai di NextLink seharusnya digunakan di panggilan berikutnya untuk mendapatkan halaman topik berikutnya.
Akhirnya, parameter ODataQuery digunakan untuk melakukan pemfilteran untuk hasil pencarian. Kueri pemfilteran mengikuti sintaks OData hanya menggunakan properti Name. Operasi yang didukung antara lain: CONTAINS, eq (untuk sama), ne (tidak sama), AND, OR dan NOT.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzEventGridTopic -ResourceGroup MyResourceGroupName -Name Topic1
```

Mendapatkan detail topik Kisi Acara Topic1 \`di grup\` sumber daya \`MyResourceGroupName\`.

### Contoh 2
```powershell
PS C:\> Get-AzEventGridTopic -ResourceId "/subscriptions/$subscriptionId/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/topics/Topic1"
```

Mendapatkan detail topik Kisi Acara Topic1 \`di grup\` sumber daya \`MyResourceGroupName\`.

### Contoh 3
```powershell
PS C:\> Get-AzEventGridTopic -ResourceGroup MyResourceGroupName
```

List all the Event Grid topics in resource group \`MyResourceGroupName\` without pagination.

### Contoh 4
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> $result = Get-AzEventGridTopic -ResourceGroup MyResourceGroupName -Top 10 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridTopic $result.NextLink
```

List the first 10 Event Grid topics (if any) in resource group \`MyResourceGroupName\` that satisfies the $odataFilter query. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman topik berikutnya, pengguna diharapkan untuk menghubungi kembali halaman Get-AzEventGridTopic menggunakan hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti saat hasil. NextLink menjadi $null.

### Contoh 5
```powershell
PS C:\> Get-AzEventGridTopic
```

List all the Event Grid topics in the subscription without pagination.

### Contoh 6
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> $result = Get-AzEventGridTopic -Top 10 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridTopic $result.NextLink
```

List the first 10 Event Grid topics (if any) in the subscription that satisfies the $odataFilter query. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman topik berikutnya, pengguna diharapkan untuk menghubungi kembali halaman Get-AzEventGridTopic menggunakan hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti saat hasil. NextLink menjadi $null.

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

### -Nama
Nama Topik EventGrid.

```yaml
Type: System.String
Parameter Sets: TopicNameParameterSet
Aliases: TopicName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextLink
Link untuk halaman berikutnya dari sumber daya yang akan diperoleh. Nilai ini diperoleh dengan panggilan cmdlet Get-AzEventGrid pertama ketika sumber daya lainnya masih tersedia untuk dikuer lainnya.

```yaml
Type: System.String
Parameter Sets: NextLinkParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ODataQuery
Kueri OData digunakan untuk memfilter hasil daftar. Pemfilteran saat ini hanya diperbolehkan pada properti Name. Operasi yang didukung antara lain: CONTAINS, eq (untuk sama), ne (tidak sama), AND, OR dan NOT.

```yaml
Type: System.String
Parameter Sets: ResourceGroupNameParameterSet, TopicNameParameterSet, ResourceIdEventSubscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: ResourceGroupNameParameterSet
Aliases: ResourceGroup

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: TopicNameParameterSet
Aliases: ResourceGroup

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi Sumber Daya yang mewakili Topik Kisi Acara.

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

### -Top
Jumlah maksimum sumber daya yang akan diperoleh. Nilai valid adalah antara 1 dan 100. Jika nilai teratas ditentukan dan hasil lainnya masih tersedia, hasilnya akan berisi link ke halaman berikutnya yang akan dikuerifikasi di NextLink. Jika nilai Teratas tidak ditentukan, daftar lengkap sumber daya akan dikembalikan sekaligus.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: ResourceGroupNameParameterSet, TopicNameParameterSet, ResourceIdEventSubscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSTopic

### Microsoft.Azure.Commands.EventGrid.Models.PSTopicListInstance

## CATATAN

## RELATED LINKS
