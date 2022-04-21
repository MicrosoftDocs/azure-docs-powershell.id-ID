---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/remove-azsentinelalertrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Remove-AzSentinelAlertRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Remove-AzSentinelAlertRule.md
ms.openlocfilehash: 45954cecbdb0c03efb91defa7e09ac3b886ffa20
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142694728"
---
# Remove-AzSentinelAlertRule

## SYNOPSIS
Menghapus Aturan Analitik (AlertRule)

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.securityinsights/remove-azsentinelalertrule) untuk informasi terbaru.

## SYNTAX

### AlertRuleId (Default)
```
Remove-AzSentinelAlertRule -ResourceGroupName <String> -WorkspaceName <String> -AlertRuleId <String>
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Remove-AzSentinelAlertRule -InputObject <PSSentinelAlertRule> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzSentinelAlertRule** menghapus Aturan Peringatan secara permanen dari ruang kerja tertentu.
Anda dapat melewati objek **AlertRule** menggunakan operator pipeline, atau menentukan parameter yang diperlukan.
Anda dapat menggunakan variabel Konfirmasi parameter dan $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Remove-AzSentinelAlertRule -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName" -AlertRuleId "dcf87c5a-19c3-4b5a-90cd-78bf46deee5b"
```

Perintah ini menghapus Aturan Pemberitahuan dari ruang kerja.

## PARAMETERS

### -AlertRuleId
Id Aturan Peringatan.

```yaml
Type: System.String
Parameter Sets: AlertRuleId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -InputObject
InputObject.

```yaml
Type: Microsoft.Azure.Commands.SecurityInsights.Models.AlertRules.PSSentinelAlertRule
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
PassThru

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

```yaml
Type: System.String
Parameter Sets: AlertRuleId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Nama Ruang Kerja.

```yaml
Type: System.String
Parameter Sets: AlertRuleId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String
### Microsoft.Azure.Commands.SecurityInsights.Models.AlertRules.PSSentinelAlertRule
## OUTPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.AlertRules.PSSentinelAlertRule
## NOTES

## RELATED LINKS
