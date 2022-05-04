---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/Update-AzOperationalInsightsWorkspaceSharedKey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Update-AzOperationalInsightsWorkspaceSharedKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Update-AzOperationalInsightsWorkspaceSharedKey.md
ms.openlocfilehash: 284d4c979e436f243a5ac0bbecf808ad488a7e11
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144630604"
---
# Update-AzOperationalInsightsWorkspaceSharedKey

## SYNOPSIS
Meregenerasi kunci bersama untuk Ruang Kerja Analitik Log. Kunci ini digunakan untuk menghubungkan agen Operational Insights Microsoft ke ruang kerja.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.operationalinsights/update-azoperationalinsightsworkspacesharedkey) untuk informasi terbaru.

## SYNTAX

```
Update-AzOperationalInsightsWorkspaceSharedKey [-ResourceGroupName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Meregenerasi kunci bersama untuk Ruang Kerja Analitik Log. Kunci ini digunakan untuk menghubungkan agen Operational Insights Microsoft ke ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Update-AzOperationalInsightsWorkspaceSharedKey -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace"
```

Meregenerasi kunci bersama untuk Ruang Kerja Analitik Log. mengembalikan kunci bersama Primer dan Sekunder

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama ruang kerja.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspaceKeys

## NOTES

## RELATED LINKS
