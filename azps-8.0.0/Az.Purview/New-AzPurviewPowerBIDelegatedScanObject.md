---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewPowerBIDelegatedScanObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewPowerBIDelegatedScanObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewPowerBIDelegatedScanObject.md
ms.openlocfilehash: cb4df147fee6cf29622d97e25cc8c73eecbc9342
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145534025"
---
# New-AzPurviewPowerBIDelegatedScanObject

## SYNOPSIS
Buat objek dalam memori untuk PowerBIDelegatedScan.

## SYNTAX

```
New-AzPurviewPowerBIDelegatedScanObject -Kind <ScanAuthorizationType> [-AuthenticationType <String>]
 [-ClientId <String>] [-CollectionReferenceName <String>] [-CollectionType <String>]
 [-ConnectedViaReferenceName <String>] [-IncludePersonalWorkspace <Boolean>] [-Password <String>]
 [-ScanRulesetName <String>] [-ScanRulesetType <ScanRulesetType>] [-Tenant <String>] [-UserName <String>]
 [-Worker <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk PowerBIDelegatedScan.

## EXAMPLES

### Contoh 1: Membuat objek pemindaian yang didelegasikan PowerBI
```powershell
PS C:\> New-AzPurviewPowerBIDelegatedScanObject -Kind 'PowerBIDelegated' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -IncludePersonalWorkspace $true -ClientId 'xxxxxxx-cdfd-4016-9e80-xxxxxxxx' -UserName 'abcd@msft.com' -Password 'pwd'

AuthenticationType        :
ClientId                  : xxxxxxx-cdfd-4016-9e80-xxxxxxxx
CollectionLastModifiedAt  :
CollectionReferenceName   : parv-brs-2
CollectionType            : CollectionReference
ConnectedViaReferenceName :
CreatedAt                 :
Id                        :
IncludePersonalWorkspace  : True
Kind                      : PowerBIDelegated
LastModifiedAt            :
Name                      :
Password                  : pwd
Result                    :
ScanRulesetName           :
ScanRulesetType           :
Tenant                    :
UserName                  : abcd@msft.com
Worker                    :
```

Membuat objek pemindaian yang didelegasikan PowerBI

## PARAMETERS

### -AuthenticationType

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

### -ClientId

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

### -IncludePersonalWorkspace

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kind

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

### -Kata sandi

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

### -Penyewa

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

### -UserName

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.PowerBiDelegatedScan

## NOTES

ALIAS

## RELATED LINKS
