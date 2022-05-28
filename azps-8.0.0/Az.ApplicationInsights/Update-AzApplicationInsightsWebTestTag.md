---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.applicationinsights/update-azapplicationinsightswebtesttag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/help/Update-AzApplicationInsightsWebTestTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/help/Update-AzApplicationInsightsWebTestTag.md
ms.openlocfilehash: c33ed7e9ef98874e17193dc138a09975262c8723
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145545466"
---
# Update-AzApplicationInsightsWebTestTag

## SYNOPSIS
Membuat atau memperbarui definisi pengujian web Application Insights.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzApplicationInsightsWebTestTag -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzApplicationInsightsWebTestTag -InputObject <IApplicationInsightsIdentity> [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui definisi pengujian web Application Insights.

## EXAMPLES

### Contoh 1: Memperbarui tautan Insights Aplikasi dari pengujian Web
```powershell
Update-AzApplicationInsightsWebTestTag -ResourceGroupName azpwsh-rg-test -Name webtest01-lucasappinsights -Tag @{"hidden-link:/subscriptions/xxxxxxxxxx-xxxxx-xxxx-xxxxxxxxxxxx/resourceGroups/azpwsh-rg-test/providers/microsoft.insights/components/lucasappinsights" = "Resource"}
```

```output
Location Name                       WebTestKind   ResourceGroupName   Enabled
-------- ----                       -----------   -----------------   -------
westus2  webtest01-lucasappinsights standard      azpwsh-rg-test      True
```

Perintah ini memperbarui tautan Insights Aplikasi dari pengujian Web.

### Contoh 2: Memperbarui tautan Insights Aplikasi dari pengujian Web menurut alur
```powershell
Get-AzApplicationInsightsWebTest -ResourceGroupName azpwsh-rg-test -WebTestName webtest01-lucasappinsights | Update-AzApplicationInsightsWebTestTag -Tag @{"hidden-link:/subscriptions/xxxxxxxxxx-xxxxx-xxxx-xxxxxxxxxxxx/resourceGroups/azpwsh-rg-test/providers/microsoft.insights/components/appinsightsportal01" = "Resource"}
```

```output
Location Name                       WebTestKind   ResourceGroupName     Enabled
-------- ----                       -----------   -----------------     -------
westus2  webtest01-lucasappinsights standard      azpwsh-rg-test        True
```

Perintah ini memperbarui tautan Application Insights pengujian Web menurut alur.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.IApplicationInsightsIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama sumber daya Application Insights WebTest.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

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
Parameter Sets: UpdateExpanded
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
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.IWebTest

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

