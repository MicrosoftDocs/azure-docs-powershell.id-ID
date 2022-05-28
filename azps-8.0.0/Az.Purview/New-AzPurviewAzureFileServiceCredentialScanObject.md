---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAzureFileServiceCredentialScanObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureFileServiceCredentialScanObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureFileServiceCredentialScanObject.md
ms.openlocfilehash: 4791dc51588f3ea0c5e99c6eb58458612589179b
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145545911"
---
# New-AzPurviewAzureFileServiceCredentialScanObject

## SYNOPSIS
Buat objek dalam memori untuk AzureFileServiceCredentialScan.

## SYNTAX

```
New-AzPurviewAzureFileServiceCredentialScanObject -Kind <ScanAuthorizationType>
 [-CollectionReferenceName <String>] [-CollectionType <String>] [-ConnectedViaReferenceName <String>]
 [-CredentialReferenceName <String>] [-CredentialType <CredentialType>] [-ScanRulesetName <String>]
 [-ScanRulesetType <ScanRulesetType>] [-ShareName <String>] [-Worker <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AzureFileServiceCredentialScan.

## EXAMPLES

### Contoh 1: Membuat objek pemindaian Kredensial Azure File Service
```powershell
PS C:\> New-AzPurviewAzureFileServiceCredentialScanObject -Kind 'AzureFileServiceCredential' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -CredentialReferenceName 'datascantestdataparv-accountkey' -CredentialType 'AccountKey' -ScanRulesetName 'AzureFileService'  -ScanRulesetType 'System' -ShareName 'share'

CollectionLastModifiedAt  :
CollectionReferenceName   : parv-brs-2
CollectionType            : CollectionReference
ConnectedViaReferenceName :
CreatedAt                 :
CredentialReferenceName   : datascantestdataparv-accountkey
CredentialType            : AccountKey
Id                        :
Kind                      : AzureFileServiceCredential
LastModifiedAt            :
Name                      :
Result                    :
ScanRulesetName           : AzureFileService
ScanRulesetType           : System
ShareName                 : share
Worker                    :
```

Membuat objek pemindaian Kredensial Azure File Service

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

### -ShareName

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AzureFileServiceCredentialScan

## NOTES

ALIAS

## RELATED LINKS
