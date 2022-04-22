---
external help file: ''
Module Name: Az.Datadog
online version: https://docs.microsoft.com/powershell/module/az.datadog/new-azdatadogtagrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/New-AzDatadogTagRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/New-AzDatadogTagRule.md
ms.openlocfilehash: 503e503864c3941520262cdeda982b7f6e50801b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142967321"
---
# New-AzDatadogTagRule

## SYNOPSIS
Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datadog/new-azdatadogtagrule) untuk informasi terbaru.

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

### Contoh 2: Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu menurut pipeline
```powershell
PS C:\> $ftobjArray = @()
PS C:\> $ftobjArray += New-AzDatadogFilteringTagObject -Action "Include" -Value "Prod" -Name "Environment"
PS C:\> $ftobjArray += New-AzDatadogFilteringTagObject -Action "Exclude" -Value "Dev" -Name "Environment"
PS C:\> Get-AzDatadogTagRule -ResourceGroupName azure-rg-Datadog -MonitorName Datadog -Name 'default' | New-AzDatadogTagRule -LogRuleFilteringTag $ftobjArray

Name    Type
----    ----
default microsoft.Datadog/monitors/tagrules
```

Perintah ini membuat atau memperbarui aturan tag yang ditetapkan untuk sumber daya monitor tertentu menurut pipeline.

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
Parameter Sets: CreateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LogRuleFilteringTag
Daftar pemfilteran tag yang akan digunakan untuk mengambil log.
Hal ini hanya berlaku jika bendera SendResourceLogs diaktifkan.
Jika kosong, semua sumber daya akan direkam.
Jika hanya tindakan Pengecualian yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia.
Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
Untuk membangun, lihat bagian CATATAN untuk properti LOGRULEFILTERINGTAG dan membuat tabel hash.

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
Bendera yang menentukan apakah log AAD harus dikirim untuk sumber daya Monitor.

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
Bendera yang menentukan apakah log sumber daya Azure harus dikirim untuk sumber daya Monitor.

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
Daftar pemfilteran tag yang akan digunakan untuk mengambil metrik.
Jika kosong, semua sumber daya akan direkam.
Jika hanya tindakan Pengecualian yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia.
Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
Untuk membangun, lihat bagian CATATAN untuk properti METRICRULEFILTERINGTAG dan membuat tabel hash.

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
Pantau nama sumber daya

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
Nama ini tidak peka huruf besar kecil.

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

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.IDatadogIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.Api20210301.IMonitoringTagRules

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDatadogIdentity>: Parameter Identitas
  - `[ConfigurationName <String>]`: Nama konfigurasi
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MonitorName <String>]`: Memantau nama sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[RuleSetName <String>]`: Nama kumpulan aturan
  - `[SubscriptionId <String>]`: ID langganan target.

LOGRULEFILTERINGTAG <IFilteringTag[]>: Daftar tag pemfilteran yang akan digunakan untuk mengambil log. Hal ini hanya berlaku jika bendera SendResourceLogs diaktifkan. Jika kosong, semua sumber daya akan direkam. Jika hanya tindakan Pengecualian yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia. Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
  - `[Action <TagAction?>]`: Tindakan valid untuk tag pemfilteran. Pengecualian lebih diprioritaskan daripada penyertaan.
  - `[Name <String>]`: Nama (juga dikenal sebagai kunci) tag.
  - `[Value <String>]`: Nilai tag.

METRICRULEFILTERINGTAG <IFilteringTag[]>: Daftar tag pemfilteran yang akan digunakan untuk mengambil metrik. Jika kosong, semua sumber daya akan direkam. Jika hanya tindakan Pengecualian yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia. Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
  - `[Action <TagAction?>]`: Tindakan valid untuk tag pemfilteran. Pengecualian lebih diprioritaskan daripada penyertaan.
  - `[Name <String>]`: Nama (juga dikenal sebagai kunci) tag.
  - `[Value <String>]`: Nilai tag.

## RELATED LINKS

