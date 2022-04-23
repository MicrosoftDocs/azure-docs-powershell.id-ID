---
external help file: ''
Module Name: Az.MySql
online version: https://docs.microsoft.com/powershell/module/az.mysql/get-azmysqlflexibleserverconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Get-AzMySqlFlexibleServerConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Get-AzMySqlFlexibleServerConfiguration.md
ms.openlocfilehash: c922a88c00c70d879f7b77205473973d0818383b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143333099"
---
# Get-AzMySqlFlexibleServerConfiguration

## SYNOPSIS
Mendapatkan informasi tentang konfigurasi server.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.mysql/get-azmysqlflexibleserverconfiguration) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzMySqlFlexibleServerConfiguration -ResourceGroupName <String> -ServerName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzMySqlFlexibleServerConfiguration -Name <String> -ResourceGroupName <String> -ServerName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzMySqlFlexibleServerConfiguration -InputObject <IMySqlIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi tentang konfigurasi server.

## EXAMPLES

### Contoh 1: Mencantumkan semua konfigurasi di server MySql yang ditentukan
```powershell
PS C:\> Get-AzMySqlFlexibleServerConfiguration -ResourceGroupName PowershellMySqlTest -ServerName mysql-test

Name                                     Value
----                                     -----
archive                                  OFF
audit_log_enabled                        OFF
audit_log_events                         CONNECTION
audit_log_exclude_users                  azure_superuser
...
wait_timeout                             28800
```

Cmdlet ini mencantumkan semua konfigurasi di server MySql yang ditentukan.

### Contoh 2: Dapatkan konfigurasi MySql yang ditentukan menurut nama
```powershell
PS C:\> Get-AzMySqlFlexibleServerConfiguration -Name wait_timeout -ResourceGroupName PowershellMySqlTest -ServerName mysql-test

Name         Value AllowedValue Source         DefaultValue
----         ----- ------------ ------         ------------
wait_timeout 28800 1-31536000   system-default 28800
```

Cmdlet ini mendapatkan konfigurasi MySql yang ditentukan berdasarkan nama.

### Contoh 3: Daftar konfigurasi menurut identitas
```powershell
PS C:\> $ID = "/subscriptions/<SubscriptionId>/resourceGroups/PowershellMySqlTest/providers/Microsoft.DBforMySQL/flexibleServers/mysql-test/configurations/wait_timeout"
Get-AzMySqlFlexibleServerConfiguration -Name wait_timeout -ResourceGroupName PowershellMySqlTest -ServerName mysql-test

Name         Value AllowedValue Source         DefaultValue
----         ----- ------------ ------         ------------
wait_timeout 28800 1-31536000   system-default 28800
```

Cmdlet ini mendapatkan konfigurasi MySql yang ditentukan menurut identitas.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.IMySqlIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama konfigurasi server.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: ConfigurationName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.IMySqlIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20210501.IConfigurationAutoGenerated

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMySqlIdentity>: Parameter Identitas
  - `[BackupName <String>]`: Nama cadangan.
  - `[ConfigurationName <String>]`: Nama konfigurasi server.
  - `[DatabaseName <String>]`: Nama database.
  - `[FirewallRuleName <String>]`: Nama aturan firewall server.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LocationName <String>]`: Nama lokasi.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[SecurityAlertPolicyName <SecurityAlertPolicyName?>]`: Nama kebijakan pemberitahuan keamanan.
  - `[ServerName <String>]`: Nama server.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VirtualNetworkRuleName <String>]`: Nama aturan jaringan virtual.

## RELATED LINKS

