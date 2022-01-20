---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/get-azeventgridsubscription
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridSubscription.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridSubscription.md
ms.openlocfilehash: 205353ac4d7dad0f97cd0afabd107efa666f5252
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136370126"
---
# Get-AzEventGridSubscription

## SYNOPSIS
Mendapatkan detail langganan acara, atau mendapatkan daftar semua langganan acara dalam langganan Azure saat ini.

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
Cmdlet Get-AzEventGridSubscription mendapatkan detail langganan Kisi Kejadian yang ditentukan, atau daftar semua langganan Kisi Acara di grup sumber daya atau langganan Azure saat ini.
Jika nama langganan acara disediakan, detail dari satu langganan Kisi Acara akan dikembalikan.
Jika nama langganan acara tidak tersedia, daftar semua langganan acara akan dikembalikan. Jumlah elemen yang dikembalikan dalam daftar ini dikontrol oleh parameter Top. Jika nilai Teratas tidak ditentukan atau $null, daftar akan berisi semua item langganan acara. Jika tidak, Atas akan menunjukkan jumlah maksimum elemen yang akan dikembalikan dalam daftar.
Jika masih ada langganan yang lebih banyak, nilai di NextLink harus digunakan di panggilan berikutnya untuk mendapatkan halaman langganan acara berikutnya.
Akhirnya, parameter ODataQuery digunakan untuk melakukan pemfilteran untuk hasil pencarian. Kueri pemfilteran mengikuti sintaks OData hanya menggunakan properti Name. Operasi yang didukung antara lain: CONTAINS, eq (untuk sama), ne (tidak sama), AND, OR dan NOT.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -TopicName Topic1 -EventSubscriptionName EventSubscription1
```

Mendapatkan detail kejadian langganan \` EventSubscription1 yang dibuat \` untuk topik \` Topic1 di grup sumber daya \` \` MyResourceGroupName \` .

### Contoh 2
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -TopicName Topic1 -EventSubscriptionName EventSubscription1 -IncludeFullEndpointUrl
```

Mendapatkan detail acara Langganan EventSubscription1 yang dibuat untuk topik Topic1 di grup sumber daya \` \` \` \` \` MyResourceGroupName, termasuk URL titik akhir lengkap jika itu adalah langganan acara berbasis \` web.

### Contoh 3
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -TopicName Topic1
```

Dapatkan daftar semua langganan acara yang dibuat untuk topik Topic1 dalam grup \` \` sumber daya \` MyResourceGroupName \` tanpa penomoran halaman.

### Contoh 4
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -TopicName Topic1 -Top 10 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

List the first 10 event subscriptions (if any) created for \` topic Topic1 \` in resource group \` MyResourceGroupName \` that satisfies the $odataFilter query. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk melakukan panggilan ulang dan Get-AzEventGridSubscription hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti saat hasil. NextLink menjadi $null.

### Contoh 5
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -EventSubscriptionName EventSubscription1
```

Mendapatkan detail kejadian langganan \` EventSubscription1 yang dibuat \` untuk grup sumber daya \` MyResourceGroupName. \`

### Contoh 6
```powershell
PS C:\> Get-AzEventGridSubscription -EventSubscriptionName EventSubscription1
```

Dapatkan detail langganan \` acaraSubskrip1 yang dibuat \` untuk langganan Azure yang saat ini dipilih.

### Contoh 7
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName
```

Mendapatkan daftar semua langganan acara global yang dibuat di bawah grup sumber daya \` MyResourceGroupName \` tanpa penomoran halaman.

### Contoh 8
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -Top 5 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

List the first event subscriptions (if any) created under resource group \` MyResourceGroupName \` that satisfies the $odataFilter query. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk melakukan panggilan ulang dan Get-AzEventGridSubscription hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti saat hasil. NextLink menjadi $null.

### Contoh 9
```powershell
PS C:\> Get-AzEventGridSubscription
```

Mendapatkan daftar semua langganan acara global yang dibuat di bawah langganan Azure yang saat ini dipilih tanpa penomoran halaman.

### Contoh 10
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -Top 15 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

List the first global event subscriptions (if any) created under the currently selected Azure subscription that satisfies the $odataFilter query. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk melakukan panggilan ulang dan Get-AzEventGridSubscription hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti saat hasil. NextLink menjadi $null.

### Contoh 11
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -Location westus2
```

