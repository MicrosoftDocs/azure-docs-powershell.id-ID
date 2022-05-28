---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewSapS4HanaSapS4HanaCredentialScanObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewSapS4HanaSapS4HanaCredentialScanObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewSapS4HanaSapS4HanaCredentialScanObject.md
ms.openlocfilehash: 3eb906994c8059667144e41854d4c8bdd00c92d8
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145517899"
---
# New-AzPurviewSapS4HanaSapS4HanaCredentialScanObject

## SYNOPSIS
Buat objek dalam memori untuk SapS4HanaSapS4HanaCredentialScan.

## SYNTAX

```
New-AzPurviewSapS4HanaSapS4HanaCredentialScanObject -Kind <ScanAuthorizationType> [-ClientId <String>]
 [-CollectionReferenceName <String>] [-CollectionType <String>] [-ConnectedViaReferenceName <String>]
 [-CredentialReferenceName <String>] [-CredentialType <CredentialType>] [-JCoLibraryPath <String>]
 [-MaximumMemoryAllowedInGb <String>] [-MitiCache <String>] [-ScanRulesetName <String>]
 [-ScanRulesetType <ScanRulesetType>] [-Worker <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk SapS4HanaSapS4HanaCredentialScan.

## EXAMPLES

### Contoh 1: Membuat Objek Pemindaian Kredensial Hana SAPS4
```powershell
PS C:\> New-AzPurviewSapS4HanaSapS4HanaCredentialScanObject -Kind 'SapS4HanaSapS4HanaCredential' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -ClientId '444' -CredentialReferenceName 'fdsafsdf' -CredentialType 'BasicAuth' -MaximumMemoryAllowedInGb 4 -JCoLibraryPath 'file://asdas' -ConnectedViaReferenceName 'IntegrationRuntime-NJh'

ClientId                  : 444
CollectionLastModifiedAt  :
CollectionReferenceName   : parv-brs-2
CollectionType            : CollectionReference
ConnectedViaReferenceName : IntegrationRuntime-NJh
CreatedAt                 :
CredentialReferenceName   : fdsafsdf
CredentialType            : BasicAuth
Id                        :
JCoLibraryPath            : file://asdas
Kind                      : SapS4HanaSapS4HanaCredential
LastModifiedAt            :
MaximumMemoryAllowedInGb  : 4
MitiCache                 :
Name                      :
Result                    :
ScanRulesetName           :
ScanRulesetType           :
Worker                    :
```

Membuat Objek Pemindaian Kredensial SAPS4 Hana

## PARAMETERS

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

### -CredentialReferenceName

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

### -CredentialType

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.CredentialType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JCoLibraryPath

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

### -MaximumMemoryAllowedInGb

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

### -MitiCache

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.SapS4HanaSapS4HanaCredentialScan

## NOTES

ALIAS

## RELATED LINKS
