---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/get-azsentinelalertruleaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelAlertRuleAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelAlertRuleAction.md
ms.openlocfilehash: d9ea9748cafbce576d8e8f55d6b19f0798f3ae40
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136754604"
---
# Get-AzSentinelAlertRuleAction

## SYNOPSIS
Mendapatkan Respons Otomatis (Tindakan Aturan Pemberitahuan) untuk Aturan Analitik, seperti Azure Logic Apps Putar.<br/>
Aturan Otomatisasi Azure Sentinel akan didukung di masa mendatang.

*Catatan: Hal ini memerlukan nilai parameter "AlertRuleId"*

## SYNTAX

### AlertRuleId (Default)
```
Get-AzSentinelAlertRuleAction -ResourceGroupName <String> -WorkspaceName <String> -AlertRuleId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ActionId
```
Get-AzSentinelAlertRuleAction -ResourceGroupName <String> -WorkspaceName <String> -AlertRuleId <String>
 -ActionId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSentinelAlertRuleAction** mendapatkan Respons Otomatis (Tindakan Aturan Pemberitahuan) dari ruang kerja tertentu.
Jika Anda menentukan *parameter ActionId* *dan AlertRuleId,* satu objek **AlertRuleAction** dikembalikan.<br/>
Jika Anda tidak menentukan parameter *ActionId,* array yang berisi semua Tindakan untuk Aturan Pemberitahuan spesifik dalam ruang kerja tertentu akan dikembalikan.
Anda bisa menggunakan **objek** Tindakan untuk memperbarui Tindakan, misalnya Anda bisa mengubah **Tindakan untuk** Aturan Pemberitahuan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $AlertRuleActions = Get-AzSentinelAlertRuleAction -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName" -AlertRuleId "29d2523f-84ce-42d3-b5f1-9e63c85aaed1"
```

Contoh ini mendapatkan semua Tindakan **untuk** Aturan Pemberitahuan yang ditentukan dalam ruang kerja tertentu, lalu menyimpannya di $AlertRuleActions lain.<br/><br/>

*Catatan: bidang **LogicAppResourceID** berisi ID lengkap Azure Resource Manager (ARM), yang berisi nama Playbook Azure Logic Apps baru.*

### Contoh 2
```powershell
PS C:\> $AlertRuleAction = Get-AzSentinelAlertRuleAction -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName" -AlertRuleId "MyAlertRuleId" -ActionId "MyActionId"
```

Contoh ini mendapatkan **AlertRuleAction untuk** Aturan Pemberitahuan yang ditentukan di ruang kerja tertentu, lalu menyimpannya di $AlertRuleAction perusahaan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada
## OUTPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.Actions.PSSentinelActionResponse
## CATATAN

## RELATED LINKS
