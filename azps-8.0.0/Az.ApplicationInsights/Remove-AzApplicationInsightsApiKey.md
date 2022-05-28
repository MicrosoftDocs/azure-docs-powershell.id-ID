---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.applicationinsights/remove-azapplicationinsightsapikey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/help/Remove-AzApplicationInsightsApiKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/help/Remove-AzApplicationInsightsApiKey.md
ms.openlocfilehash: e2ae739659f0a2b80ea321b5c67b701b80e3f5c8
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145562756"
---
# Remove-AzApplicationInsightsApiKey

## SYNOPSIS
Menghapus Kunci API komponen Insights Aplikasi.

## SYNTAX

### Hapus (Default)
```
Remove-AzApplicationInsightsApiKey -ApiKeyId <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzApplicationInsightsApiKey -InputObject <IApplicationInsightsIdentity> [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus Kunci API komponen Insights Aplikasi.

## EXAMPLES

### Contoh 1: Menghapus kunci api application insights untuk sumber daya application insights
```powershell
Remove-AzApplicationInsightsApiKey -ResourceGroupName "testGroup" -Name "test" -ApiKeyId dd173f38-4fd1-4c75-8af5-99c29aa0f867 -PassThru
```

Menghapus kunci api application insights untuk sumber daya application insights

## PARAMETERS

### -ApiKeyId
ID Kunci API.
Ini unik dalam komponen Insights Aplikasi.

```yaml
Type: System.String
Parameter Sets: Delete
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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.IApplicationInsightsIdentity
Parameter Sets: DeleteViaIdentity
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
Parameter Sets: Delete
Aliases: ApplicationInsightsComponentName, ComponentName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: Delete
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
Type: System.String
Parameter Sets: Delete
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
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


INPUTOBJECT <IApplicationInsightsIdentity>: Parameter Identitas
  - `[AnnotationId <String>]`: ID anotasi unik. Ini unik dalam komponen Insights Aplikasi.
  - `[ComponentName <String>]`: Nama sumber daya komponen Insights Aplikasi.
  - `[ExportId <String>]`: ID konfigurasi Ekspor Berkelanjutan. Ini unik dalam komponen Insights Aplikasi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[KeyId <String>]`: ID Kunci API. Ini unik dalam komponen Insights Aplikasi.
  - `[PurgeId <String>]`: Dalam permintaan status penghapusan menyeluruh, ini adalah Id operasi yang statusnya dikembalikan.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar/kecil.
  - `[ResourceName <String>]`: Nama sumber daya komponen Insights Aplikasi.
  - `[StorageType <StorageType?>]`: Jenis sumber data komponen Application Insights untuk akun penyimpanan yang ditautkan.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[WebTestName <String>]`: Nama sumber daya WebTest Insights Aplikasi.

## RELATED LINKS

