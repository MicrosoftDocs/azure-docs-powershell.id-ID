---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/Get-AzOperationalInsightsPurgeWorkspaceStatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsPurgeWorkspaceStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsPurgeWorkspaceStatus.md
ms.openlocfilehash: f441da88640df2305933e75adb532dc0eae4bffd
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140085563"
---
# Get-AzOperationalInsightsPurgeWorkspaceStatus

## SYNOPSIS
Mendapatkan status operasi pembersihan yang sedang berlangsung.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.operationalinsights/get-azoperationalinsightspurgeworkspacestatus) untuk informasi terkini.

## SYNTAX

```
Get-AzOperationalInsightsPurgeWorkspaceStatus [-ResourceGroupName] <String> [-WorkspaceName] <String>
 [-PurgeId] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan status operasi pembersihan yang sedang berlangsung.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzOperationalInsightsPurgeWorkspaceStatus -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "MyWorkspace" -PurgeId "cd944bc7-ba11-447e-910c-c6393ac020a9"
```

Perintah ini mendapatkan status operasi pembersihan yang sedang berlangsung dengan nama grup sumber daya, nama ruang kerja, dan id pembersihan yang dikembalikan dari New-AzOperationalInsightsPurgeWorkspace grup.

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

### -PurgeId
Dalam permintaan status pembersihan, ini adalah Id operasi yang statusnya dikembalikan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
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

### -WorkspaceName
Nama ruang kerja yang berisi tabel.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspacePurgeStatusResponse

## CATATAN

## RELATED LINKS
