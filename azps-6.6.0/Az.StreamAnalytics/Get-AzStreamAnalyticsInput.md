---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/get-azstreamanalyticsinput
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsInput.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsInput.md
ms.openlocfilehash: f3d4499d1d42ea6e9ccca9afafd8a50289fce1bc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142960427"
---
# Get-AzStreamAnalyticsInput

## SYNOPSIS
Mendapatkan detail tentang input yang ditentukan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.streamanalytics/get-azstreamanalyticsinput) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzStreamAnalyticsInput -JobName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-Select <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzStreamAnalyticsInput -JobName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzStreamAnalyticsInput -InputObject <IStreamAnalyticsIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail tentang input yang ditentukan.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang input yang ditentukan pada pekerjaan
```powershell
PS C:\> Get-AzStreamAnalyticsInput -ResourceGroupName azure-rg-test -JobName sajob-01-pwsh

Name     Type                                           ETag
----     ----                                           ----
input-01 Microsoft.StreamAnalytics/streamingjobs/inputs
```

Perintah ini mengembalikan informasi tentang semua input yang ditentukan pada pekerjaan StreamingJob.

### Contoh 2: Mendapatkan informasi tentang input tertentu yang ditentukan pada pekerjaan
```powershell
PS C:\> Get-AzStreamAnalyticsInput -ResourceGroupName azure-rg-test -JobName sajob-01-pwsh -Name input-01

Name     Type                                           ETag
----     ----                                           ----
input-01 Microsoft.StreamAnalytics/streamingjobs/inputs c3e34ed5-4f82-482e-a4a4-25520ca89098
```

Perintah ini mengembalikan informasi tentang input bernama EntryStream yang ditentukan pada pekerjaan StreamingJob.

### Contoh 3: Mendapatkan informasi tentang input tertentu yang ditentukan pada pekerjaan menurut pipeline
```powershell
PS C:\> New-AzStreamAnalyticsInput -ResourceGroupName azure-rg-test -JobName sajob-01-portal -Name input-05 -File .\test\template-json\IotHub.json | Get-AzStreamAnalyticsInput

Name     Type                                           ETag
----     ----                                           ----
input-05 Microsoft.StreamAnalytics/streamingjobs/inputs abb81160-d9e1-4729-9b3a-5af04bd880c6
```

Perintah ini mengembalikan informasi tentang input bernama EntryStream yang ditentukan pada pekerjaan StreamingJob.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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
Nama input.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: InputName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

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
Parameter kueri OData $select.
Ini adalah daftar properti struktural yang dipisahkan koma untuk disertakan dalam respons, atau "*" untuk menyertakan semua properti. Secara default, semua properti dikembalikan kecuali diagnostik. Saat ini hanya menerima '*' sebagai nilai yang valid.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.IStreamAnalyticsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IInput

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IStreamAnalyticsIdentity>: Parameter Identitas
  - `[ClusterName <String>]`: Nama kluster.
  - `[FunctionName <String>]`: Nama fungsi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InputName <String>]`: Nama input.
  - `[JobName <String>]`: Nama pekerjaan streaming.
  - `[Location <String>]`: Kawasan tempat untuk mengambil informasi kuota langganan. Anda dapat mengetahui kawasan mana Azure Stream Analytics didukung di sini: https://azure.microsoft.com/en-us/regions/
  - `[OutputName <String>]`: Nama output.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[TransformationName <String>]`: Nama transformasi.

## RELATED LINKS

