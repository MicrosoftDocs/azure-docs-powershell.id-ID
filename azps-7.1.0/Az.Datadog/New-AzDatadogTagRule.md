---
external help file: ''
Module Name: Az.Datadog
online version: https://docs.microsoft.com/powershell/module/az.datadog/new-azdatadogtagrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/New-AzDatadogTagRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/New-AzDatadogTagRule.md
ms.openlocfilehash: 5c31ae88cf01d1b276fc15227f571310310170db
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136726604"
---
# New-AzDatadogTagRule

## SYNOPSIS
Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu.

## SYNTAX

### CreateExpanded (Default)
```
New-AzDatadogTagRule -MonitorName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-LogRuleFilteringTag <IFilteringTag[]>] [-LogRuleSendAadLog]
 [-LogRuleSendResourceLog] [-LogRuleSendSubscriptionLog] [-MetricRuleFilteringTag <IFilteringTag[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### CreateViaIdentityExpanded
```
New-AzDatadogTagRule -InputObject <IDatadogIdentity> [-LogRuleFilteringTag <IFilteringTag[]>]
 [-LogRuleSendAadLog] [-LogRuleSendResourceLog] [-LogRuleSendSubscriptionLog]
 [-MetricRuleFilteringTag <IFilteringTag[]>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu
```powershell
PS C:\> $ftobjArray = @()
PS C:\> $ftobjArray += New-AzDatadogFilteringTagObject -Action "Include" -Value "Prod" -Name "Environment"
PS C:\> $ftobjArray += New-AzDatadogFilteringTagObject -Action "Exclude" -Value "Dev" -Name "Environment"
PS C:\> New-AzDatadogTagRule -ResourceGroupName azure-rg-Datadog -MonitorName Datadog -Name 'test' -LogRuleFilteringTag $ftobjArray

Name    Type
----    ----
default microsoft.Datadog/monitors/tagrules
```

Perintah ini membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu.

### Contoh 2: Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu menurut saluran
```powershell
PS C:\> $ftobjArray = @()
PS C:\> $ftobjArray += New-AzDatadogFilteringTagObject -Action "Include" -Value "Prod" -Name "Environment"
PS C:\> $ftobjArray += New-AzDatadogFilteringTagObject -Action "Exclude" -Value "Dev" -Name "Environment"
PS C:\> Get-AzDatadogTagRule -ResourceGroupName azure-rg-Datadog -MonitorName Datadog -Name 'default' | New-AzDatadogTagRule -LogRuleFilteringTag $ftobjArray

Name    Type
----    ----
default microsoft.Datadog/monitors/tagrules
```

Perintah ini membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu menurut saluran.

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.IDatadogIdentity
Parameter Sets: CreateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LogRuleFilteringTag
Daftar tag pemfilteran yang akan digunakan untuk merekam log.
Hal ini hanya berlaku jika bendera SendResourceLogs diaktifkan.
Jika kosong, semua sumber daya akan diambil.
Jika hanya tindakan Kecualikan yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia.
Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
Untuk membuat, lihat bagian CATATAN untuk properti LOGRULEFILTERINGTAG dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.Api20210301.IFilteringTag[]
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

### -LogRuleSendResourceLog
Bendera yang menentukan apakah log sumber daya Azure harus dikirim untuk Sumber daya Monitor.

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
Bendera yang menentukan apakah log langganan Azure harus dikirim untuk sumber daya Monitor.

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

### -MetricRuleFilteringTag
Daftar tag pemfilteran yang akan digunakan untuk merekam metrik.
Jika kosong, semua sumber daya akan diambil.
Jika hanya tindakan Kecualikan yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia.
Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
Untuk membuat, lihat bagian CATATAN untuk properti METRICRULEFILTERINGTAG dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.Api20210301.IFilteringTag[]
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
Parameter Sets: CreateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kumpulan aturan

```yaml
Type: System.String
Parameter Sets: CreateExpanded
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
Parameter Sets: CreateExpanded
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
Parameter Sets: CreateExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.IData cmdletIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.Api20210301.IMonitoringTagRules

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDatadogIdentity> : Parameter Identitas
  - `[ConfigurationName <String>]`: Nama konfigurasi
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MonitorName <String>]`: Memantau nama sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[RuleSetName <String>]`: Nama kumpulan aturan
  - `[SubscriptionId <String>]`: ID langganan target.

LOGRULEFILTERINGTAG <IFilteringTag[]>: Daftar tag pemfilteran yang akan digunakan untuk mengambil log. Hal ini hanya berlaku jika bendera SendResourceLogs diaktifkan. Jika kosong, semua sumber daya akan diambil. Jika hanya tindakan Kecualikan yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia. Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
  - `[Action <TagAction?>]`: Tindakan yang valid untuk tag pemfilteran. Pengecualian akan diprioritaskan atas pencakusan.
  - `[Name <String>]`: Nama (juga dikenal sebagai kunci) tag.
  - `[Value <String>]`: Nilai tag.

METRICRULEFILTERINGTAG <IFilteringTag[]>: Daftar tag pemfilteran yang akan digunakan untuk merekam metrik. Jika kosong, semua sumber daya akan diambil. Jika hanya tindakan Kecualikan yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia. Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
  - `[Action <TagAction?>]`: Tindakan yang valid untuk tag pemfilteran. Pengecualian akan diprioritaskan atas pencakusan.
  - `[Name <String>]`: Nama (juga dikenal sebagai kunci) tag.
  - `[Value <String>]`: Nilai tag.

## RELATED LINKS

