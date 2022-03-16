---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/get-azstreamanalyticsoutput
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsOutput.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsOutput.md
ms.openlocfilehash: 5944be4e80d4882461575e5ad69494abfd132d12
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139947824"
---
# Get-AzStreamAnalyticsOutput

## SYNOPSIS
Mendapatkan detail tentang output tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.streamanalytics/get-azstreamanalyticsoutput) untuk informasi terkini.

## SYNTAX

### Daftar (Default)
```
Get-AzStreamAnalyticsOutput -JobName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-Select <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzStreamAnalyticsOutput -JobName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzStreamAnalyticsOutput -InputObject <IStreamAnalyticsIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail tentang output tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan informasi tentang output pekerjaan
```powershell
PS C:\> Get-AzStreamAnalyticsOutput -ResourceGroupName azure-rg-test -JobName sajob-02-pwsh

Name      Type                                            ETag
----      ----                                            ----
output-01 Microsoft.StreamAnalytics/streamingjobs/outputs
```

Perintah ini mengembalikan informasi tentang output yang ditentukan pada pekerjaan.

### Contoh 2: Mendapatkan informasi tentang output pekerjaan tertentu
```powershell
PS C:\> Get-AzStreamAnalyticsOutput -ResourceGroupName azure-rg-test -JobName sajob-02-pwsh -Name output-01

Name      Type                                            ETag
----      ----                                            ----
output-01 Microsoft.StreamAnalytics/streamingjobs/outputs 3819fb65-07f5-4dc3-83e1-d3149596f8d0
```

Perintah ini mengembalikan informasi tentang output yang ditentukan pada pekerjaan.

### Contoh 3: Mendapatkan informasi tentang output pekerjaan tertentu menurut pipeline
```powershell
PS C:\>New-AzStreamAnalyticsOutput -ResourceGroupName azure-rg-test -JobName sajob-01-portal -Name output-05 -File .\test\template-json\StroageAccount.json | Get-AzStreamAnalyticsOutput

Name      Type                                            ETag
----      ----                                            ----
output-05 Microsoft.StreamAnalytics/streamingjobs/outputs 3a11e210-2a7f-4856-8d5a-25d4ecabee06
```

Perintah ini mengembalikan informasi tentang output yang ditentukan pada pekerjaan.

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

### -JobName
Nama pekerjaan streaming.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama output.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: OutputName

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
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pilih
Parameter $select OData.
Daftar ini merupakan daftar properti struktural yang dipisahkan tanda koma untuk disertakan dalam respons, atau "*" untuk menyertakan semua properti. Secara default, semua properti akan dikembalikan kecuali diagnostik. Saat ini hanya menerima '*' sebagai nilai yang valid.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: Get, List
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

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IOutput

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

