---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/remove-azsqlserveroutboundfirewallrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Remove-AzSqlServerOutboundFirewallRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Remove-AzSqlServerOutboundFirewallRule.md
ms.openlocfilehash: 178aef11dc411d093bd0feff08bfb907459c16c0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143141363"
---
# Remove-AzSqlServerOutboundFirewallRule

## SYNOPSIS
Menghapus FQDN yang diperbolehkan dari daftar aturan firewall keluar (FQDN yang Diizinkan) dari server SQL Database.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.sql/remove-azsqlserveroutboundfirewallrule) untuk informasi terbaru.

## SYNTAX

```
Remove-AzSqlServerOutboundFirewallRule [-ResourceGroupName] <String> [-ServerName] <String>
 [-AllowedFQDN] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [-Force] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzSqlServerOutboundFirewallRule** menghapus FQDN yang diperbolehkan tertentu dari daftar aturan firewall keluar (FQDN Yang Diizinkan) dari server Azure SQL Database yang ditentukan.

## EXAMPLES

### Contoh 1: Menghapus aturan firewall keluar
```
PS C:\>Remove-AzSqlServerOutboundFirewallRule -ServerName "Server01" -ResourceGroupName "ResourceGroup01" -AllowedFQDN "OutboundFirewallRule01"

ResourceGroupName : ResourceGroup01
ServerName        : Server01
AllowedFQDN       : OutboundFirewallRule01
```

Perintah ini menghapus FQDN yang diperbolehkan bernama OutboundFirewallRule01 dari daftar aturan firewall keluar di server bernama Server01.

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

### -AllowedfQDN
Menentukan nama domain yang diperbolehkan sepenuhnya memenuhi syarat (FQDN) dalam daftar aturan firewall keluar.

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

### -Paksa
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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.OutboundFirewallRules.Model.AzureSqlServerOutboundFirewallRulesModel

## NOTES

## RELATED LINKS

[Get-AzSqlServerOutboundFirewallRule](./Get-AzSqlServerOutboundFirewallRule.md)

[New-AzSqlServerOutboundFirewallRule](./New-AzSqlServerOutboundFirewallRule.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
