---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/get-azsqlserveroutboundfirewallrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServerOutboundFirewallRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServerOutboundFirewallRule.md
ms.openlocfilehash: fa35929adfed3aa9f43d96ac63dc740c0cd2a050
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140480163"
---
# Get-AzSqlServerOutboundFirewallRule

## SYNOPSIS
Mendapatkan aturan firewall keluar (FQDN yang Diperbolehkan) untuk server SQL Database.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.sql/get-azsqlserveroutboundfirewallrule) untuk informasi terkini.

## SYNTAX

```
Get-AzSqlServerOutboundFirewallRule [-ResourceGroupName] <String> [-ServerName] <String>
 [-AllowedFQDN] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSqlServerOutboundFirewallRule** mendapatkan daftar FQDN yang Diperbolehkan di Aturan Firewall Keluar untuk Azure SQL Database server.
Jika Anda menentukan nama FQDN yang diperbolehkan, cmdlet ini mendapatkan informasi tentang FQDN spesifik yang diperbolehkan tersebut.

## EXAMPLES

### Contoh 1: Mendapatkan aturan firewall keluar untuk server
```
PS C:\>Get-AzSqlServerOutboundFirewallRule -ServerName "Server01" -ResourceGroupName "ResourceGroup01" -AllowedFQDN "OutboundFirewallRule01"

ResourceGroupName : ResourceGroup01
ServerName        : Server01
AllowedFQDN       : OutboundFirewallRule01

PS C:\>Get-AzSqlServerOutboundFirewallRule -ResourceGroupName "ResourceGroup01" -ServerName "Server01"

ResourceGroupName : ResourceGroup01
ServerName        : Server01
AllowedFQDN       : OutboundFirewallRule01

ResourceGroupName : ResourceGroup01
ServerName        : Server01
AllowedFQDN       : OutboundFirewallRule02

ResourceGroupName : ResourceGroup01
ServerName        : Server01
AllowedFQDN       : OutboundFirewallRule03
```

Perintah ini mendapatkan semua FQDN yang diperbolehkan dari daftar Aturan Firewall Keluar untuk server yang bernama Server01 dalam grup sumber daya bernama ResourceGroup01.

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
Menentukan nama grup sumber daya tempat SQL Server ditetapkan.

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
Menentukan nama SQL Server.

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

### -AllowedFQDN
Menentukan nama domain berkualifikasi penuh (FQDN, Fully Qualified Domain Name) yang diperbolehkan dalam daftar aturan firewall keluar.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.sql.OutboundFirewallRules.Model.AzureSqlServerOutboundFirewallRulesModel

## CATATAN

## RELATED LINKS

[New-AzSqlServerOutboundFirewallRule](./New-AzSqlServerOutboundFirewallRule.md)

[Remove-AzSqlServerOutboundFirewallRule](./Remove-AzSqlServerOutboundFirewallRule.md)

[SQL Database Dokumen](https://docs.microsoft.com/azure/sql-database/)
