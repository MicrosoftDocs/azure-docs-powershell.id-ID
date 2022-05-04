---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/invoke-azpurviewtagclassificationruleclassificationversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Invoke-AzPurviewTagClassificationRuleClassificationVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Invoke-AzPurviewTagClassificationRuleClassificationVersion.md
ms.openlocfilehash: 870b58fbb83d369607c65bdfcac339a741ba2e45
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144716762"
---
# Invoke-AzPurviewTagClassificationRuleClassificationVersion

## SYNOPSIS
Mengatur Tindakan Klasifikasi pada versi aturan klasifikasi tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/invoke-azpurviewtagclassificationruleclassificationversion) untuk informasi terbaru.

## SYNTAX

```
Invoke-AzPurviewTagClassificationRuleClassificationVersion -Endpoint <String> -ClassificationRuleName <String>
 -ClassificationRuleVersion <Int32> -Action <ClassificationAction> [-DefaultProfile <PSObject>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mengatur Tindakan Klasifikasi pada versi aturan klasifikasi tertentu.

## EXAMPLES

### Contoh 1: Mengatur Tindakan Klasifikasi pada versi aturan tertentu
```powershell
PS C:\> Invoke-AzPurviewTagClassificationRuleClassificationVersion -Endpoint 'https://parv-brs-2.purview.azure.com/' -ClassificationRuleName 'ClassificationRule2' -ClassificationRuleVersion 1 -Action 'Delete'

EndTime ScanResultId StartTime Status
------- ------------ --------- ------
                               Accepted
```

Mengatur Tindakan Klasifikasi pada versi aturan tertentu

## PARAMETERS

### -Tindakan
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.ClassificationAction
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClassificationRuleName
.

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

### -ClassificationRuleVersion
.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
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

### -Titik akhir
Titik akhir pemindaian akun purview Anda.
Contoh: https://{accountName}.purview.azure.com

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IOperationResponse

## NOTES

ALIAS

## RELATED LINKS
