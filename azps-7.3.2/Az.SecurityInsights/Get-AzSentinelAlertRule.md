---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/get-azsentinelalertrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelAlertRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelAlertRule.md
ms.openlocfilehash: 81d3e38902831a2361f439fb3664176f6d43c1c8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142758736"
---
# Get-AzSentinelAlertRule

## SYNOPSIS
Mendapatkan aturan analitik tertentu atau semua (Aturan Peringatan).

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.securityinsights/get-azsentinelalertrule) untuk informasi terbaru.

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
Cmdlet **Get-AzSentinelAlertRule** mendapatkan satu atau beberapa Aturan Analitik (Aturan Peringatan) dari ruang kerja tertentu.
Jika Anda menentukan parameter *AlertRuleId* , sebuah objek AlertRule dikembalikan.
Jika Anda tidak menentukan parameter *AlertRuleId* , array yang berisi semua Aturan Peringatan dalam ruang kerja tertentu akan dikembalikan.
Anda dapat menggunakan objek AlertRule untuk memperbarui AlertRule. Misalnya, Anda dapat mengaktifkan atau menonaktifkan AlertRule. <br/>

*Catatan: AlertRuleId dapat berupa string apa pun, selama string tersebut unik di ruang kerja Anda dan dapat ditemukan dalam tampilan Azure Sentinel Analytics di bawah panel detail aturan di sebelah kanan Anda di bidang "Id"*

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $AlertRules = Get-AzSentinelAlertRule -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName"
```

Contoh ini mendapatkan semua AlertRules di ruang kerja tertentu, lalu menyimpannya dalam variabel $AlertRules.

### Contoh 2
```powershell
PS C:\> $AlertRule = Get-AzSentinelAlertRule -ResourceGroupName "myResourceGroup" -WorkspaceName "myWorkspaceName" -AlertRuleId "myAlertRuleId"
```

Contoh ini mendapatkan AlertRule di ruang kerja tertentu, lalu menyimpannya dalam variabel $AlertRule.<br/>
*Harap diperhatikan bahwa **AlertRuleId** dalam format ini: 168d330b-219b-4191-a5b1-742c211adb05*

### Contoh 3
```powershell
Get-AzSentinelAlertRule -ResourceGroupName $resourceGroupName -WorkspaceName $workspaceName | Where-Object {$_.DisplayName -like "*Azure Security Center*"}
```

Contoh ini mendapatkan AlertRule dengan nama tampilan yang berisi "Azure Security Center"

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

### -Nama Ruang Kerja
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
## OUTPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.AlertRules.PSSentinelAlertRule
## NOTES

## RELATED LINKS
