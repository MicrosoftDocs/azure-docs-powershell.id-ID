---
external help file: ''
Module Name: Az.Elastic
online version: https://docs.microsoft.com/powershell/module/az.elastic/new-azelastictagrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/New-AzElasticTagRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/New-AzElasticTagRule.md
ms.openlocfilehash: 50d6ecf947606141071c8434fc7c69e7eaa5283f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143316413"
---
# New-AzElasticTagRule

## SYNOPSIS
Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu.

## SYNTAX

```
New-AzElasticTagRule -MonitorName <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-LogRuleFilteringTag <IFilteringTag[]>] [-LogRuleSendAadLog] [-LogRuleSendActivityLog]
 [-LogRuleSendSubscriptionLog] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui kumpulan aturan tag untuk sumber daya monitor tertentu
```powershell
New-AzElasticTagRule -ResourceGroupName azps-elastic-test -MonitorName elastic-pwsh02 -LogRuleSendActivityLog
```

```output
Name    ProvisioningState ResourceGroupName
----    ----------------- -----------------
default Succeeded         azps-elastic-test
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
Daftar pemfilteran tag yang akan digunakan untuk mengambil log.
Ini hanya berlaku jika bendera SendActivityLogs diaktifkan.
Jika kosong, semua sumber daya akan direkam.
Jika hanya tindakan Pengecualian yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia.
Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
Untuk membangun, lihat bagian CATATAN untuk properti LOGRULEFILTERINGTAG dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Elastic.Models.Api20200701.IFilteringTag[]
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

### -LogRuleSendActivityLog
Bendera yang menentukan apakah log aktivitas dari sumber daya Azure harus dikirim untuk sumber daya Monitor.

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
Bendera yang menentukan apakah log langganan harus dikirim untuk sumber daya Monitor.

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
Pantau nama sumber daya

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
Nama grup sumber daya tempat sumber daya Elastis berada.

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
ID langganan Azure.
Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000)

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Elastic.Models.Api20200701.IMonitoringTagRules

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LOGRULEFILTERINGTAG <IFilteringTag[]>: Daftar tag pemfilteran yang akan digunakan untuk mengambil log. Ini hanya berlaku jika bendera SendActivityLogs diaktifkan. Jika kosong, semua sumber daya akan direkam. Jika hanya tindakan Pengecualian yang ditentukan, aturan akan berlaku untuk daftar semua sumber daya yang tersedia. Jika Sertakan tindakan ditentukan, aturan hanya akan menyertakan sumber daya dengan tag terkait.
  - `[Action <TagAction?>]`: Tindakan valid untuk tag pemfilteran.
  - `[Name <String>]`: Nama (juga dikenal sebagai kunci) tag.
  - `[Value <String>]`: Nilai tag.

## RELATED LINKS

