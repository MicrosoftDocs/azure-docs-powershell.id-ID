---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.applicationinsights/get-azapplicationinsightsapikey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/help/Get-AzApplicationInsightsApiKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/help/Get-AzApplicationInsightsApiKey.md
ms.openlocfilehash: 66cdd4a7f41b267e0ebd92b1f883f860a24bc53d
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146633098"
---
# Get-AzApplicationInsightsApiKey

## SYNOPSIS
Dapatkan Kunci API untuk id kunci ini.

## SYNTAX

### Daftar (Default)
```
Get-AzApplicationInsightsApiKey -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzApplicationInsightsApiKey -ApiKeyId <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzApplicationInsightsApiKey -InputObject <IApplicationInsightsIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan Kunci API untuk id kunci ini.

## EXAMPLES

### Contoh 1: Dapatkan Kunci Api untuk sumber daya wawasan aplikasi
```powershell
Get-AzApplicationInsightsApiKey -ResourceGroupName "testGroup" -Name "test"
```

Mendapatkan Kunci Api untuk sumber daya application insights

### Contoh 2: Mendapatkan kunci API tertentu untuk sumber daya wawasan aplikasi
```powershell
Get-AzApplicationInsightsApiKey -ResourceGroupName "testGroup" -Name "test" -ApiKeyId 7c4c61dc-b392-4aa4-992f-ee92b84e5dee
```

Mendapatkan kunci API tertentu untuk sumber daya application insights

## PARAMETERS

### -ApiKeyId
ID Kunci API.
Ini unik dalam komponen Insights Aplikasi.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.IApplicationInsightsIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama sumber daya komponen Insights Aplikasi.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases: ApplicationInsightsComponentName, ComponentName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.IApplicationInsightsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20150501.IApplicationInsightsComponentApiKey

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IApplicationInsightsIdentity>`: Parameter Identitas
  - `[AnnotationId <String>]`: ID anotasi unik. Ini unik dalam komponen Insights Aplikasi.
  - `[ComponentName <String>]`: Nama sumber daya komponen Insights Aplikasi.
  - `[ExportId <String>]`: ID konfigurasi Ekspor Berkelanjutan. Ini unik dalam komponen Insights Aplikasi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[KeyId <String>]`: ID Kunci API. Ini unik dalam komponen Insights Aplikasi.
  - `[PurgeId <String>]`: Dalam permintaan status penghapusan menyeluruh, ini adalah Id operasi yang statusnya dikembalikan.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[ResourceName <String>]`: Nama sumber daya komponen Insights Aplikasi.
  - `[StorageType <StorageType?>]`: Jenis sumber data komponen Application Insights untuk akun penyimpanan yang ditautkan.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[WebTestName <String>]`: Nama sumber daya WebTest Insights Aplikasi.

## RELATED LINKS

