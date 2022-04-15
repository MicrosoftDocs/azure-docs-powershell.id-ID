---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/update-azoperationalinsightsdataexport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Update-AzOperationalInsightsDataExport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Update-AzOperationalInsightsDataExport.md
ms.openlocfilehash: 89b0a7cb39bf02723c5e5967cb6fac3f586d449a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142421589"
---
# Update-AzOperationalInsightsDataExport

## SYNOPSIS
Perbarui ekspor data.

## SYNTAX

### UpdateByNameParameterSet (Default)
```
Update-AzOperationalInsightsDataExport -ResourceGroupName <String> -WorkspaceName <String>
 [-DataExportName <String>] [-TableName <String[]>] [-DestinationResourceId <String>] [-EventHubName <String>]
 [-Enable <Boolean>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateByResourceIdParameterSet
```
Update-AzOperationalInsightsDataExport -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateByInputObjectParameterSet
```
Update-AzOperationalInsightsDataExport -InputDataExport <PSDataExport>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui ekspor data.

## EXAMPLES

### Contoh 1
```powershell
Update-AzOperationalInsightsDataExport -ResourceGroupName {rg-name} -WorkspaceName {workspace-name} -DataExportName {dataExportName} -TableNames {table_names} -Enable $true
```

```output
Name             : {dataExportName}
Id               : /subscriptions/{subscription}/resourcegroups/{rg-name}/providers/microsoft.operationalinsights/workspaces/{workspace-name}/dataexports/{dataExportName}
Type             : Microsoft.OperationalInsights/workspaces/export
DataExportId     : {GUID}
TableNames       : {table_names}
ResourceId       : /subscriptions/{resource_subscription}/resourceGroups/{resource_rg}/providers/Microsoft.Storage/storageAc
                   counts/{storage_name}
DataExportType   : StorageAccount
EventHubName     :
Enable           : true
CreatedDate      : 
LastModifiedDate :
```

Memperbarui ekspor Data ruang kerja.

## PARAMETERS

### -DataExportName
Nama ekspor data.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet
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

### -DestinationResourceId
ID sumber daya tujuan. Ini dapat disalin dari entri Properti sumber daya tujuan di Azure.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Aktifkan
Aktif saat diaktifkan.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventHubName
Opsional.
Memungkinkan untuk menentukan nama Hub Kejadian.
Tidak berlaku ketika tujuan adalah Akun Storage.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputDataExport
Menentukan DataExport yang akan diperbarui.

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSDataExport
Parameter Sets: UpdateByInputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya tujuan.
Ini dapat disalin dari entri Properti sumber daya tujuan di Azure.

```yaml
Type: System.String
Parameter Sets: UpdateByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TableName
Array tabel untuk diekspor, misalnya: ["Heartbeat, SecurityEvent"].

```yaml
Type: System.String[]
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Nama ruang kerja yang akan berisi wawasan penyimpanan.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Azure.Commands.OperationalInsights.Models.PSDataExport

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSDataExport

## CATATAN

## RELATED LINKS
