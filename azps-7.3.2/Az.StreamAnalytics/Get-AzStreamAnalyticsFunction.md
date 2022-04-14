---
external help file: ''
Module Name: Az.StreamAnalytics
online version: https://docs.microsoft.com/powershell/module/az.streamanalytics/get-azstreamanalyticsfunction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsFunction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StreamAnalytics/help/Get-AzStreamAnalyticsFunction.md
ms.openlocfilehash: 1726856f7f70ba52ba966d520d071eedecb770dc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142250207"
---
# Get-AzStreamAnalyticsFunction

## SYNOPSIS
Mendapatkan detail tentang fungsi yang ditentukan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.streamanalytics/get-azstreamanalyticsfunction) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzStreamAnalyticsFunction -JobName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-Select <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzStreamAnalyticsFunction -JobName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzStreamAnalyticsFunction -InputObject <IStreamAnalyticsIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail tentang fungsi yang ditentukan.

## EXAMPLES

### Contoh 1: Dapatkan semua fungsi Stream Analytics
```powershell
PS C:\> Get-AzStreamAnalyticsFunction -ResourceGroupName azure-rg-test -JobName sajob-01-pwsh

Name        Type                                              ETag
----        ----                                              ----
function-01 Microsoft.StreamAnalytics/streamingjobs/functions
```

Perintah ini mendapatkan fungsi yang ditentukan pada pekerjaan.

### Contoh 2: Dapatkan fungsi Stream Analytics tertentu
```powershell
PS C:\> Get-AzStreamAnalyticsFunction -ResourceGroupName azure-rg-test -JobName sajob-01-pwsh -Name function-01

Name        Type                                              ETag
----        ----                                              ----
function-01 Microsoft.StreamAnalytics/streamingjobs/functions e35beaf1-8c6c-4b26-bafe-733835510f49
```

Perintah ini mendapatkan informasi tentang fungsi yang ditentukan pada pekerjaan.

### Contoh 3: Mendapatkan fungsi Stream Analytics tertentu menurut pipeline
```powershell
PS C:\> New-AzStreamAnalyticsFunction -ResourceGroupName azure-rg-test -JobName sajob-01-portal -Name function-05 -File .\test\template-json\Function_JavascriptUdf.json | Get-AzStreamAnalyticsFunction

Name        Type                                              ETag
----        ----                                              ----
function-05 Microsoft.StreamAnalytics/streamingjobs/functions e35beaf1-8c6c-4b26-bafe-733835510f49
```

Perintah ini mendapatkan informasi tentang fungsi yang ditentukan pada pekerjaan.

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
Nama fungsi.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: FunctionName

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

### Microsoft.Azure.PowerShell.Cmdlets.StreamAnalytics.Models.Api20170401Preview.IFunction

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
  - `[Location <String>]`: Kawasan tempat untuk mengambil informasi kuota langganan. Anda dapat mengetahui kawasan mana Azure Stream Analytics didukung di sini: https://azure.microsoft.com/en-us/regions/
  - `[OutputName <String>]`: Nama output.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[TransformationName <String>]`: Nama transformasi.

## RELATED LINKS

