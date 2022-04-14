---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/get-azeventgridtopic
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridTopic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridTopic.md
ms.openlocfilehash: 49950de95206388f2baa9778de4f40630c98b178
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141997787"
---
# Get-AzEventGridTopic

## SYNOPSIS
Mendapatkan detail topik Kisi Acara, atau mendapatkan daftar semua topik Kisi Acara dalam langganan Azure saat ini.

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
Cmdlet Get-AzEventGridTopic mendapatkan detail Topik Kisi Acara tertentu, atau daftar semua topik Kisi Acara dalam langganan Azure saat ini.
Jika nama topik disediakan, detail dari satu Topik Kisi Acara dikembalikan.
Jika nama topik tidak disediakan, daftar topik akan dikembalikan. Jumlah elemen yang dikembalikan dalam daftar ini dikontrol oleh parameter Teratas. Jika Nilai teratas tidak ditentukan atau $null, daftar akan berisi semua item topik. Jika tidak, Top akan menunjukkan jumlah maksimum elemen yang akan dikembalikan dalam daftar.
Jika topik lainnya masih tersedia, nilai di NextLink harus digunakan dalam panggilan berikutnya untuk mendapatkan halaman topik berikutnya.
Terakhir, parameter ODataQuery digunakan untuk melakukan pemfilteran untuk hasil pencarian. Kueri pemfilteran mengikuti sintaks OData menggunakan properti Name saja. Operasi yang didukung meliputi: CONTAINS, eq (untuk sama dengan), ne (untuk tidak sama dengan), AND, OR dan NOT.

## EXAMPLES

### Contoh 1
```powershell
Get-AzEventGridTopic -ResourceGroup MyResourceGroupName -Name Topic1
```

Mendapatkan detail topik \`Kisi Kejadian Topik1\` dalam grup \`sumber daya MyResourceGroupName\`.

### Contoh 2
```powershell
Get-AzEventGridTopic -ResourceId "/subscriptions/$subscriptionId/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/topics/Topic1"
```

Mendapatkan detail topik \`Kisi Kejadian Topik1\` dalam grup \`sumber daya MyResourceGroupName\`.

### Contoh 3
```powershell
Get-AzEventGridTopic -ResourceGroup MyResourceGroupName
```

Cantumkan semua topik Kisi Kejadian dalam grup \`sumber daya MyResourceGroupName\` tanpa pagination.

### Contoh 4
```powershell
$odataFilter = "Name ne 'ABCD'"
$result = Get-AzEventGridTopic -ResourceGroup MyResourceGroupName -Top 10 -ODataQuery $odataFilter
Get-AzEventGridTopic $result.NextLink
```

Cantumkan 10 topik Kisi Kejadian pertama (jika ada) dalam grup \`sumber daya MyResourceGroupName\` yang memenuhi kueri $odataFilter. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman topik berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridTopic dan menggunakan hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

### Contoh 5
```powershell
Get-AzEventGridTopic
```

Cantumkan semua topik Kisi Acara dalam langganan tanpa paginasi.

### Contoh 6
```powershell
$odataFilter = "Name ne 'ABCD'"
$result = Get-AzEventGridTopic -Top 10 -ODataQuery $odataFilter
Get-AzEventGridTopic $result.NextLink
```

Cantumkan 10 topik Kisi Kejadian pertama (jika ada) dalam langganan yang memenuhi kueri $odataFilter. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman topik berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridTopic dan menggunakan hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

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
Tautan untuk halaman sumber daya berikutnya yang akan diperoleh. Nilai ini diperoleh dengan panggilan cmdlet pertama Get-AzEventGrid ketika lebih banyak sumber daya masih tersedia untuk dikueri.

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
Kueri OData digunakan untuk memfilter hasil daftar. Pemfilteran saat ini hanya diperbolehkan pada properti Nama. Operasi yang didukung meliputi: CONTAINS, eq (untuk sama dengan), ne (untuk tidak sama dengan), AND, OR dan NOT.

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
Pengidentifikasi Sumber Daya yang mewakili Topik Kisi Kejadian.

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
Jumlah sumber daya maksimum yang akan diperoleh. Nilai valid adalah antara 1 dan 100. Jika nilai teratas ditentukan dan hasil lainnya masih tersedia, hasilnya akan berisi link ke halaman berikutnya yang akan dikueri di NextLink. Jika nilai Teratas tidak ditentukan, daftar lengkap sumber daya akan dikembalikan sekaligus.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSTopic

### Microsoft.Azure.Commands.EventGrid.Models.PSTopicListInstance

## CATATAN

## RELATED LINKS
