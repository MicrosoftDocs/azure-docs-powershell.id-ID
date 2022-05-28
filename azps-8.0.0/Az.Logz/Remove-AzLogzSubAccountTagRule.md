---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.logz/remove-azlogzsubaccounttagrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Remove-AzLogzSubAccountTagRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Remove-AzLogzSubAccountTagRule.md
ms.openlocfilehash: adaca27edb987bf78073047a6104142c82c52848
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145501140"
---
# Remove-AzLogzSubAccountTagRule

## SYNOPSIS
Menghapus seperangkat aturan tag untuk sumber daya monitor tertentu.

## SYNTAX

### Hapus (Default)
```
Remove-AzLogzSubAccountTagRule -MonitorName <String> -ResourceGroupName <String> -SubAccountName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzLogzSubAccountTagRule -InputObject <ILogzIdentity> [-DefaultProfile <PSObject>] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus seperangkat aturan tag untuk sumber daya monitor tertentu.

## EXAMPLES

### Contoh 1: Menghapus seperangkat aturan tag untuk sumber daya sub akun logz tertentu
```powershell
Remove-AzLogzSubAccountTagRule -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04 -SubAccountName logz-pwshsub01
```

Perintah ini menghapus seperangkat aturan tag untuk sumber daya sub akun logz tertentu.

### Contoh 2: Menghapus seperangkat aturan tag untuk sumber daya sub akun logz tertentu menurut alur
```powershell
Get-AzLogzSubAccountTagRule -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04 -SubAccountName logz-pwshsub01 | Remove-AzLogzSubAccountTagRule
```

Perintah ini menghapus seperangkat aturan tag untuk sumber daya sub akun logz tertentu menurut alur.

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
Parameter Sets: DeleteViaIdentity
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
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
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

### -SubAccountName
Nama sumber daya Sub Akun

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

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.ILogzIdentity

## OUTPUTS

### System.Boolean

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

