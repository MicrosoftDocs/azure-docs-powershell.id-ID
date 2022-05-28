---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAzureSqlDatabaseManagedInstanceMsiScanObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureSqlDatabaseManagedInstanceMsiScanObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureSqlDatabaseManagedInstanceMsiScanObject.md
ms.openlocfilehash: 5b9411f3ce06a7a4a3e0932b443b39c6b56aad81
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145503657"
---
# New-AzPurviewAzureSqlDatabaseManagedInstanceMsiScanObject

## SYNOPSIS
Buat objek dalam memori untuk AzureSqlDatabaseManagedInstanceMsiScan.

## SYNTAX

```
New-AzPurviewAzureSqlDatabaseManagedInstanceMsiScanObject -Kind <ScanAuthorizationType>
 [-CollectionReferenceName <String>] [-CollectionType <String>] [-ConnectedViaReferenceName <String>]
 [-DatabaseName <String>] [-ScanRulesetName <String>] [-ScanRulesetType <ScanRulesetType>]
 [-ServerEndpoint <String>] [-Worker <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AzureSqlDatabaseManagedInstanceMsiScan.

## EXAMPLES

### Contoh 1: Membuat objek pemindaian Azure Sql Database Managed Instance Msi
```powershell
PS C:\> New-AzPurviewAzureSqlDatabaseManagedInstanceMsiScanObject -Kind 'AzureSqlDatabaseManagedInstanceMsi' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -DatabaseName 'db' -ScanRulesetName 'AzureSqlDatabaseManagedInstance' -ScanRulesetType 'System' -ServerEndpoint 'tcp:sqstzn.public.5aaf14.database.windows.net,3342'

CollectionLastModifiedAt  :
CollectionReferenceName   : parv-brs-2
CollectionType            : CollectionReference
ConnectedViaReferenceName :
CreatedAt                 :
DatabaseName              : db
Id                        :
Kind                      : AzureSqlDatabaseManagedInstanceMsi
LastModifiedAt            :
Name                      :
Result                    :
ScanRulesetName           : AzureSqlDatabaseManagedInstance
ScanRulesetType           : System
ServerEndpoint            : tcp:sqstzn.public.5aaf14.database.windows.net,3342
Worker                    :
```

Membuat objek pemindaian Azure Sql Database Managed Instance Msi

## PARAMETERS

### -CollectionReferenceName

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectionType

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectedViaReferenceName

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jenis

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.ScanAuthorizationType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanRulesetName

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanRulesetType

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.ScanRulesetType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerEndpoint

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pekerja

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AzureSqlDatabaseManagedInstanceMsiScan

## NOTES

ALIAS

## RELATED LINKS
