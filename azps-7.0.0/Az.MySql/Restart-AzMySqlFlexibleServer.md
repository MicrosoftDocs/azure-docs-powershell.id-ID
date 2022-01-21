---
external help file: ''
Module Name: Az.MySql
online version: https://docs.microsoft.com/powershell/module/az.mysql/restart-azmysqlflexibleserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Restart-AzMySqlFlexibleServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Restart-AzMySqlFlexibleServer.md
ms.openlocfilehash: fa2a717b4d647e068cd1c33337301b7d03ccaf37
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136569545"
---
# Restart-AzMySqlFlexibleServer

## SYNOPSIS
Memulai ulang server.

## SYNTAX

### RestartExpanded (Default)
```
Restart-AzMySqlFlexibleServer -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-MaxFailoverSecond <Int32>] [-RestartWithFailover <EnableStatusEnum>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Mulai ulang
```
Restart-AzMySqlFlexibleServer -Name <String> -ResourceGroupName <String> -Parameter <IServerRestartParameter>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### RestartViaIdentity
```
Restart-AzMySqlFlexibleServer -InputObject <IMySqlIdentity> -Parameter <IServerRestartParameter>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### RestartViaIdentityExpanded
```
Restart-AzMySqlFlexibleServer -InputObject <IMySqlIdentity> [-MaxFailoverSecond <Int32>]
 [-RestartWithFailover <EnableStatusEnum>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memulai ulang server.

## EXAMPLES

### Contoh 1: Mulai ulang server dengan nama sumber daya
```powershell
PS C:\> Restart-AzMySqlFlexibleServer -ResourceGroupName PowershellMySqlTest -Name mysql-test
```

Mulai ulang server menurut nama

### Contoh 2: Mulai ulang server dengan identitas
```powershell
PS C:\> $ID = "/subscriptions/<SubscriptionId>/resourceGroups/PowershellMySqlTest/providers/Microsoft.DBforMySQL/flexibleServers/mysql-test/restart"
PS C:\> Restart-AzMySqlFlexibleServer -InputObject $ID
```

Mulai ulang server menurut identitas

### Contoh 2: Mulai ulang server dengan failover
```powershell
PS C:\> Restart-AzMySqlFlexibleServer -ResourceGroupName PowershellMySqlTest -Name mysql-test -RestartWithFailover Enabled
```

Mulai ulang server dengan failover

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.IMySqlIdentity
Parameter Sets: RestartViaIdentity, RestartViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaxFailoverSecond
Waktu maksimum failover yang diperbolehkan dalam detik.

```yaml
Type: System.Int32
Parameter Sets: RestartExpanded, RestartViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama server.

```yaml
Type: System.String
Parameter Sets: Restart, RestartExpanded
Aliases: ServerName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### -Parameter
Parameter mulai ulang server.
Untuk membuat, lihat bagian CATATAN untuk properti PARAMETER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20210501.IServerRestartParameter
Parameter Sets: Restart, RestartViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

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
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: Restart, RestartExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestartWithFailover
Apakah failover ke server siaga atau tidak ketika memulai ulang server dengan ketersediaan tinggi diaktifkan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MySql.Support.EnableStatusEnum
Parameter Sets: RestartExpanded, RestartViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: Restart, RestartExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20210501.IServerRestartParameter

### Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.IMySqlIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMySqlIdentity> : Parameter Identitas
  - `[BackupName <String>]`: Nama cadangan.
  - `[ConfigurationName <String>]`: Nama konfigurasi server.
  - `[DatabaseName <String>]`: Nama database.
  - `[FirewallRuleName <String>]`: Nama aturan firewall server.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LocationName <String>]`: Nama lokasi.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SecurityAlertPolicyName <SecurityAlertPolicyName?>]`: Nama kebijakan pemberitahuan keamanan.
  - `[ServerName <String>]`: Nama server.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VirtualNetworkRuleName <String>]`: Nama aturan jaringan virtual.

PARAMETER <IServerRestartParameter> : Parameter mulai ulang server.
  - `[MaxFailoverSecond <Int32?>]`: Waktu maksimum failover yang diperbolehkan dalam detik.
  - `[RestartWithFailover <EnableStatusEnum?>]`: Apakah failover ke server siaga atau tidak ketika memulai ulang server dengan ketersediaan tinggi diaktifkan.

## RELATED LINKS

