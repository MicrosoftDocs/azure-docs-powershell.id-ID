---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridSystemTopic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridSystemTopic.md
ms.openlocfilehash: 7c01b24da936011d061e9472810d116a14ebcef4
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145522426"
---
# Get-AzEventGridSystemTopic

## SYNOPSIS
Mendapatkan detail topik sistem Event Grid, atau mendapatkan daftar semua topik sistem Event Grid di langganan Azure saat ini.

## SYNTAX

### ResourceGroupNameParameterSet (Default)
```
Get-AzEventGridSystemTopic [-ResourceGroupName <String>] [-ODataQuery <String>] [-Top <Int32>]
 [-NextLink <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SystemTopicNameParameterSet
```
Get-AzEventGridSystemTopic [-ResourceGroupName <String>] [-Name <String>] [-ODataQuery <String>] [-Top <Int32>]
 [-NextLink <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzEventGridSystemTopic mendapatkan detail Topik Sistem Event Grid tertentu, atau daftar semua topik Event Grid di langganan Azure saat ini.
Jika nama topik disediakan, detail satu Topik Event Grid dikembalikan.
Jika nama topik tidak disediakan, daftar topik dikembalikan. Jumlah elemen yang dikembalikan dalam daftar ini dikontrol oleh parameter Teratas. Jika nilai Teratas tidak ditentukan atau $null, daftar akan berisi semua item topik. Jika tidak, Top akan menunjukkan jumlah maksimum elemen yang akan dikembalikan dalam daftar.
Jika lebih banyak topik masih tersedia, nilai di NextLink harus digunakan dalam panggilan berikutnya untuk mendapatkan halaman topik berikutnya.
Terakhir, parameter ODataQuery digunakan untuk melakukan pemfilteran untuk hasil pencarian. Kueri pemfilteran mengikuti sintaks OData menggunakan properti Nama saja. Operasi yang didukung meliputi: CONTAINS, eq (untuk equal), ne (untuk not equal), AND, OR dan NOT.

## EXAMPLES

### Contoh 1
```powershell
Get-AzEventGridSystemTopic -ResourceGroup MyResourceGroupName -Name Topic1
```

Mendapatkan detail topik \`Sistem Event Grid Topic1\` dalam grup \`sumber daya MyResourceGroupName\`.

### Contoh 2
```powershell
Get-AzEventGridSystemTopic -ResourceGroup MyResourceGroupName
```

Cantumkan semua topik Sistem Event Grid dalam grup \`sumber daya MyResourceGroupName\` tanpa penomoran halaman.

### Contoh: 3
```powershell
$odataFilter = "Name ne 'ABCD'"
$result = Get-AzEventGridSystemTopic -ResourceGroup MyResourceGroupName -Top 10 -ODataQuery $odataFilter
Get-AzEventGridSystemTopic $result.NextLink
```

Cantumkan 10 topik Sistem Event Grid pertama (jika ada) dalam grup \`sumber daya MyResourceGroupName\` yang memenuhi kueri $odataFilter. Jika lebih banyak hasil tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman topik berikutnya, pengguna diharapkan untuk memanggil kembali Get-AzEventGridSystemTopic dan menggunakan hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

### Contoh 4
```powershell
Get-AzEventGridSystemTopic
```

Cantumkan semua topik Event Grid dalam langganan tanpa penomoran halaman.

### Contoh 5
```powershell
$odataFilter = "Name ne 'ABCD'"
$result = Get-AzEventGridSystemTopic -Top 10 -ODataQuery $odataFilter
Get-AzEventGridSystemTopic $result.NextLink
```

Cantumkan 10 topik Sistem Event Grid pertama (jika ada) dalam langganan yang memenuhi kueri $odataFilter. Jika lebih banyak hasil tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman topik berikutnya, pengguna diharapkan untuk memanggil kembali Get-AzEventGridSystemTopic dan menggunakan hasil. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

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

### -Name
Nama topik EventGrid.

```yaml
Type: System.String
Parameter Sets: SystemTopicNameParameterSet
Aliases: SystemTopicName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextLink
Tautan untuk halaman sumber daya berikutnya yang akan diperoleh.
Nilai ini diperoleh dengan panggilan cmdlet Get-AzEventGrid pertama ketika lebih banyak sumber daya masih tersedia untuk dikueri.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ODataQuery
Kueri OData yang digunakan untuk memfilter hasil daftar.
Pemfilteran saat ini hanya diperbolehkan pada properti Nama. Operasi yang didukung meliputi: CONTAINS, eq (untuk equal), ne (untuk not equal), AND, OR dan NOT.

```yaml
Type: System.String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: ResourceGroup

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Atas
Jumlah maksimum sumber daya yang akan diperoleh.
Nilai yang valid adalah antara 1 dan 100.
Jika nilai teratas ditentukan dan lebih banyak hasil masih tersedia, hasilnya akan berisi tautan ke halaman berikutnya yang akan dikueri di NextLink.
Jika nilai Teratas tidak ditentukan, daftar lengkap sumber daya akan dikembalikan sekaligus.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSSystemTopic

### Microsoft.Azure.Commands.EventGrid.Models.PSSytemTopicListInstance

## NOTES

## RELATED LINKS
