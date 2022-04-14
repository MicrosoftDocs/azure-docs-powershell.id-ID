---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/get-azoperationalinsightstable
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsTable.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsTable.md
ms.openlocfilehash: 1252c711fd0d18acefaf01dc0b7f33ac40a5ac77
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142175824"
---
# Get-AzOperationalInsightsTable

## SYNOPSIS
Dapatkan atau cantumkan tabel untuk ruang kerja.

## SYNTAX

```
Get-AzOperationalInsightsTable [-ResourceGroupName] <String> [-WorkspaceName] <String> [[-TableName] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan atau cantumkan tabel untuk ruang kerja, daftar tabel di bawah ruang kerja saat "-TableName" tidak disediakan.

## EXAMPLES

### Contoh 1: Mendapatkan semua tabel untuk ruang kerja
```powershell
Get-AzOperationalInsightsTable -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "ContosoWorkspace"
```

Perintah ini mendapatkan semua tabel yang terkait dengan ruang kerja.

### Contoh 2: Mendapatkan tabel tertentu menurut nama
```powershell
Get-AzOperationalInsightsTable -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "ContosoWorkspace" -tableName "ContosoSavedTableName"
```

Perintah ini mendapatkan tabel tertentu menurut namanya.

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

### -TableName
Nama tabel.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama Ruang Kerja
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSTable

## CATATAN

## RELATED LINKS
