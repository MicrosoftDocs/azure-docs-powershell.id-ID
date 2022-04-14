---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/get-azeventgriddomain
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridDomain.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridDomain.md
ms.openlocfilehash: 84629045971619bdf5da05cb37062b88612eb40b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141837347"
---
# Get-AzEventGridDomain

## SYNOPSIS
Mendapatkan detail domain Kisi Acara, atau mendapatkan daftar semua domain Kisi Acara dalam langganan Azure saat ini.

## SYNTAX

### ResourceGroupNameParameterSet (Default)
```
Get-AzEventGridDomain [[-ResourceGroupName] <String>] [-ODataQuery <String>] [-Top <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### DomainNameParameterSet
```
Get-AzEventGridDomain [-ResourceGroupName] <String> [-Name] <String> [-ODataQuery <String>] [-Top <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdEventSubscriptionParameterSet
```
Get-AzEventGridDomain [-ResourceId] <String> [-ODataQuery <String>] [-Top <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### NextLinkParameterSet
```
Get-AzEventGridDomain [-NextLink <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzEventGridDomain mendapatkan detail domain Kisi Kejadian tertentu, atau daftar semua domain Kisi Acara dalam langganan Azure saat ini.
Jika nama domain disediakan, detail satu domain Kisi Kejadian dikembalikan.
Jika nama domain tidak disediakan, daftar domain akan dikembalikan. Jumlah elemen yang dikembalikan dalam daftar ini dikontrol oleh parameter Teratas. Jika Nilai teratas tidak ditentukan atau $null, daftar akan berisi semua item domain yang dikembalikan sekaligus. Jika tidak, Top akan menunjukkan jumlah maksimum elemen yang akan dikembalikan dalam daftar.
Jika domain lain masih tersedia, nilai di NextLink harus digunakan dalam panggilan berikutnya untuk mendapatkan halaman domain berikutnya.
Terakhir, parameter ODataQuery digunakan untuk melakukan pemfilteran untuk hasil pencarian. Kueri pemfilteran mengikuti sintaks OData menggunakan properti Name saja. Operasi yang didukung meliputi: CONTAINS, eq (untuk sama dengan), ne (untuk tidak sama dengan), AND, OR dan NOT.

## EXAMPLES

### Contoh 1

Mendapatkan detail domain \`Kisi Kejadian Domain1\` dalam grup \`sumber daya MyResourceGroupName\`.

```powershell
Get-AzEventGridDomain -ResourceGroup MyResourceGroupName -Name Domain1
```

```output
ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/myresourcegroupname/providers/Microsoft.EventGrid/domains/domain1
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain1.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              : {[Tag1, Value1], [Tag2, Value2]}
```

### Contoh 2

Mendapatkan detail domain \`Kisi Kejadian Domain1\` dalam grup \`sumber daya MyResourceGroupName\` menggunakan opsi ResourceId.

```powershell
Get-AzEventGridDomain -ResourceId "/subscriptions/$subscriptionId/resourceGroups/MyResourceGroupName/providers/Microsoft.EventGrid/domains/Domain1"
```

```output
ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/myresourcegroupname/providers/Microsoft.EventGrid/domains/domain1
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain1.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              : {[Tag1, Value1], [Tag2, Value2]}
```

### Contoh 3

Mencantumkan semua domain Kisi Kejadian dalam grup \`sumber daya MyResourceGroupName\` tanpa pagination (semua domain dikembalikan dalam satu bidikan)

```powershell
$result=Get-AzEventGridDomain -ResourceGroup MyResourceGroupName
Write-Output $result.PsDomainsList
```

```output
ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/myresourcegroupname/providers/Microsoft.EventGrid/domains/domain1
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain1.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              : {[Tag1, Value1], [Tag2, Value2]}

ResourceGroupName : MyResourceGroupName
DomainName        : Domain2
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/myresourcegroupname/providers/Microsoft.EventGrid/domains/domain2
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain2.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              :

ResourceGroupName : MyResourceGroupName
DomainName        : Domain3
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/myresourcegroupname/providers/Microsoft.EventGrid/domains/domain3
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain3.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              : {[Tag3, Value3], [Tag4, Value4]}

ResourceGroupName : MyResourceGroupName
DomainName        : Domain4
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/myresourcegroupname/providers/Microsoft.EventGrid/domains/domain4
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain4.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              :
```

### Contoh 4

Cantumkan domain Kisi Kejadian (jika ada) dalam grup \`sumber daya MyResourceGroupName\` yang memenuhi kueri $odataFilter 10 domain dalam satu waktu. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman domain berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridDomain dan menggunakan hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

```powershell
$total = 0
$odataFilter = "Name ne 'ABCD'"
$result = Get-AzEventGridDomain -ResourceGroup MyResourceGroupName -Top 10 -ODataQuery $odataFilter
$total += $result.Count
while ($null -ne $result.NextLink)
    {
        $result = Get-AzEventGridDomain -NextLink $result.NextLink
        $total += $result.Count
    }

Write-Output "Total number of domains is $Total"
```

### Contoh 5

Mencantumkan semua domain Kisi Kejadian di Langganan Azure tanpa paginasi (semua domain dikembalikan dalam satu bidikan)

```powershell
$result=Get-AzEventGridDomain
Write-Output $result.PsDomainsList
```

```output
ResourceGroupName : MyResourceGroupName
DomainName        : Domain1
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/myresourcegroupname1/providers/Microsoft.EventGrid/domains/domain1
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain1.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              : {[Tag1, Value1], [Tag2, Value2]}

ResourceGroupName : MyResourceGroupName
DomainName        : Domain2
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/myresourcegroupname1/providers/Microsoft.EventGrid/domains/domain2
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain2.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              :

ResourceGroupName : MyResourceGroupName
DomainName        : Domain3
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/myresourcegroupname2/providers/Microsoft.EventGrid/domains/domain3
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain3.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              : {[Tag3, Value3], [Tag4, Value4]}

ResourceGroupName : MyResourceGroupName
DomainName        : Domain4
Id                : /subscriptions/<Azure Subscription Id>/resourceGroups/myresourcegroupname3/providers/Microsoft.EventGrid/domains/domain4
Type              : Microsoft.EventGrid/domains
Location          : westus2
Endpoint          : https://domain4.westus2-1.eventgrid.azure.net/api/events
ProvisioningState : Succeeded
Tags              :
```

### Contoh 6

Cantumkan domain Kisi Kejadian (jika ada) di Langganan Azure yang memenuhi kueri $odataFilter 20 domain dalam satu waktu. Jika hasil lainnya tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman domain berikutnya, pengguna diharapkan untuk menghubungi kembali Get-AzEventGridDomain dan menggunakan hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

```powershell
$total = 0
$odataFilter = "Contains(Name, 'ABCD')"
$result = Get-AzEventGridDomain -Top 20 -ODataQuery $odataFilter
$total += $result.Count
while ($null -ne $result.NextLink)
    {
        $result = Get-AzEventGridDomain -NextLink $result.NextLink
        $total += $result.Count
    }
Write-Output "Total number of domains is $Total"
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

### -Nama
Nama domain EventGrid.

```yaml
Type: System.String
Parameter Sets: DomainNameParameterSet
Aliases: DomainName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextLink
Tautan untuk halaman sumber daya berikutnya yang akan diperoleh.
Nilai ini diperoleh dengan panggilan cmdlet pertama Get-AzEventGrid ketika lebih banyak sumber daya masih tersedia untuk dikueri.

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
Kueri OData digunakan untuk memfilter hasil daftar.
Pemfilteran saat ini hanya diperbolehkan pada properti Nama. Operasi yang didukung meliputi: CONTAINS, eq (untuk sama dengan), ne (untuk tidak sama dengan), AND, OR dan NOT.

```yaml
Type: System.String
Parameter Sets: ResourceGroupNameParameterSet, DomainNameParameterSet, ResourceIdEventSubscriptionParameterSet
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
Parameter Sets: DomainNameParameterSet
Aliases: ResourceGroup

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi Sumber Daya yang mewakili Domain Kisi Kejadian.

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
Jumlah sumber daya maksimum yang akan diperoleh.
Nilai valid adalah antara 1 dan 100.
Jika nilai teratas ditentukan dan hasil lainnya masih tersedia, hasilnya akan berisi link ke halaman berikutnya yang akan dikueri di NextLink.
Jika nilai Teratas tidak ditentukan, daftar lengkap sumber daya akan dikembalikan sekaligus.

```yaml
Type: System.Int32
Parameter Sets: ResourceGroupNameParameterSet, DomainNameParameterSet, ResourceIdEventSubscriptionParameterSet
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

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSDomain

### Microsoft.Azure.Commands.EventGrid.Models.PSDomainListInstance

## CATATAN

## RELATED LINKS
