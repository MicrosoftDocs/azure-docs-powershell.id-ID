---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/get-azoperationalinsightsdataexport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsDataExport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsDataExport.md
ms.openlocfilehash: 05c10cf105245423279d7f558f845fd2fd4b8b68
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138288604"
---
# Get-AzOperationalInsightsDataExport

## SYNOPSIS
Dapatkan atau  list ekspor data untuk ruang kerja.

## SYNTAX

### ListParameterSet (Default)
```
Get-AzOperationalInsightsDataExport [-ResourceGroupName <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByNameParameterSet
```
Get-AzOperationalInsightsDataExport -ResourceGroupName <String> -WorkspaceName <String>
 [-DataExportName <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceIdParameterSet
```
Get-AzOperationalInsightsDataExport -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan ekspor Data ruang kerja berdasarkan nama atau semua ekspor data ruang kerja yang ada.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzOperationalInsightsDataExport -ResourceGroupName {rg-name} -WorkspaceName {workspace-name} -DataExportName {dataExportName}

Name             : {dataExportName}
Id               : /subscriptions/{subscription}/resourcegroups/{rg-name}/providers/microsoft.operationalinsights/workspaces/{workspace-name}/dataexports/{dataExportName}
Type             : Microsoft.OperationalInsights/workspaces/export
DataExportId     : {GUID}
TableNames       : {tbl1,tbl2}
ResourceId       : /subscriptions/{resource_subscription}/resourceGroups/{resource_rg}/providers/Microsoft.Storage/storageAc
                   counts/{storage_name}
DataExportType   : StorageAccount
EventHubName     :
Enable           : True
CreatedDate      : 
LastModifiedDate :
```

Mendapatkan ekspor Data ruang kerja.

### Contoh 2
```powershell
PS C:\> Get-AzOperationalInsightsDataExport -ResourceGroupName {rg-name} -WorkspaceName {workspace-name}
```

Mendapatkan semua ekspor Data ruang kerja.

## PARAMETERS

### -DataExportName
Nama ekspor data.

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet
Aliases:

Required: False
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
Parameter Sets: ListParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya tujuan.
Ini dapat disalin dari entri Properti dari sumber daya tujuan di Azure.

```yaml
Type: System.String
Parameter Sets: GetByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja yang akan berisi wawasan penyimpanan.

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSDataExport

## CATATAN

## RELATED LINKS
