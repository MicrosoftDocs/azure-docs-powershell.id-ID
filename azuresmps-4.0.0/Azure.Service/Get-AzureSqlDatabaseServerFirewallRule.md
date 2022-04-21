---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: BE00A25D-3ECE-4B27-9D79-78128CFEBDB0
online version: ''
schema: 2.0.0
ms.openlocfilehash: a21e6ebdd450fcc73e83c53bebcd58ac0ec49ff0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142656433"
---
# Get-AzureSqlDatabaseServerFirewallRule

## SYNOPSIS
Mendapatkan aturan firewall untuk server Azure SQL Database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSqlDatabaseServerFirewallRule -ServerName <String> [-RuleName <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSqlDatabaseServerFirewallRule** mendapatkan aturan firewall untuk contoh Azure SQL Database Server.
Jika Anda menentukan aturan firewall menurut nama, cmdlet ini mengembalikan informasi tentang aturan firewall tersebut.
Jika tidak, cmdlet mengembalikan informasi tentang semua aturan firewall di server Azure SQL Database yang ditentukan.

## EXAMPLES

### Contoh 1: Dapatkan semua aturan firewall di server
```
PS C:\> Get-AzureSqlDatabaseServerFirewallRule -ServerName "lpqd0zbr8y"
```

Perintah ini mendapatkan semua aturan firewall di server Azure SQL Database bernama lpqd0zbr8y.

### Contoh 2: Dapatkan aturan firewall dengan menggunakan namanya
```
PS C:\> Get-AzureSqlDatabaseServerFirewallRule -ServerName "lpqd0zbr8y" -RuleName "FirewallRule24"
```

Perintah ini mendapatkan aturan firewall bernama FirewallRule24 di server bernama lpqd0zbr8y.

## PARAMETERS

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleName
Menentukan nama aturan firewall yang didapat cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Menentukan nama server.
Cmdlet ini mendapatkan aturan firewall dari server yang ditentukan parameter ini.
Tentukan nama server, bukan nama DNS yang sepenuhnya memenuhi syarat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerFirewallRuleContext

## OUTPUTS

### Ienumerable\<Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerFirewallRuleContext\>

## NOTES

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Aturan Firewall Daftar](https://msdn.microsoft.com/en-us/library/azure/dn505715.aspx)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Baru-AzureSqlDatabaseServerFirewallRule](./New-AzureSqlDatabaseServerFirewallRule.md)

[Hapus-AzureSqlDatabaseServerFirewallRule](./Remove-AzureSqlDatabaseServerFirewallRule.md)

[Set-AzureSqlDatabaseServerFirewallRule](./Set-AzureSqlDatabaseServerFirewallRule.md)


