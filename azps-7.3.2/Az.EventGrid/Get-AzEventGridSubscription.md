---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/get-azeventgridsubscription
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridSubscription.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridSubscription.md
ms.openlocfilehash: 24b8e9318984860a0a0c11474482d79b7aa95b1f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143135441"
---
# Get-AzEventGridSubscription

## SYNOPSIS
Mendapatkan detail langganan acara, atau mendapatkan daftar semua langganan acara dalam langganan Azure saat ini.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.eventgrid/get-azeventgridsubscription) untuk informasi terbaru.

## SYNTAX

### EventSubscriptionTopicNameParameterSet (Default)
```
Get-AzEventGridSubscription [-EventSubscriptionName <String>] [-ResourceGroupName <String>]
 [-TopicName <String>] [-IncludeFullEndpointUrl] [-ODataQuery <String>] [-Top <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdEventSubscriptionParameterSet
```
Get-AzEventGridSubscription [-EventSubscriptionName <String>] [-ResourceId] <String> [-IncludeFullEndpointUrl]
 [-ODataQuery <String>] [-Top <Int32>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### EventSubscriptionDomainNameParameterSet
```
Get-AzEventGridSubscription [-EventSubscriptionName <String>] [-ResourceGroupName <String>]
 [-DomainName <String>] [-DomainTopicName <String>] [-IncludeFullEndpointUrl] [-ODataQuery <String>]
 [-Top <Int32>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### EventSubscriptionTopicTypeNameParameterSet
```
Get-AzEventGridSubscription [-ResourceGroupName <String>] [-TopicTypeName <String>] [-Location <String>]
 [-IncludeFullEndpointUrl] [-ODataQuery <String>] [-Top <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### EventSubscriptionCustomTopicInputObjectParameterSet
```
Get-AzEventGridSubscription [-InputObject] <PSTopic> [-ODataQuery <String>] [-Top <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### EventSubscriptionDomainInputObjectParameterSet
```
Get-AzEventGridSubscription [-DomainInputObject] <PSDomain> [-ODataQuery <String>] [-Top <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### EventSubscriptionDomainTopicInputObjectParameterSet
```
Get-AzEventGridSubscription [-DomainTopicInputObject] <PSDomainTopic> [-ODataQuery <String>] [-Top <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### NextLinkParameterSet
```
Get-AzEventGridSubscription [-NextLink <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzEventGridSubscription mendapatkan detail langganan Kisi Acara tertentu, atau daftar semua langganan Kisi Acara dalam grup sumber daya atau langganan Azure saat ini.
Jika nama langganan acara disediakan, detail satu langganan Kisi Acara akan dikembalikan.
Jika nama langganan acara tidak disediakan, daftar semua langganan acara akan dikembalikan. Jumlah elemen yang dikembalikan dalam daftar ini dikontrol oleh parameter Teratas. Jika Nilai teratas tidak ditentukan atau $null, daftar akan berisi semua item langganan acara. Jika tidak, Top akan menunjukkan jumlah maksimum elemen yang akan dikembalikan dalam daftar.
Jika langganan acara lainnya masih tersedia, nilai di NextLink harus digunakan dalam panggilan berikutnya untuk mendapatkan halaman langganan acara berikutnya.
Terakhir, parameter ODataQuery digunakan untuk melakukan pemfilteran untuk hasil pencarian. Kueri pemfilteran mengikuti sintaks OData menggunakan properti Name saja. Operasi yang didukung meliputi: CONTAINS, eq (untuk sama dengan), ne (untuk tidak sama dengan), AND, OR dan NOT.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -TopicName Topic1 -EventSubscriptionName EventSubscription1
```

Mendapatkan detail langganan acara EventSubscription1\` yang dibuat untuk topik \`Topik1\` dalam grup \`sumber daya MyResourceGroupName\`.\`

### Contoh 2
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -TopicName Topic1 -EventSubscriptionName EventSubscription1 -IncludeFullEndpointUrl
```

Mendapatkan detail langganan \`acara EventSubscription1\` yang dibuat untuk topik \`Topik1\` dalam grup \`sumber daya MyResourceGroupName\`, termasuk URL titik akhir penuh jika merupakan langganan acara berbasis webhook.

### Contoh 3
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -TopicName Topic1
```

Dapatkan daftar semua langganan acara yang dibuat untuk topik \`Topik1\` dalam grup \`sumber daya MyResourceGroupName\` tanpa pagination.

### Contoh 4
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -TopicName Topic1 -Top 10 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

Cantumkan 10 langganan kejadian pertama (jika ada) yang dibuat untuk topik \`Topik1\` dalam grup \`sumber daya MyResourceGroupName\` yang memenuhi kueri $odataFilter. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridSubscription dan menggunakan hasilnya. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

### Contoh 5
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -EventSubscriptionName EventSubscription1
```

Mendapatkan detail langganan \`acara EventSubscription1\` yang dibuat untuk grup \`sumber daya MyResourceGroupName\`.

### Contoh 6
```powershell
PS C:\> Get-AzEventGridSubscription -EventSubscriptionName EventSubscription1
```

Mendapatkan detail langganan \`acara Langganan acara1\` dibuat untuk langganan Azure yang saat ini dipilih.

### Contoh 7
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName
```

Mendapatkan daftar semua langganan acara global yang dibuat di bawah grup \`sumber daya MyResourceGroupName\` tanpa pagination.

### Contoh 8
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -Top 5 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

Cantumkan 5 langganan acara pertama (jika ada) yang dibuat di bawah grup \`sumber daya MyResourceGroupName\` yang memenuhi kueri $odataFilter. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridSubscription dan menggunakan hasilnya. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

### Contoh 9
```powershell
PS C:\> Get-AzEventGridSubscription
```

Mendapatkan daftar semua langganan acara global yang dibuat di bawah langganan Azure yang saat ini dipilih tanpa paginasi.

### Contoh 10
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -Top 15 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

Cantumkan 15 langganan acara global pertama (jika ada) yang dibuat di bawah langganan Azure yang saat ini dipilih yang memenuhi kueri $odataFilter. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridSubscription dan menggunakan hasilnya. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

### Contoh 11
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -Location westus2
```

Mendapatkan daftar semua langganan acara kawasan yang dibuat di bawah grup \`sumber daya MyResourceGroupName\` di lokasi \`yang ditentukan westus2\` tanpa pagination.

### Contoh 12
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -Location westus2 -Top 15 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

Cantumkan 15 langganan acara regional pertama (jika ada) yang dibuat di bawah grup \`sumber daya MyResourceGroupName\` di westus2\` lokasi \`yang ditentukan yang memenuhi kueri $odataFilter. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridSubscription dan menggunakan hasilnya. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

### Contoh 13
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceId "/subscriptions/$subscriptionId/resourceGroups/$resourceGroupName/providers/Microsoft.EventHub/namespaces/$namespaceName"
```

Mendapatkan daftar semua langganan acara yang dibuat untuk ruang nama EventHub tertentu tanpa paginasi.

### Contoh 14
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -ResourceId "/subscriptions/$subscriptionId/resourceGroups/$resourceGroupName/providers/Microsoft.EventHub/namespaces/$namespaceName" -Top 25 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

Cantumkan 25 langganan acara pertama (jika ada) yang dibuat untuk ruang nama EventHub tertentu yang memenuhi kueri $odataFilter. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridSubscription dan menggunakan hasilnya. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

### Contoh 15
```powershell
PS C:\> Get-AzEventGridSubscription -TopicTypeName "Microsoft.EventHub.Namespaces" -Location $location
```

Mendapatkan daftar semua langganan acara yang dibuat untuk tipe topik tertentu (ruang nama EventHub) di lokasi yang ditentukan tanpa paginasi.

### Contoh 16
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -TopicTypeName "Microsoft.EventHub.Namespaces" -Location $location -Top 15 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

Cantumkan 15 langganan kejadian pertama (jika ada) yang dibuat untuk tipe topik tertentu (Ruang nama EventHub) di lokasi tertentu yang memenuhi kueri $odataFilter. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridSubscription dan menggunakan hasilnya. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

### Contoh 17
```powershell
PS C:\> Get-AzEventGridSubscription -TopicTypeName "Microsoft.Resources.ResourceGroups" -ResourceGroupName MyResourceGroupName
```

Mendapatkan daftar semua langganan acara yang dibuat untuk grup sumber daya tertentu tanpa paginasi.

### Contoh 18
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -TopicTypeName "Microsoft.Resources.ResourceGroups" -ResourceGroupName MyResourceGroupName -Top 100 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

Cantumkan 100 langganan kejadian pertama (jika ada) yang dibuat untuk grup sumber daya tertentu yang memenuhi kueri $odataFilter. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridSubscription dan menggunakan hasilnya. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

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

### -DomainInputObject
Objek Domain EventGrid.

```yaml
Type: Microsoft.Azure.Commands.EventGrid.Models.PSDomain
Parameter Sets: EventSubscriptionDomainInputObjectParameterSet
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
Parameter Sets: EventSubscriptionDomainNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DomainTopicInputObject
Objek Topik Domain EventGrid.

```yaml
Type: Microsoft.Azure.Commands.EventGrid.Models.PSDomainTopic
Parameter Sets: EventSubscriptionDomainTopicInputObjectParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DomainTopicName
Nama topik domain EventGrid.

```yaml
Type: System.String
Parameter Sets: EventSubscriptionDomainNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EventSubscriptionName
Nama langganan acara

```yaml
Type: System.String
Parameter Sets: EventSubscriptionTopicNameParameterSet, ResourceIdEventSubscriptionParameterSet, EventSubscriptionDomainNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeFullEndpointUrl
Sertakan URL titik akhir penuh tujuan langganan acara.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EventSubscriptionTopicNameParameterSet, ResourceIdEventSubscriptionParameterSet, EventSubscriptionDomainNameParameterSet, EventSubscriptionTopicTypeNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek Topik EventGrid.

```yaml
Type: Microsoft.Azure.Commands.EventGrid.Models.PSTopic
Parameter Sets: EventSubscriptionCustomTopicInputObjectParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Lokasi

```yaml
Type: System.String
Parameter Sets: EventSubscriptionTopicTypeNameParameterSet
Aliases:

Required: False
Position: Named
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
Parameter Sets: EventSubscriptionTopicNameParameterSet, ResourceIdEventSubscriptionParameterSet, EventSubscriptionDomainNameParameterSet, EventSubscriptionTopicTypeNameParameterSet, EventSubscriptionCustomTopicInputObjectParameterSet, EventSubscriptionDomainInputObjectParameterSet, EventSubscriptionDomainTopicInputObjectParameterSet
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
Parameter Sets: EventSubscriptionTopicNameParameterSet, EventSubscriptionDomainNameParameterSet, EventSubscriptionTopicTypeNameParameterSet
Aliases: ResourceGroup

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya tempat langganan acara telah dibuat.

```yaml
Type: System.String
Parameter Sets: ResourceIdEventSubscriptionParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Top
Kueri OData digunakan untuk memfilter hasil daftar. Pemfilteran saat ini hanya diperbolehkan pada properti Nama. Operasi yang didukung meliputi: CONTAINS, eq (untuk sama dengan), ne (untuk tidak sama dengan), AND, OR dan NOT.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: EventSubscriptionTopicNameParameterSet, ResourceIdEventSubscriptionParameterSet, EventSubscriptionDomainNameParameterSet, EventSubscriptionTopicTypeNameParameterSet, EventSubscriptionCustomTopicInputObjectParameterSet, EventSubscriptionDomainInputObjectParameterSet, EventSubscriptionDomainTopicInputObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TopicName
Nama Topik EventGrid.

```yaml
Type: System.String
Parameter Sets: EventSubscriptionTopicNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TopicTypeName
Nama TopicType

```yaml
Type: System.String
Parameter Sets: EventSubscriptionTopicTypeNameParameterSet
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

### Microsoft.Azure.Commands.EventGrid.Models.PSTopic

### Microsoft.Azure.Commands.EventGrid.Models.PSDomain

### Microsoft.Azure.Commands.EventGrid.Models.PSDomainTopic

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSEventSubscription

## NOTES

## RELATED LINKS
