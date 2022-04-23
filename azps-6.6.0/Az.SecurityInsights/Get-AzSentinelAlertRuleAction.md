---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/get-azsentinelalertruleaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelAlertRuleAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelAlertRuleAction.md
ms.openlocfilehash: c12128bad16b11b9f7c6416ad5746ec3a569fbe7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143191151"
---
# Get-AzSentinelAlertRuleAction

## SYNOPSIS
Mendapatkan Respons Otomatis (Tindakan Aturan Peringatan) untuk Aturan Analitik, seperti Playbook Azure Logic Apps.<br/>
Aturan Otomatisasi Azure Sentinel akan didukung di masa mendatang.

*Catatan: Ini memerlukan nilai parameter "AlertRuleId"*

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.securityinsights/get-azsentinelalertruleaction) untuk informasi terbaru.

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
Cmdlet **Get-AzSentinelAlertRuleAction** mendapatkan Respons Otomatis (Tindakan Aturan Peringatan) dari ruang kerja tertentu.
Jika Anda menentukan parameter *ActionId* dan *AlertRuleId* , sebuah objek **AlertRuleAction** dikembalikan.<br/>
Jika Anda tidak menentukan parameter *ActionId* , array yang berisi semua Tindakan untuk Aturan Peringatan tertentu dalam ruang kerja tertentu akan dikembalikan.
Anda bisa menggunakan objek **Tindakan** untuk memperbarui Tindakan, misalnya Anda bisa mengubah **Tindakan** untuk Aturan Peringatan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $AlertRuleActions = Get-AzSentinelAlertRuleAction -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName" -AlertRuleId "29d2523f-84ce-42d3-b5f1-9e63c85aaed1"
```

Contoh ini mendapatkan semua **Tindakan** untuk Aturan Peringatan tertentu dalam ruang kerja tertentu, lalu menyimpannya dalam variabel $AlertRuleActions.<br/><br/>

*Catatan: **Bidang LogicAppResourceID** berisi ID Azure Resource Manager (ARM) lengkap, yang berisi nama playbook Azure Logic Apps.*

### Contoh 2
```powershell
PS C:\> $AlertRuleAction = Get-AzSentinelAlertRuleAction -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName" -AlertRuleId "MyAlertRuleId" -ActionId "MyActionId"
```

Contoh ini mendapatkan **AlertRuleAction** untuk Aturan Peringatan tertentu dalam ruang kerja tertentu, lalu menyimpannya dalam variabel $AlertRuleAction.

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
Id Aturan Peringatan.

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

### -Nama Ruang Kerja
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
## OUTPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.Actions.PSSentinelActionResponse
## NOTES

## RELATED LINKS
