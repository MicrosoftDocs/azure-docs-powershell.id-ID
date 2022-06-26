---
external help file: ''
Module Name: Az.Datadog
online version: https://docs.microsoft.com/powershell/module/az.datadog/update-azdatadogmonitorsetpasswordlink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Update-AzDatadogMonitorSetPasswordLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Update-AzDatadogMonitorSetPasswordLink.md
ms.openlocfilehash: 970e74905429b9430920dac1537150ae671f65e5
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146604281"
---
# Update-AzDatadogMonitorSetPasswordLink

## SYNOPSIS
Refresh tautan atur kata sandi dan kembalikan yang terbaru.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datadog/update-azdatadogmonitorsetpasswordlink) untuk informasi terbaru.

## SYNTAX

### Refresh (Default)
```
Update-AzDatadogMonitorSetPasswordLink -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### RefreshViaIdentity
```
Update-AzDatadogMonitorSetPasswordLink -InputObject <IDatadogIdentity> [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Refresh tautan atur kata sandi dan kembalikan yang terbaru.

## EXAMPLES

### Contoh 1: Refresh tautan set kata sandi dan kembalikan yang terbaru
```powershell
Update-AzDatadogMonitorSetPasswordLink -ResourceGroupName azure-rg-Datadog -Name Datadog
```

```output
https://us3.Datadoghq.com/account/reset_password/xxxxxxxxxxxxxxxxxxxxxxxxxxx
```

Perintah ini me-refresh tautan atur kata sandi dan mengembalikan yang terbaru.

### Contoh 2: Refresh tautan set kata sandi dan kembalikan yang terbaru menurut alur
```powershell
Get-AzDatadogMonitor -ResourceGroupName azure-rg-Datadog -Name Datadog | Update-AzDatadogMonitorSetPasswordLink
```

```output
https://us3.Datadoghq.com/account/reset_password/xxxxxxxxxxxxxxxxxxxxxxxxxxx
```

Perintah ini merefresh tautan atur kata sandi dan mengembalikan yang terbaru menurut alur.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.IDatadogIdentity
Parameter Sets: RefreshViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Memantau nama sumber daya

```yaml
Type: System.String
Parameter Sets: Refresh
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
Parameter Sets: Refresh
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
Parameter Sets: Refresh
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

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.IDatadogIdentity

## OUTPUTS

### System.String

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

