---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/update-azfrontdoorcdnrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Update-AzFrontDoorCdnRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Update-AzFrontDoorCdnRule.md
ms.openlocfilehash: 79943a3d2e3d6b0b2abf9028d86b961d33d12c00
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145618148"
---
# Update-AzFrontDoorCdnRule

## SYNOPSIS
Memperbarui aturan pengiriman yang ada dalam seperangkat aturan.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzFrontDoorCdnRule -Name <String> -ProfileName <String> -ResourceGroupName <String> -SetName <String>
 [-SubscriptionId <String>] [-Action <IDeliveryRuleAction1[]>] [-Condition <IDeliveryRuleCondition[]>]
 [-MatchProcessingBehavior <MatchProcessingBehavior>] [-Order <Int32>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzFrontDoorCdnRule -InputObject <ICdnIdentity> [-Action <IDeliveryRuleAction1[]>]
 [-Condition <IDeliveryRuleCondition[]>] [-MatchProcessingBehavior <MatchProcessingBehavior>] [-Order <Int32>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui aturan pengiriman yang ada dalam seperangkat aturan.

## EXAMPLES

### Contoh 1: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

### Contoh 2: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

## PARAMETERS

### -Tindakan
Daftar tindakan yang dijalankan ketika semua kondisi aturan terpenuhi.
Untuk membuat, lihat bagian CATATAN untuk properti ACTION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IDeliveryRuleAction1[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Jalankan perintah sebagai pekerjaan

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

### -Kondisi
Daftar kondisi yang harus dicocokkan agar tindakan dijalankan Untuk membangun, lihat bagian CATATAN untuk properti CONDITION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IDeliveryRuleCondition[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MatchProcessingBehavior
Jika aturan ini cocok jika mesin aturan terus menjalankan aturan yang tersisa atau berhenti.
Jika tidak ada, default ke Lanjutkan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.MatchProcessingBehavior
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama aturan pengiriman yang unik dalam titik akhir.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: RuleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -Pesanan
Urutan penerapan aturan untuk titik akhir.
Nilai yang mungkin {0,1,2,3,.........}.
Aturan dengan urutan yang lebih rendah akan diterapkan sebelum aturan dengan urutan yang lebih besar.
Aturan dengan urutan 0 adalah aturan khusus.
Ini tidak memerlukan kondisi dan tindakan apa pun yang tercantum di dalamnya akan selalu diterapkan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileName
Nama profil Premium Azure Front Door Standard atau Azure Front Door yang unik dalam grup sumber daya.

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
Nama grup Sumber Daya dalam langganan Azure.

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

### -SetName
Nama seperangkat aturan di bawah profil.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: RuleSetName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID Langganan Azure.

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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IRule

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ACTION <IDeliveryRuleAction1[]>: Daftar tindakan yang dijalankan ketika semua kondisi aturan terpenuhi.
  - `Name <DeliveryRuleAction>`: Nama tindakan untuk aturan pengiriman.

CONDITION <IDeliveryRuleCondition[]>: Daftar kondisi yang harus dicocokkan agar tindakan dijalankan
  - `Name <MatchVariable>`: Nama kondisi untuk aturan pengiriman.

INPUTOBJECT <ICdnIdentity>: Parameter Identitas
  - `[CustomDomainName <String>]`: Nama domain di bawah profil yang unik secara global.
  - `[EndpointName <String>]`: Nama titik akhir di bawah profil yang unik secara global.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[OriginGroupName <String>]`: Nama grup asal yang unik dalam titik akhir.
  - `[OriginName <String>]`: Nama asal yang unik dalam profil.
  - `[ProfileName <String>]`: Nama profil Azure Front Door Standard atau Azure Front Door Premium atau CDN yang unik dalam grup sumber daya.
  - `[ResourceGroupName <String>]`: Nama grup Sumber Daya dalam langganan Azure.
  - `[RouteName <String>]`: Nama aturan perutean.
  - `[RuleName <String>]`: Nama aturan pengiriman yang unik dalam titik akhir.
  - `[RuleSetName <String>]`: Nama seperangkat aturan di bawah profil yang unik secara global.
  - `[SecretName <String>]`: Nama Rahasia di bawah profil.
  - `[SecurityPolicyName <String>]`: Nama kebijakan keamanan di bawah profil.
  - `[SubscriptionId <String>]`: ID Langganan Azure.

## RELATED LINKS

