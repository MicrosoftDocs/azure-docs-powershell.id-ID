---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/get-azsentinelalertrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelAlertRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelAlertRule.md
ms.openlocfilehash: 0ada96cf5729b24295ffa344dd9f3e53a45a4623
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144192267"
---
# Get-AzSentinelAlertRule

## SYNOPSIS
Mendapatkan atau semua Aturan Analitik tertentu (Aturan Pemberitahuan).

## SYNTAX

### Ruang KerjaScope (Default)
```
Get-AzSentinelAlertRule -ResourceGroupName <String> -WorkspaceName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AlertRuleId
```
Get-AzSentinelAlertRule -ResourceGroupName <String> -WorkspaceName <String> -AlertRuleId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceId
```
Get-AzSentinelAlertRule -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSentinelAlertRule** mendapatkan satu atau beberapa Aturan Analitik (Aturan Pemberitahuan) dari ruang kerja yang ditentukan.
Jika Anda menentukan parameter *AlertRuleId* , satu objek AlertRule dikembalikan.
Jika Anda tidak menentukan parameter *AlertRuleId* , array yang berisi semua Aturan Pemberitahuan di ruang kerja yang ditentukan dikembalikan.
Anda dapat menggunakan objek AlertRule untuk memperbarui AlertRule. Misalnya, Anda dapat mengaktifkan atau menonaktifkan AlertRule. <br/>

*Catatan: AlertRuleId dapat berupa string apa pun, selama unik di ruang kerja Anda dan dapat ditemukan di tampilan Azure Sentinel Analytics di bawah panel detail aturan di sebelah kanan Anda di bidang "Id"*

## EXAMPLES

### Contoh 1
```powershell
$AlertRules = Get-AzSentinelAlertRule -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName"
```

Contoh ini mendapatkan semua AlertRules di ruang kerja yang ditentukan, lalu menyimpannya dalam variabel $AlertRules.

### Contoh 2
```powershell
$AlertRule = Get-AzSentinelAlertRule -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName" -AlertRuleId "myAlertRuleId"
```

Contoh ini mendapatkan AlertRule di ruang kerja yang ditentukan, lalu menyimpannya dalam variabel $AlertRule.<br/>
*Harap dicatat bahwa **AlertRuleId** dalam format ini: 168d330b-219b-4191-a5b1-742c211adb05*

### Contoh 3
```powershell
Get-AzSentinelAlertRule -ResourceGroupName $resourceGroupName -WorkspaceName $workspaceName | Where-Object {$_.DisplayName -like "*Azure Security Center*"}
```

Contoh ini mendapatkan AlertRule dengan nama tampilan yang berisi "Azure Security Center"

## PARAMETERS

### -AlertRuleId
Id Aturan Pemberitahuan.

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: WorkspaceScope, AlertRuleId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkspaceName
Nama Ruang Kerja.

```yaml
Type: System.String
Parameter Sets: WorkspaceScope, AlertRuleId
Aliases:

Required: True
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

### Microsoft.Azure.Commands.SecurityInsights.Models.AlertRules.PSSentinelAlertRule
## NOTES

## RELATED LINKS
