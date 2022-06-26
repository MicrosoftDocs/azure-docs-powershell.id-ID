---
external help file: ''
Module Name: Az.Datadog
online version: https://docs.microsoft.com/powershell/module/az.datadog/get-azdatadogtagrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Get-AzDatadogTagRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Get-AzDatadogTagRule.md
ms.openlocfilehash: 4ca90f272562e06026347ff5358e1f0db650489f
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146638283"
---
# Get-AzDatadogTagRule

## SYNOPSIS
Dapatkan seperangkat aturan tag untuk sumber daya monitor tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datadog/get-azdatadogtagrule) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzDatadogTagRule -MonitorName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzDatadogTagRule -MonitorName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDatadogTagRule -InputObject <IDatadogIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan seperangkat aturan tag untuk sumber daya monitor tertentu.

## EXAMPLES

### Contoh 1: Mencantumkan semua aturan tag yang ditetapkan untuk sumber daya monitor tertentu
```powershell
Get-AzDatadogTagRule -ResourceGroupName azure-rg-Datadog -MonitorName Datadog
```

```output
Name    Type
----    ----
default microsoft.Datadog/monitors/tagrules
```

Perintah ini mencantumkan semua aturan tag yang ditetapkan untuk sumber daya monitor tertentu.

### Contoh 2: Mendapatkan seperangkat aturan tag untuk sumber daya monitor tertentu
```powershell
Get-AzDatadogTagRule -ResourceGroupName azure-rg-Datadog -MonitorName Datadog -Name 'default'
```

```output
Name    Type
----    ----
default microsoft.Datadog/monitors/tagrules
```

Perintah ini mendapatkan seperangkat aturan tag untuk sumber daya monitor tertentu.

### Contoh 3: Mendapatkan seperangkat aturan tag untuk sumber daya monitor tertentu menurut alur
```powershell
Get-AzDatadogTagRule -ResourceGroupName azure-rg-Datadog -MonitorName Datadog -Name 'default' | Get-AzDatadogTagRule
```

```output
Name    Type
----    ----
default microsoft.Datadog/monitors/tagrules
```

Perintah ini mendapatkan seperangkat aturan tag untuk sumber daya monitor tertentu menurut alur.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.IDatadogIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MonitorName
Memantau nama sumber daya

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

### -Name
Nama seperangkat aturan

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

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.IDatadogIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.Api20210301.IMonitoringTagRules

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IDatadogIdentity>`: Parameter Identitas
  - `[ConfigurationName <String>]`: Nama konfigurasi
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MonitorName <String>]`: Memantau nama sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[RuleSetName <String>]`: Nama seperangkat aturan
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

