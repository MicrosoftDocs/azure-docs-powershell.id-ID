---
external help file: ''
Module Name: Az.MySql
online version: https://docs.microsoft.com/powershell/module/az.mysql/update-azmysqlserverconfigurationslist
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Update-AzMySqlServerConfigurationsList.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Update-AzMySqlServerConfigurationsList.md
ms.openlocfilehash: 6265a8d7f5bdce17d63e202e8c2d57e8612b2c6d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142806742"
---
# Update-AzMySqlServerConfigurationsList

## SYNOPSIS
Memperbarui daftar konfigurasi di server tertentu.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzMySqlServerConfigurationsList -ResourceGroupName <String> -ServerName <String>
 [-SubscriptionId <String>] [-Value <IConfiguration[]>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzMySqlServerConfigurationsList -InputObject <IMySqlIdentity> [-Value <IConfiguration[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui daftar konfigurasi di server tertentu.

## EXAMPLES

### Contoh 1: Perbarui daftar konfigurasi MySQL menurut nama
```powershell
Update-AzMySqlServerConfigurationsList -ResourceGroupName PowershellMySqlTest -ServerName mysql-test
```

Perbarui daftar konfigurasi MySQL menurut nama.

### Contoh 2: Perbarui daftar konfigurasi MySQL menurut identitas
```powershell
Get-AzMySqlServer -ResourceGroupName PowershellMySqlTest -ServerName mysql-test | Update-AzMySqlServerConfigurationsList
```

Perbarui daftar konfigurasi MySQL menurut ID.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.IMySqlIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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
Nama ini tidak peka huruf besar kecil.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
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
Parameter Sets: UpdateExpanded
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
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value
Daftar konfigurasi server.
Untuk membangun, lihat bagian CATATAN untuk properti VALUE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20171201.IConfiguration[]
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.IMySqlIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20171201.IConfiguration

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

VALUE <IConfiguration[]>: Daftar konfigurasi server.
  - `[Source <String>]`: Sumber konfigurasi.
  - `[Value <String>]`: Nilai konfigurasi.

## RELATED LINKS

