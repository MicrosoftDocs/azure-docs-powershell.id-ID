---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/get-azsentinelalertruleaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelAlertRuleAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelAlertRuleAction.md
ms.openlocfilehash: f6a8536c3cf7338f61bbb0a25b1bfe6e257414aa
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145511443"
---
# Get-AzSentinelAlertRuleAction

## SYNOPSIS
Mendapatkan Respons Otomatis (Tindakan Aturan Pemberitahuan) untuk Aturan Analitik, seperti Azure Logic Apps Playbook.<br/>
Aturan Otomatisasi Azure Sentinel akan didukung di masa mendatang.

*Catatan: Ini memerlukan nilai parameter "AlertRuleId"*

## SYNTAX

### AlertRuleId (Default)
```
Get-AzSentinelAlertRuleAction -ResourceGroupName <String> -WorkspaceName <String> -AlertRuleId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Actionid
```
Get-AzSentinelAlertRuleAction -ResourceGroupName <String> -WorkspaceName <String> -AlertRuleId <String>
 -ActionId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSentinelAlertRuleAction** mendapatkan Respons Otomatis (Tindakan Aturan Pemberitahuan) dari ruang kerja yang ditentukan.
Jika Anda menentukan parameter *ActionId* dan *AlertRuleId* , satu objek **AlertRuleAction** dikembalikan.<br/>
Jika Anda tidak menentukan parameter *ActionId* , array yang berisi semua Tindakan untuk Aturan Pemberitahuan tertentu di ruang kerja yang ditentukan akan dikembalikan.
Anda bisa menggunakan objek **Tindakan** untuk memperbarui Tindakan, misalnya Anda bisa mengubah **Tindakan** untuk Aturan Pemberitahuan.

## EXAMPLES

### Contoh 1
```powershell
$AlertRuleActions = Get-AzSentinelAlertRuleAction -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName" -AlertRuleId "29d2523f-84ce-42d3-b5f1-9e63c85aaed1"
```

Contoh ini mendapatkan semua **Tindakan** untuk Aturan Pemberitahuan yang ditentukan di ruang kerja yang ditentukan, lalu menyimpannya dalam variabel $AlertRuleActions.<br/><br/>

*Catatan: bidang **LogicAppResourceID** berisi ID Azure Resource Manager (ARM) lengkap, yang berisi nama Azure Logic Apps Playbook.*

### Contoh 2
```powershell
$AlertRuleAction = Get-AzSentinelAlertRuleAction -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName" -AlertRuleId "MyAlertRuleId" -ActionId "MyActionId"
```

Contoh ini mendapatkan **AlertRuleAction** untuk Aturan Pemberitahuan yang ditentukan di ruang kerja yang ditentukan, lalu menyimpannya dalam variabel $AlertRuleAction.

## PARAMETERS

### -ActionId
Id Tindakan.

```yaml
Type: System.String
Parameter Sets: ActionId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AlertRuleId
Id Aturan Pemberitahuan.

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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama Ruang Kerja.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada
## OUTPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.Actions.PSSentinelActionResponse
## NOTES

## RELATED LINKS
