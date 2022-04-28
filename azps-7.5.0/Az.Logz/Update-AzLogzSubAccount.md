---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.logz/update-azlogzsubaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Update-AzLogzSubAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Update-AzLogzSubAccount.md
ms.openlocfilehash: 465e18448640da50a0a35347d496f4a9b0646e40
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144192928"
---
# Update-AzLogzSubAccount

## SYNOPSIS
Memperbarui sumber daya monitor.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzLogzSubAccount -MonitorName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-MonitoringStatus <MonitoringStatus>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzLogzSubAccount -InputObject <ILogzIdentity> [-MonitoringStatus <MonitoringStatus>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui sumber daya monitor.

## EXAMPLES

### Contoh 1: Memperbarui sumber daya sub akun logz
```powershell
Update-AzLogzSubAccount -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04 -Name logz-pwshsub01 -Tag @{'key01'=1;'key02'=2;'key03'=3}
```

```output
Name           MonitoringStatus Location ResourceGroupName
----           ---------------- -------- -----------------
logz-pwshsub01 Enabled          westus2  logz-rg-test
```

Perintah ini memperbarui sumber daya sub akun logz.

### Contoh 2: Memperbarui sumber daya sub akun logz menurut alur
```powershell
Get-AzLogzSubAccount -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04 -Name logz-pwshsub01 | Update-AzLogzSubAccount -Tag @{'key01'=1;'key02'=2;'key03'=3}
```

```output
Name           MonitoringStatus Location ResourceGroupName
----           ---------------- -------- -----------------
logz-pwshsub01 Enabled          westus2  logz-rg-test
```

Perintah ini memperbarui sumber daya sub akun logz menurut alur.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.ILogzIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MonitoringStatus
Bendera yang menentukan apakah pemantauan sumber daya diaktifkan atau dinonaktifkan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Logz.Support.MonitoringStatus
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitorName
Memantau nama sumber daya

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

### -Name
Nama sumber daya Sub Akun

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: SubAccountName

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
Tag baru sumber daya monitor.

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

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.ILogzIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.ILogzMonitorResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ILogzIdentity>: Parameter Identitas
  - `[ConfigurationName <String>]`: 
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MonitorName <String>]`: Memantau nama sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[RuleSetName <String>]`: 
  - `[SubAccountName <String>]`: Nama sumber daya Sub Akun
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