Mendapatkan daftar semua langganan acara kawasan yang dibuat di bawah grup sumber daya MyResourceGroupName di lokasi tertentu \` \` \` westus2 \` tanpa penomoran halaman.

### Contoh 12
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -ResourceGroupName MyResourceGroupName -Location westus2 -Top 15 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

List the first regional event subscriptions (if any) created under resource group \` MyResourceGroupName \` in the specified location \` westus2 \` that satisfies the $odataFilter query. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk melakukan panggilan ulang dan Get-AzEventGridSubscription hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti saat hasil. NextLink menjadi $null.

### Contoh 13
```powershell
PS C:\> Get-AzEventGridSubscription -ResourceId "/subscriptions/$subscriptionId/resourceGroups/$resourceGroupName/providers/Microsoft.EventHub/namespaces/$namespaceName"
```

Mendapatkan daftar semua langganan acara yang dibuat untuk ruang nama EventHub yang ditentukan tanpa penomoran halaman.

### Contoh 14
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -ResourceId "/subscriptions/$subscriptionId/resourceGroups/$resourceGroupName/providers/Microsoft.EventHub/namespaces/$namespaceName" -Top 25 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

Membuat daftar 25 langganan acara pertama (jika ada) yang dibuat untuk kumpulan nama EventHub yang ditentukan yang memenuhi $odataFilter pencarian. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk melakukan panggilan ulang dan Get-AzEventGridSubscription hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti saat hasil. NextLink menjadi $null.

### Contoh 15
```powershell
PS C:\> Get-AzEventGridSubscription -TopicTypeName "Microsoft.EventHub.Namespaces" -Location $location
```

Mendapatkan daftar semua langganan acara yang dibuat untuk tipe topik yang ditentukan (ruang nama EventHub) di lokasi yang ditentukan tanpa penomoran halaman.

### Contoh 16
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -TopicTypeName "Microsoft.EventHub.Namespaces" -Location $location -Top 15 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

Membuat daftar 15 langganan acara pertama (jika ada) yang dibuat untuk tipe topik yang ditentukan (ruang nama EventHub) di lokasi yang ditentukan yang memenuhi $odataFilter kueri. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk melakukan panggilan ulang dan Get-AzEventGridSubscription hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti saat hasil. NextLink menjadi $null.

### Contoh 17
```powershell
PS C:\> Get-AzEventGridSubscription -TopicTypeName "Microsoft.Resources.ResourceGroups" -ResourceGroupName MyResourceGroupName
```

Mendapatkan daftar semua langganan acara yang dibuat untuk grup sumber daya tertentu tanpa penomoran halaman.

### Contoh 18
```powershell
$odataFilter = "Name ne 'ABCD'"
PS C:\> Get-AzEventGridSubscription -TopicTypeName "Microsoft.Resources.ResourceGroups" -ResourceGroupName MyResourceGroupName -Top 100 -ODataQuery $odataFilter
PS C:\> Get-AzEventGridSubscription $result.NextLink
```

List the first 100 event subscriptions (if any) created for the specific resource group that satisfies the $odataFilter query. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan acara berikutnya, pengguna diharapkan untuk melakukan panggilan ulang dan Get-AzEventGridSubscription hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti saat hasil. NextLink menjadi $null.

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

### -DomainInputObject
Objek EventGrid Domain.

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
Objek EventGrid Domain Topic.

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
Sertakan URL titik akhir lengkap tujuan langganan acara.

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
Objek EventGrid Topic.

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
Pengidentifikasi sumber daya tempat langganan kejadian dibuat.

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
Kueri OData digunakan untuk memfilter hasil daftar. Pemfilteran saat ini hanya diperbolehkan pada properti Name. Operasi yang didukung antara lain: CONTAINS, eq (untuk sama), ne (tidak sama), AND, OR dan NOT.

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
Nama Jenis Topik

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.EventGrid.Models.PSTopic

### Microsoft.Azure.Commands.EventGrid.Models.PSDomain

### Microsoft.Azure.Commands.EventGrid.Models.PSDomainTopic

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSEventSubscription

## CATATAN

## RELATED LINKS
