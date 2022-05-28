---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/get-azsqlserverdnsalias
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServerDnsAlias.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServerDnsAlias.md
ms.openlocfilehash: 300db6e67128b0099d20d39c4659c1118a414978
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145513234"
---
# Get-AzSqlServerDnsAlias

## SYNOPSIS
Mendapatkan atau mencantumkan Azure SQL Alias DNS Server.

## SYNTAX

```
Get-AzSqlServerDnsAlias [-Name <String>] -ServerName <String> [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan Alias DNS server Azure SQL tertentu atau mencantumkan semua Alias DNS Server untuk server

## EXAMPLES

### Contoh 1
```powershell
$serverDNSAliases = Get-AzSqlServerDnsAlias -ServerName servername -ResourceGroupName rgname
```

```output
ResourceGroupName  ServerName   DnsAliasName
-----------------  ----------   ------------------
rgname             servername   dnsaliasname
rgname             servername   dnsaliasname2
```

Mencantumkan semua Alias DNS Server untuk server tertentu

### Contoh 2
```powershell
$serverDNSAliases = Get-AzSqlServerDnsAlias -DnsAliasName dnsaliasname -ServerName servername -ResourceGroupName rgname
```

```output
ResourceGroupName  ServerName   DnsAliasName
-----------------  ----------   ------------------
rgname             servername   dnsaliasname
```

Mendapatkan Alias DNS Server yang ditentukan oleh nama server dan alias

### Contoh: 3
```powershell
$serverDNSAliases = Get-AzSqlServerDnsAlias -ServerName servername -ResourceGroupName rgname -DnsAliasName "dnsaliasname*"
```

```output
ResourceGroupName  ServerName   DnsAliasName
-----------------  ----------   ------------------
rgname             servername   dnsaliasname
rgname             servername   dnsaliasname2
```

Mencantumkan semua Alias DNS Server untuk server tertentu yang dimulai dengan "dnsaliasname".

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Name
Nama Alias DNS Azure Sql Server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DnsAliasName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
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

### -ServerName
Nama Azure Sql Server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ServerDnsAlias.Model.AzureSqlServerDnsAliasModel

## NOTES

## RELATED LINKS
