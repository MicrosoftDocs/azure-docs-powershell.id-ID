---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridSystemTopicEventSubscription.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridSystemTopicEventSubscription.md
ms.openlocfilehash: bbadfaae7f7f8d78fd58ec1f9abc7fee45ef376e
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145516303"
---
# Get-AzEventGridSystemTopicEventSubscription

## SYNOPSIS
Mendapatkan detail langganan peristiwa, atau mendapatkan daftar semua langganan peristiwa untuk topik sistem Azure Eventgrid tertentu.

## SYNTAX

### TopicNameParameterSet (Default)
```
Get-AzEventGridSystemTopicEventSubscription [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SystemTopicEventSuscriptionParameterSet
```
Get-AzEventGridSystemTopicEventSubscription [-EventSubscriptionName <String>] -ResourceGroupName <String>
 -SystemTopicName <String> [-IncludeFullEndpointUrl] [-ODataQuery <String>] [-Top <Int32>] [-NextLink <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzEventGridSystemTopicEventSubscription mendapatkan detail langganan topik sytem Event Grid tertentu, atau daftar semua langganan topik sytem Event Grid untuk topik sistem Azure Eventgrid tertentu.

## EXAMPLES

### Contoh 1
```powershell
Get-AzEventGridSystemTopicEventSubscription -ResourceGroupName MyResourceGroupName -SystemTopicName Topic1 -EventSubscriptionName EventSubscription1
```

Mendapatkan detail langganan \`peristiwa EventSubscription1\` yang dibuat untuk topik \`sistem Topic1\` dalam grup \`sumber daya MyResourceGroupName\`.

### Contoh 2
```powershell
Get-AzEventGridSystemTopicEventSubscription -ResourceGroupName MyResourceGroupName -SystemTopicName Topic1 -EventSubscriptionName EventSubscription1 -IncludeFullEndpointUrl
```

Mendapatkan detail langganan \`peristiwa EventSubscription1\` yang dibuat untuk topik \`sistem Topic1\` di grup \`sumber daya MyResourceGroupName\`, termasuk URL titik akhir lengkap jika merupakan langganan peristiwa berbasis webhook.

### Contoh: 3
```powershell
Get-AzEventGridSystemTopicEventSubscription -ResourceGroupName MyResourceGroupName -SystemTopicName Topic1
```

Dapatkan daftar semua langganan peristiwa yang dibuat untuk topik \`sistem Topic1\` di grup \`sumber daya MyResourceGroupName\` tanpa penomoran halaman.

### Contoh 4
```powershell
$odataFilter = "Name ne 'ABCD'"
Get-AzEventGridSystemTopicEventSubscription -ResourceGroupName MyResourceGroupName -TopicName Topic1 -Top 10 -ODataQuery $odataFilter
Get-AzEventGridSystemTopicEventSubscription -ResourceGroupName MyResourceGroupName -TopicName Topic1 $result.NextLink
```

Cantumkan 10 langganan peristiwa pertama (jika ada) yang dibuat untuk topik \`sistem Topic1\` dalam grup \`sumber daya MyResourceGroupName\` yang memenuhi kueri $odataFilter. Jika lebih banyak hasil tersedia, $result. NextLink tidak akan $null. Untuk mendapatkan halaman langganan peristiwa berikutnya, pengguna diharapkan untuk memanggil kembali Get-AzEventGridSystemTopicEventSubscription dan menggunakan hasilnya. NextLink diperoleh dari panggilan sebelumnya. Penelepon harus berhenti ketika hasil. NextLink menjadi $null.

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

### -EventSubscriptionName
Nama langganan peristiwa EventGrid.

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

### -IncludeFullEndpointUrl
Jika ditentukan, sertakan URL titik akhir lengkap tujuan langganan peristiwa dalam respons.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SystemTopicEventSuscriptionParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextLink
Tautan untuk halaman sumber daya berikutnya yang akan diperoleh.
Nilai ini diperoleh dengan panggilan cmdlet Get-AzEventGrid pertama ketika lebih banyak sumber daya masih tersedia untuk dikueri.

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

### -ODataQuery
Kueri OData yang digunakan untuk memfilter hasil daftar.
Pemfilteran saat ini hanya diperbolehkan pada properti Nama. Operasi yang didukung meliputi: CONTAINS, eq (untuk equal), ne (untuk not equal), AND, OR dan NOT.

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

### -Atas
Jumlah maksimum sumber daya yang akan diperoleh.
Nilai yang valid adalah antara 1 dan 100.
Jika nilai teratas ditentukan dan lebih banyak hasil masih tersedia, hasilnya akan berisi tautan ke halaman berikutnya untuk dikueri di NextLink.
Jika nilai Teratas tidak ditentukan, daftar lengkap sumber daya akan dikembalikan sekaligus.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: SystemTopicEventSuscriptionParameterSet
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

### Microsoft.Azure.Commands.EventGrid.Models.PSEventSubscription

### Microsoft.Azure.Commands.EventGrid.Models.PSEventSubscriptionListInstance

## NOTES

## RELATED LINKS
