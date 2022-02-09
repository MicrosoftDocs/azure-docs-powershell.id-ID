---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.logz/new-azlogzmonitortagrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/New-AzLogzMonitorTagRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/New-AzLogzMonitorTagRule.md
ms.openlocfilehash: fee473bebd86698e48d79b437e974b6c64d4ecc0
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138307836"
---
# New-AzLogzMonitorTagRule

## SYNOPSIS
Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu.

## SYNTAX

```
New-AzLogzMonitorTagRule -MonitorName <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-LogRuleFilteringTag <IFilteringTag[]>] [-LogRuleSendAadLog] [-LogRuleSendActivityLog]
 [-LogRuleSendSubscriptionLog] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu
```powershell
PS C:\> New-AzLogzMonitorTagRule -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04

Name    ProvisioningState ResourceGroupName
----    ----------------- -----------------
default Succeeded         logz-rg-test
```

Perintah ini membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu.

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

### -LogRuleFilteringTag
Daftar tag pemfilteran yang akan digunakan untuk merekam log.
Hal ini hanya berlaku jika bendera SendActivityLogs diaktifkan.
Jika kosong, semua sumber daya akan diambil.
Jika hanya tindakan Kecualikan yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia.
Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
Untuk membuat, lihat bagian CATATAN untuk properti LOGRULEFILTERINGTAG dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.IFilteringTag[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogRuleSendAadLog
Bendera menentukan apakah AAD log harus dikirim untuk sumber daya Monitor.

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

### -LogRuleSendActivityLog
Bendera yang menentukan apakah log aktivitas dari Sumber Daya Azure harus dikirim untuk sumber daya Monitor.

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

### -LogRuleSendSubscriptionLog
Bendera menentukan apakah log langganan harus dikirim untuk sumber daya Monitor.

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

### -MonitorName
Memantau nama sumber daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.IMonitoringTagRules

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LOGRULEFILTERINGTAG <IFilteringTag[]>: Daftar tag pemfilteran yang akan digunakan untuk merekam log. Hal ini hanya berlaku jika bendera SendActivityLogs diaktifkan. Jika kosong, semua sumber daya akan diambil. Jika hanya tindakan Kecualikan yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia. Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
  - `[Action <TagAction?>]`: Tindakan yang valid untuk tag pemfilteran. Pengecualian akan diprioritaskan atas pencakusan.
  - `[Name <String>]`: Nama (juga dikenal sebagai kunci) tag.
  - `[Value <String>]`: Nilai tag.

## RELATED LINKS

