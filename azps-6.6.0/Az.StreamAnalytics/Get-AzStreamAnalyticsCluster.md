---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/get-azstreamanalyticscluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsCluster.md
ms.openlocfilehash: 717179261b18a248064df10c99d7865c3f6d5eaf
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140243449"
---
# Get-AzStreamAnalyticsCluster

## SYNOPSIS
Mendapatkan informasi tentang kluster tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.streamanalytics/get-azstreamanalyticscluster) untuk informasi terkini.

## SYNTAX

### Daftar (Default)
```
Get-AzStreamAnalyticsCluster [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzStreamAnalyticsCluster -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzStreamAnalyticsCluster -InputObject <IStreamAnalyticsIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar1
```
Get-AzStreamAnalyticsCluster -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi tentang kluster tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan semua kluster analitik streaming di bawah langganan
```powershell
PS C:\> Get-AzStreamAnalyticsCluster

Location        Name         Type                               Etag
--------        ----         ----                               ----
West Central US sac-m-test01 Microsoft.StreamAnalytics/clusters 77ba5ccb-3005-40b6-b9ac-3ae9d7fb21c9
```

Perintah ini akan mendapatkan semua kluster analitik streaming di bawah langganan.

### Contoh 2: Mendapatkan semua kluster analitik streaming di bawah grup sumber daya
```powershell
PS C:\> Get-AzStreamAnalyticsCluster -ResourceGroupName pwshaz-rg-test

Location        Name         Type                               Etag
--------        ----         ----                               ----
West Central US sac-m-test01 Microsoft.StreamAnalytics/clusters c2bcffd8-b35d-430b-9759-13af9c18ed72
```

Perintah ini akan mendapatkan semua kluster analitik streaming di bawah grup sumber daya.

### Contoh 3: Dapatkan kluster analitik streaming menurut nama
```powershell
PS C:\> Get-AzStreamAnalyticsCluster -ResourceGroupName pwshaz-rg-test -Name sac-m-test01

Location        Name         Type                               Etag
--------        ----         ----                               ----
West Central US sac-m-test01 Microsoft.StreamAnalytics/clusters c2bcffd8-b35d-430b-9759-13af9c18ed72
```

Perintah ini menghasilkan kluster analitik streaming menurut nama.

### Contoh 4: Dapatkan streaming analitik kluster menurut pipeline
```powershell
PS C:\> Get-AzStreamAnalyticsCluster -ResourceGroupName pwshaz-rg-test -Name sac-m-test01 | Get-AzStreamAnalyticsCluster

Location        Name         Type                               Etag
--------        ----         ----                               ----
West Central US sac-m-test01 Microsoft.StreamAnalytics/clusters c2bcffd8-b35d-430b-9759-13af9c18ed72
```

Perintah ini membuat kluster analitik streaming menurut saluran.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama kluster.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: ClusterName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: Get, List, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20200301Preview.ICluster

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IStreamAnalyticsIdentity>: Parameter Identitas
  - `[ClusterName <String>]`: Nama kluster.
  - `[FunctionName <String>]`: Nama fungsi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InputName <String>]`: Nama input.
  - `[JobName <String>]`: Nama pekerjaan streaming.
  - `[Location <String>]`: Kawasan untuk mengambil informasi kuota langganan. Anda dapat mencari tahu wilayah mana Azure Stream Analytics didukung di sini: https://azure.microsoft.com/en-us/regions/
  - `[OutputName <String>]`: Nama output.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[TransformationName <String>]`: Nama transformasi tersebut.

## RELATED LINKS

