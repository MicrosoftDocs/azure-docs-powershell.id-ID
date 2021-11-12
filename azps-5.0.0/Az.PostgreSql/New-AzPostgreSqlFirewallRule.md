---
external help file: ''
Module Name: Az.PostgreSql
online version: https://docs.microsoft.com/en-us/powershell/module/az.postgresql/new-azpostgresqlfirewallrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/PostgreSql/help/New-AzPostgreSqlFirewallRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/PostgreSql/help/New-AzPostgreSqlFirewallRule.md
ms.openlocfilehash: bafd0e20530198da87c1fa3ece36905e73307a42
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132408125"
---
# New-AzPostgreSqlFirewallRule

## SYNOPSIS
Membuat aturan firewall baru atau memperbarui aturan firewall yang sudah ada.

## SINTAKS

### CreateExpanded (Default)
```
New-AzPostgreSqlFirewallRule -ResourceGroupName <String> -ServerName <String> -EndIPAddress <String>
 -StartIPAddress <String> [-Name <String>] [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### AllowAll
```
New-AzPostgreSqlFirewallRule -ResourceGroupName <String> -ServerName <String> -AllowAll [-Name <String>]
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### ClientIPAddress
```
New-AzPostgreSqlFirewallRule -ResourceGroupName <String> -ServerName <String> -ClientIPAddress <String>
 [-Name <String>] [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESKRIPSI
Membuat aturan firewall baru atau memperbarui aturan firewall yang sudah ada.

## CONTOH

### Contoh 1: Membuat Aturan Firewall server PostgreSql baru
```powershell
PS C:\> New-AzPostgreSqlFirewallRule -Name rule -ResourceGroupName PostgreSqlTestRG -ServerName PostgreSqlTestServer -EndIPAddress 0.0.0.1 -StartIPAddress 0.0.0.0

Name StartIPAddress EndIPAddress
---- -------------- ------------
rule 0.0.0.0        0.0.0.1
```

Cmdlet ini membuat Aturan Firewall server PostgreSql.

### Contoh 2: Buat Aturan Firewall PostgreSql baru menggunakan -ClientIPAddress.
```powershell
PS C:\> New-AzPostgreSqlFirewallRule -ResourceGroupName PostgreSqlTestRG -ServerName PostgreSqlTestServer -ClientIPAddress 0.0.0.1

Name                                StartIPAddress EndIPAddress
----                                -------------- ------------
ClientIPAddress_2020-08-11_18-19-27 0.0.0.1        0.0.0.1
```

Cmdlet ini membuat Aturan Firewall PostgreSql menggunakan -ClientIPAddress.

### Contoh 3: Buat Aturan Firewall PostgreSql baru untuk memperbolehkan semua IP
```powershell
PS C:\> New-AzPostgreSqlFirewallRule -ResourceGroupName PostgreSqlTestRG -ServerName PostgreSqlTestServer -AllowAll

Name                         StartIPAddress EndIPAddress
----                         -------------- ------------
AllowAll_2020-08-11_18-19-27 0.0.0.0        255.255.255.255
```

Cmdlet ini membuat Aturan Firewall PostgreSql baru untuk memperbolehkan semua IP.

## PARAMETERS

### -AllowAll
Sajikan untuk memperbolehkan semua IP rentang, dari 0.0.0.0 hingga 255.255.255.255.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllowAll
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -ClientIPAddress
Klien ip tunggal aturan firewall server yang ditentukan.
Harus menggunakan format IPv4.

```yaml
Type: System.String
Parameter Sets: ClientIPAddress
Aliases:

Required: True
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

### -EndIPAddress
Alamat IP akhir aturan firewall server.
Harus menggunakan format IPv4.

```yaml
Type: System.String
Parameter Sets: CreateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama aturan firewall server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FirewallRuleName

Required: False
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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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

### -ServerName
Nama server.

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

### -StartIPAddress
Alamat IP mulai aturan firewall server.
Harus menggunakan format IPv4.

```yaml
Type: System.String
Parameter Sets: CreateExpanded
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
Parameter Sets: (All)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

## OUTPUT

### Microsoft.Azure.PowerShell.Cmdlets.PostgreSql.Models.Api20171201.IFirewallRule

## CATATAN

ALIAS

## LINK TERKAIT

