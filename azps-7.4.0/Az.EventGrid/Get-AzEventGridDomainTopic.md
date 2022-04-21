---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/get-azeventgriddomaintopic
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridDomainTopic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridDomainTopic.md
ms.openlocfilehash: 99ddea00a8e825c21becba9a9346deca1818d2aa
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142684036"
---
# Get-AzEventGridDomainTopic

## SYNOPSIS
Mendapatkan detail topik domain Kisi Kejadian, atau mendapatkan daftar semua topik domain Kisi Acara di bawah domain Kisi Kejadian tertentu dalam langganan Azure saat ini.

## SYNTAX

### DomainTopicNameParameterSet (Default)
```
Get-AzEventGridDomainTopic [-ResourceGroupName] <String> [-DomainName] <String> [-Name <String>]
 [-ODataQuery <String>] [-Top <Int32>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdDomainTopicParameterSet
```
Get-AzEventGridDomainTopic [-ResourceId] <String> [-ODataQuery <String>] [-Top <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### NextLinkParameterSet
```
Get-AzEventGridDomainTopic [-NextLink <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzEventGridDomainTopic mendapatkan detail topik domain Kisi Kejadian tertentu, atau daftar semua topik domain Kisi Acara di bawah domain tertentu dalam langganan Azure saat ini.
Jika nama topik domain disediakan, detail dari satu topik domain Kisi Kejadian dikembalikan.
Jika nama topik domain tidak disediakan, daftar topik domain di bawah nama domain tertentu akan dikembalikan. Jumlah elemen yang dikembalikan dalam daftar ini dikontrol oleh parameter Teratas. Jika Nilai teratas tidak ditentukan atau $null, daftar akan berisi semua item topik domain. Jika tidak, Top akan menunjukkan jumlah maksimum elemen yang akan dikembalikan dalam daftar.
Jika topik domain lainnya masih tersedia, nilai di NextLink harus digunakan dalam panggilan berikutnya untuk mendapatkan halaman topik domain berikutnya.
Terakhir, parameter ODataQuery digunakan untuk melakukan pemfilteran untuk hasil pencarian. Kueri pemfilteran mengikuti sintaks OData menggunakan properti Name saja. Operasi yang didukung meliputi: CONTAINS, eq (untuk sama dengan), ne (untuk tidak sama dengan), AND, OR dan NOT.

## EXAMPLES

### Contoh 1

Mendapatkan detail topik \`domain Kisi Kejadian DomainTopic1\` di bawah Domain \`Kisi Kejadian1\` dalam grup \`sumber daya MyResourceGroupName\`.

```powershell
Get-AzEventGridDomainTopic -ResourceGroup MyResourceGroupName -DomainName Domain1 -DomainTopicName DomainTopic1
```

```output
ResourceGroupName : MyResourceGroupName
DomainName        : DomainTopic1
DomainTopicName   : Topic1
Id                : /subscriptions/20902276-e53b-4421-8565-f57bcad74f6e/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1/topics/DomainTopic1
Type              : Microsoft.EventGrid/domains/topics
ProvisioningState : Succeeded
```

### Contoh 2

Mendapatkan detail topik \`domain Kisi Kejadian DomainTopic1\` di bawah Domain \`Kisi Kejadian1\` dalam grup \`sumber daya MyResourceGroupName\` menggunakan opsi ResourceId.

```powershell
Get-AzEventGridDomainTopic -ResourceId "/subscriptions/$subscriptionId/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1/topics/DomainTopic1"
```

```output
ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
DomainTopicName   : DomainTopic1
Id                : /subscriptions/20902276-e53b-4421-8565-f57bcad74f6e/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1/topics/DomainTopic1
Type              : Microsoft.EventGrid/domains/topics
ProvisioningState : Succeeded
```

### Contoh 3

Cantumkan semua topik domain Kisi Kejadian di bawah Domain \`Kisi Kejadian1\` dalam grup \`sumber daya MyResourceGroupName\` tanpa pagination (semua hasil dikembalikan dalam satu bidikan).

```powershell
$result=Get-AzEventGridDomainTopic -ResourceGroup MyResourceGroupName -DomainName Domain1
echo $result.PsDomainTopicsList
```

```output
ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
DomainTopicName   : DomainTopic1
Id                : /subscriptions/20902276-e53b-4421-8565-f57bcad74f6e/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1/topics/DomainTopic1
Type              : Microsoft.EventGrid/domains/topics
ProvisioningState : Succeeded


ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
DomainTopicName   : DomainTopic2
Id                : /subscriptions/20902276-e53b-4421-8565-f57bcad74f6e/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1/topics/DomainTopic2
Type              : Microsoft.EventGrid/domains/topics
ProvisioningState : Succeeded


ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
DomainTopicName   : DomainTopic3
Id                : /subscriptions/20902276-e53b-4421-8565-f57bcad74f6e/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1/topics/DomainTopic3
Type              : Microsoft.EventGrid/domains/topics
ProvisioningState : Succeeded
```

### Contoh 4

Mencantumkan semua topik domain Kisi Kejadian di bawah Domain \`Kisi Kejadian1\` dalam grup \`sumber daya MyResourceGroupName\` tanpa pagination (semua hasil dikembalikan dalam satu bidikan) menggunakan opsi ResourceId

```powershell
$result=Get-AzEventGridDomainTopic -ResourceId "/subscriptions/$subscriptionId/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1"
echo $result.PsDomainTopicsList
```

```output
ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
DomainTopicName   : DomainTopic1
Id                : /subscriptions/20902276-e53b-4421-8565-f57bcad74f6e/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1/topics/DomainTopic1
Type              : Microsoft.EventGrid/domains/topics
ProvisioningState : Succeeded


ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
DomainTopicName   : DomainTopic2
Id                : /subscriptions/20902276-e53b-4421-8565-f57bcad74f6e/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1/topics/DomainTopic2
Type              : Microsoft.EventGrid/domains/topics
ProvisioningState : Succeeded


ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
DomainTopicName   : DomainTopic3
Id                : /subscriptions/20902276-e53b-4421-8565-f57bcad74f6e/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1/topics/DomainTopic3
Type              : Microsoft.EventGrid/domains/topics
ProvisioningState : Succeeded
```

### Contoh 5

Cantumkan topik domain Kisi Kejadian (jika ada) di bawah domain \`Domain1\` dalam grup \`sumber daya MyResourceGroupName\` yang memenuhi kueri $odataFilter 10 topik domain dalam satu waktu. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman topik domain berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridDomainTopic dan menggunakan hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

```powershell
$total = 0
$odataFilter = "Name ne 'ABCD'"
$result = Get-AzEventGridDomainTopic -ResourceGroup MyResourceGroupName -DomainName Domain1 -Top 10 -ODataQuery $odataFilter
$total += $result.Count
while ($result.NextLink -ne $Null)
    {
        $result = Get-AzEventGridDomainTopic -NextLink $result.NextLink
        $total += $result.Count
    }

echo "Total number of domain topics is $Total"
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

### -DomainName
Nama domain EventGrid.

```yaml
Type: System.String
Parameter Sets: DomainTopicNameParameterSet
Aliases: Domain

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama topik domain EventGrid.

```yaml
Type: System.String
Parameter Sets: DomainTopicNameParameterSet
Aliases: DomainTopicName

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
Parameter Sets: DomainTopicNameParameterSet, ResourceIdDomainTopicParameterSet
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
Parameter Sets: DomainTopicNameParameterSet
Aliases: ResourceGroup

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi Sumber Daya yang mewakili Domain Kisi Acara atau Topik Domain Kisi.

```yaml
Type: System.String
Parameter Sets: ResourceIdDomainTopicParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Top
Kueri OData digunakan untuk memfilter hasil daftar. Pemfilteran saat ini hanya diperbolehkan pada properti Nama. Operasi yang didukung meliputi: CONTAINS, eq (untuk sama dengan), ne (untuk tidak sama dengan), AND, OR dan NOT.

```yaml
Type: System.Int32
Parameter Sets: DomainTopicNameParameterSet, ResourceIdDomainTopicParameterSet
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

### System.Int32

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSDomainTopic

### Microsoft.Azure.Commands.EventGrid.Models.PSDomainTopicListInstance

## NOTES

## RELATED LINKS
