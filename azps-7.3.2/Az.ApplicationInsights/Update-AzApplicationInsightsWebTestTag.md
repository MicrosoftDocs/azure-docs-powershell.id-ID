---
external help file: ''
Module Name: Az.ApplicationInsights
online version: https://docs.microsoft.com/powershell/module/az.applicationinsights/update-azapplicationinsightswebtesttag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/Update-AzApplicationInsightsWebTestTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApplicationInsights/ApplicationInsights/help/Update-AzApplicationInsightsWebTestTag.md
ms.openlocfilehash: ef24aaf2c989c6a2ba05dbccbaf0e00a291a9dbd
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142219519"
---
# Update-AzApplicationInsightsWebTestTag

## SYNOPSIS
Membuat atau memperbarui definisi uji web Insights Aplikasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.applicationinsights/update-azapplicationinsightswebtesttag) untuk informasi terbaru.

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
Membuat atau memperbarui definisi uji web Insights Aplikasi.

## EXAMPLES

### Contoh 1: Tautan Insights Aplikasi Pembaruan dari uji Web
```powershell
Update-AzApplicationInsightsWebTestTag -ResourceGroupName azpwsh-rg-test -Name webtest01-lucasappinsights -Tag @{"hidden-link:/subscriptions/xxxxxxxxxx-xxxxx-xxxx-xxxxxxxxxxxx/resourceGroups/azpwsh-rg-test/providers/microsoft.insights/components/lucasappinsights" = "Resource"}
```
```output
Location Name                       WebTestKind   ResourceGroupName   Enabled
-------- ----                       -----------   -----------------   -------
westus2  webtest01-lucasappinsights standard      azpwsh-rg-test      True
```

Perintah ini memperbarui tautan Aplikasi Insights uji Web.

### Contoh 2: Update Application Insights link dari uji Web menurut pipeline
```powershell
Get-AzApplicationInsightsWebTest -ResourceGroupName azpwsh-rg-test -WebTestName webtest01-lucasappinsights | Update-AzApplicationInsightsWebTestTag -Tag @{"hidden-link:/subscriptions/xxxxxxxxxx-xxxxx-xxxx-xxxxxxxxxxxx/resourceGroups/azpwsh-rg-test/providers/microsoft.insights/components/appinsightsportal01" = "Resource"}
```
```output
Location Name                       WebTestKind   ResourceGroupName     Enabled
-------- ----                       -----------   -----------------     -------
westus2  webtest01-lucasappinsights standard      azpwsh-rg-test        True
```

Perintah ini memperbarui aplikasi Insights tautan uji web menurut saluran.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.IApplicationInsightsIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya Aplikasi Insights WebTest.

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
Nama ini tidak peka huruf besar kecil.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.IApplicationInsightsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ApplicationInsights.Models.Api20180501Preview.IWebTest

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IApplicationInsightsIdentity>: Parameter Identitas
  - `[ComponentName <String>]`: Nama sumber daya komponen Insights Aplikasi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[WebTestName <String>]`: Nama sumber daya Aplikasi Insights WebTest.

## RELATED LINKS

