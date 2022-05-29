---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/remove-azsqlserveroutboundfirewallrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Remove-AzSqlServerOutboundFirewallRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Remove-AzSqlServerOutboundFirewallRule.md
ms.openlocfilehash: 92c5285aaec97521a2b3ee0a6b74a90bac03a5b2
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145723996"
---
# Remove-AzSqlServerOutboundFirewallRule

## SYNOPSIS
Menghapus FQDN yang diizinkan dari daftar aturan firewall keluar (FQDN yang Diizinkan) dari server SQL Database.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.sql/remove-azsqlserveroutboundfirewallrule) untuk informasi terbaru.

## SYNTAX

```
Remove-AzSqlServerOutboundFirewallRule [-AllowedFQDN] <String> [-Force] [-ServerName] <String>
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzSqlServerOutboundFirewallRule** menghapus FQDN yang diizinkan yang ditentukan dari daftar aturan firewall keluar (FQDN yang Diizinkan) dari server Azure SQL Database yang ditentukan.

## EXAMPLES

### Contoh 1: Menghapus aturan firewall keluar
```powershell
Remove-AzSqlServerOutboundFirewallRule -ServerName "Server01" -ResourceGroupName "ResourceGroup01" -AllowedFQDN "OutboundFirewallRule01"
```

```output
ResourceGroupName : ResourceGroup01
ServerName        : Server01
AllowedFQDN       : OutboundFirewallRule01
```

Perintah ini menghapus FQDN yang diizinkan bernama OutboundFirewallRule01 dari daftar aturan firewall keluar di server bernama Server01.

## PARAMETERS

### -AllowedFQDN
Menentukan nama domain yang sepenuhnya memenuhi syarat (FQDN) yang diizinkan dalam daftar aturan firewall keluar.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Force
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat server ditetapkan.

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
Menentukan nama server.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.OutboundFirewallRules.Model.AzureSqlServerOutboundFirewallRulesModel

## NOTES

## RELATED LINKS

[Get-AzSqlServerOutboundFirewallRule](./Get-AzSqlServerOutboundFirewallRule.md)

[New-AzSqlServerOutboundFirewallRule](./New-AzSqlServerOutboundFirewallRule.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
