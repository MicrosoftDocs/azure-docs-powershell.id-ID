---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.logz/get-azlogzmonitortagrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Get-AzLogzMonitorTagRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Get-AzLogzMonitorTagRule.md
ms.openlocfilehash: f81c6f5f7f66e6763ab747ace1f76f9933e0c967
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145768621"
---
# Get-AzLogzMonitorTagRule

## SYNOPSIS
Dapatkan seperangkat aturan tag untuk sumber daya monitor tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.logz/get-azlogzmonitortagrule) untuk informasi terbaru.

## SYNTAX

### Dapatkan (Default)
```
Get-AzLogzMonitorTagRule -MonitorName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzLogzMonitorTagRule -InputObject <ILogzIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan seperangkat aturan tag untuk sumber daya monitor tertentu.

## EXAMPLES

### Contoh 1: Dapatkan seperangkat aturan tag default untuk sumber daya monitor tertentu
```powershell
Get-AzLogzMonitorTagRule -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04
```

```output
Name    ProvisioningState ResourceGroupName
----    ----------------- -----------------
default Succeeded         logz-rg-test
```

Perintah ini mendapatkan seperangkat aturan tag default untuk sumber daya monitor tertentu.

### Contoh 2: Dapatkan seperangkat aturan tag default untuk sumber daya monitor tertentu menurut alur
```powershell
Get-AzLogzMonitorTagRule -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04 | Get-AzLogzMonitorTagRule
```

```output
Name    ProvisioningState ResourceGroupName
----    ----------------- -----------------
default Succeeded         logz-rg-test
```

Perintah ini mendapatkan seperangkat aturan tag default untuk sumber daya monitor tertentu menurut alur.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.ILogzIdentity
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
Nama ini tidak peka huruf besar/kecil.

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: Get
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

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.ILogzIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.IMonitoringTagRules

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ILogzIdentity>: Parameter Identitas
  - `[ConfigurationName <String>]`: 
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MonitorName <String>]`: Memantau nama sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar/kecil.
  - `[RuleSetName <String>]`: 
  - `[SubAccountName <String>]`: Nama sumber daya Sub Akun
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

