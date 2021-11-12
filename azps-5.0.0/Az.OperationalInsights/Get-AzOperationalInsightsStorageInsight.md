---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
ms.assetid: 29ABCC1B-8590-4243-A629-709F207927B4
online version: https://docs.microsoft.com/en-us/powershell/module/az.operationalinsights/get-azoperationalinsightsstorageinsight
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsStorageInsight.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsStorageInsight.md
ms.openlocfilehash: a89b4210fcd498aca3a25451e6f691df20d5510e
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132409054"
---
# Get-AzOperationalInsightsStorageInsight

## SYNOPSIS
Mendapatkan informasi tentang Storage Insight.

## SINTAKS

### ByWorkspaceName (Default)
```
Get-AzOperationalInsightsStorageInsight [-ResourceGroupName] <String> [-WorkspaceName] <String>
 [[-Name] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByWorkspaceObject
```
Get-AzOperationalInsightsStorageInsight [-Workspace] <PSWorkspace> [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzOperationalInsightsStorageInsight** mendapatkan informasi tentang layanan Storage Insight.
Jika nama Storage Insight ditentukan, cmdlet ini mendapatkan informasi tentang hal Storage Insight.
Jika Anda tidak menentukan nama, cmdlet ini mendapatkan informasi tentang semua wawasan penyimpanan di dalam ruang kerja.

## CONTOH

### Contoh 1: Dapatkan Storage Insight menurut nama
```
PS C:\>Get-AzOperationalInsightsStorageInsight -Name "MyStorageInsight" -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "ContosoWorkspace"
```

Perintah ini memperoleh wawasan penyimpanan yang bernama MyStorageInsight dari ruang kerja yang bernama ContosoWorkspace.

### Contoh 2: Mendapatkan Storage Insight dengan menggunakan objek ruang kerja
```
PS C:\>$Workspace = Get-AzOperationalInsightsWorkspace -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace"
PS C:\>Get-AzOperationalInsightsStorageInsight -Workspace $Workspace -Name "MyStorageInsight"
```

Perintah pertama menggunakan cmdlet **Get-AzOperationalInsightsWorkspace** untuk mendapatkan ruang kerja Insights Operasional, lalu menyimpannya dalam variabel $Workspace tertentu.
Perintah kedua mendapatkan wawasan penyimpanan bernama MyStorageInsight untuk ruang kerja di $Workspace.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Nama
Menentukan nama Storage Wawasan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya Azure.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ruang Kerja
Menentukan ruang kerja yang berisi Storage Insights.

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace
Parameter Sets: ByWorkspaceObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorkspaceName
Menentukan nama ruang kerja yang berisi nama Storage Insights.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceName
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace

### System.String

## OUTPUT

### Microsoft.Azure.Commands.OperationalInsights.Models.PSStorageInsight

## CATATAN

## LINK TERKAIT

[Cmdlet Azure Operational Insights](./Az.OperationalInsights.md)


