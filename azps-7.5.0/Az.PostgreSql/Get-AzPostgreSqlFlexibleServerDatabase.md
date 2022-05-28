---
external help file: ''
Module Name: Az.PostgreSql
online version: https://docs.microsoft.com/powershell/module/az.postgresql/get-azpostgresqlflexibleserverdatabase
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PostgreSql/help/Get-AzPostgreSqlFlexibleServerDatabase.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PostgreSql/help/Get-AzPostgreSqlFlexibleServerDatabase.md
ms.openlocfilehash: f0dafb5ee81e3461c702cb2a544e4cb7a0f3e162
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145658470"
---
# Get-AzPostgreSqlFlexibleServerDatabase

## SYNOPSIS
Mendapatkan informasi tentang database.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.postgresql/get-azpostgresqlflexibleserverdatabase) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzPostgreSqlFlexibleServerDatabase -ResourceGroupName <String> -ServerName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzPostgreSqlFlexibleServerDatabase -Name <String> -ResourceGroupName <String> -ServerName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzPostgreSqlFlexibleServerDatabase -InputObject <IPostgreSqlIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi tentang database.

## EXAMPLES

### Contoh 1: Mendapatkan database server PostgreSql
```powershell
Get-AzPostgreSqlFlexibleServerDatabase -ResourceGroupName PowershellPostgreSqlTest -ServerName postgresql-test
```

```output
Name              Charset Collation
----              ------- ---------
azure_maintenance UTF8    en_US.utf8
postgres          UTF8    en_US.utf8
azure_sys         UTF8    en_US.utf8
flexibleserverdb  UTF8    en_US.utf8
```

Mendapatkan database dari server fleksibel

### Contoh 2: Mendapatkan database server PostgreSql
```powershell
Get-AzPostgreSqlFlexibleServerDatabase -ResourceGroupName PowershellPostgreSqlTest -ServerName postgresql-test -Name flexibleserverdb
```

```output
Name             Charset Collation
----             ------- ---------
flexibleserverdb UTF8    en_US.utf8
```

Mendapatkan database server fleksibel berdasarkan nama

### Contoh 3: Mendapatkan database server PostgreSql
```powershell
Get-AzPostgreSqlFlexibleServerDatabase -InputObject /subscriptions/0000000000-0000-0000-0000-000000000000/resourceGroups/PowershellPostgreSqlTest/providers/Microsoft.DBforPostgreSQL/flexibleServers/postgresql-test/databases/flexibleserverdb
```

```output
Name             Charset Collation
----             ------- ---------
flexibleserverdb UTF8    en_US.utf8
```

Mendapatkan database server fleksibel menurut Id sumber daya

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.PostgreSql.Models.IPostgreSqlIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama database.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: DatabaseName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Nama server.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.PostgreSql.Models.IPostgreSqlIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.PostgreSql.Models.Api20210601.IDatabaseAutoGenerated

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IPostgreSqlIdentity>: Parameter Identitas
  - `[ConfigurationName <String>]`: Nama konfigurasi server.
  - `[DatabaseName <String>]`: Nama database.
  - `[FirewallRuleName <String>]`: Nama aturan firewall server.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LocationName <String>]`: Nama lokasi.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar/kecil.
  - `[SecurityAlertPolicyName <SecurityAlertPolicyName?>]`: Nama kebijakan pemberitahuan keamanan.
  - `[ServerName <String>]`: Nama server.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VirtualNetworkRuleName <String>]`: Nama aturan jaringan virtual.

## RELATED LINKS

