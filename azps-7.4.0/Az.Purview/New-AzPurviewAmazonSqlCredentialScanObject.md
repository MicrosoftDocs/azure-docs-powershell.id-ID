---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAmazonSqlCredentialScanObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAmazonSqlCredentialScanObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAmazonSqlCredentialScanObject.md
ms.openlocfilehash: 7d5fb348366db7f2276b7e0f4354f93975a988d0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142421266"
---
# New-AzPurviewAmazonSqlCredentialScanObject

## SYNOPSIS
Membuat objek dalam memori untuk AmazonSqlCredentialScan.

## SYNTAX

```
New-AzPurviewAmazonSqlCredentialScanObject -Kind <ScanAuthorizationType> [-CollectionReferenceName <String>]
 [-CollectionType <String>] [-ConnectedViaReferenceName <String>] [-CredentialReferenceName <String>]
 [-CredentialType <CredentialType>] [-DatabaseName <String>] [-Port <Int32>] [-ScanRulesetName <String>]
 [-ScanRulesetType <ScanRulesetType>] [-ServerEndpoint <String>] [-VpcEndpointServiceName <String>]
 [-Worker <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk AmazonSqlCredentialScan.

## EXAMPLES

### Contoh 1: Buat objek pemindaian Kredensial Amazon Sql
```powershell
PS C:\> New-AzPurviewAmazonSqlCredentialScanObject -Kind 'AmazonSqlCredential' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -CredentialReferenceName 'sqlauth' -CredentialType 'SqlAuth' -DatabaseName 'db' -Port 5432 -ScanRulesetName 'AmazonSql' -ScanRulesetType 'System' -ServerEndpoint 'DummyServer' -VpcEndpointServiceName 'com.amazonaws.ypce.wus.123456789'

CollectionLastModifiedAt  :
CollectionReferenceName   : parv-brs-2
CollectionType            : CollectionReference
ConnectedViaReferenceName :
CreatedAt                 :
CredentialReferenceName   : sqlauth
CredentialType            : SqlAuth
DatabaseName              : db
Id                        :
Kind                      : AmazonSqlCredential
LastModifiedAt            :
Name                      :
Port                      : 5432
Result                    :
ScanRulesetName           : AmazonSql
ScanRulesetType           : System
ServerEndpoint            : DummyServer
VpcEndpointServiceName    : com.amazonaws.ypce.wus.123456789
Worker                    :
```

Membuat objek pemindaian Kredensial Amazon Sql

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

### -Port

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

### -VpcEndpointServiceName

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AmazonSqlCredentialScan

## CATATAN

ALIAS

## RELATED LINKS
