---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azfrontdoorcdnrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnRule.md
ms.openlocfilehash: 044238cb15630af0852ab36597892a4462628fd9
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140312359"
---
# New-AzFrontDoorCdnRule

## SYNOPSIS
Membuat aturan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.cdn/new-azfrontdoorcdnrule) untuk informasi terkini.

## SYNTAX

```
New-AzFrontDoorCdnRule
 -Action <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdRuleAction]>
 [-Condition <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdRuleCondition]>]
 -ProfileName <String> -ResourceGroupName <String> -RuleSetName <String> -RuleName <String> -Order <Int32>
 [-MatchProcessingBehavior <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat aturan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzFrontDoorCdnRule -Action $action -Condition $condition -ProfileName $profileName -ResourceGroupName $resourceGroupName -RuleSetName $ruleSetName -RuleName $ruleName -Order $order
```

Membuat aturan.

## PARAMETERS

### -Tindakan
Kumpulan tindakan untuk aturan pengiriman.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdRuleAction]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kondisi
Kumpulan kondisi untuk aturan pengiriman.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdRuleCondition]
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MatchProcessingBeprocessior
Jika aturan ini cocok jika mesin aturan terus menjalankan aturan yang tersisa atau berhenti.
Jika tidak ada, defaultnya adalah Lanjutkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pesanan
Urutan aturan yang diterapkan untuk titik akhir.
Nilai yang mungkin {0,1,2,3,.........}.
Aturan dengan urutan yang lebih kecil akan diterapkan sebelum aturan dengan urutan yang lebih besar.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileName
Nama profil Pintu Depan Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleName
Nama aturan Pintu Depan Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleSetName
Nama kumpulan aturan Pintu Depan Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdRule

## CATATAN

## RELATED LINKS
