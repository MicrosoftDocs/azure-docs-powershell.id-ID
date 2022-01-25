---
external help file: ''
Module Name: Az.PostgreSql
online version: https://docs.microsoft.com/powershell/module/az.postgresql/restore-azpostgresqlflexibleserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PostgreSql/help/Restore-AzPostgreSqlFlexibleServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PostgreSql/help/Restore-AzPostgreSqlFlexibleServer.md
ms.openlocfilehash: fa9900b53955f5a53df22096779ad4c8468f12ea
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136725373"
---
# Restore-AzPostgreSqlFlexibleServer

## SYNOPSIS
Memulihkan server dari cadangan yang sudah ada

## SYNTAX

```
Restore-AzPostgreSqlFlexibleServer -Name <String> -ResourceGroupName <String> -SourceServerName <String>
 -RestorePointInTime <DateTime> [-SubscriptionId <String>] [-PrivateDnsZone <String>] [-Subnet <String>]
 [-Zone <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memulihkan server dari cadangan yang sudah ada

## EXAMPLES

### Contoh 1: Pulihkan server PostgreSql menggunakan PointInTime Restore
```powershell
PS C:\> $restorePointInTime = (Get-Date).AddMinutes(-10)
PS C:\> Restore-AzPostgreSqlFlexibleServer -Name pg-restore -ResourceGroupName PowershellPostgreSqlTest -SourceServerName postgresql-test -Location eastus -RestorePointInTime $restorePointInTime 

Name           Location  SkuName         SkuTier        AdministratorLogin StorageSizeGb
----           --------  -------         -------        ------------------ -------------
pg-restore     East US   Standard_D2s_v3 GeneralPurpose daeunyim           128
```

Cmdlets ini memulihkan server PostgreSql menggunakan PointInTime Restore.

### Contoh 1: Pulihkan server PostgreSql menggunakan Pemulihan PointInTime dengan sumber daya jaringan yang berbeda
```powershell

PS C:\> $Subnet = '/subscriptions/00000000-0000-0000-0000-0000000000/resourceGroups/PowershellPostgreSqlTest/providers/Microsoft.Network/virtualNetworks/vnetname/subnets/subnetname'
PS C:\> $DnsZone = '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/postgresqltest/providers/Microsoft.Network/privateDnsZones/testserver.private.postgres.database.azure.com'
PS C:\> $restorePointInTime = (Get-Date).AddMinutes(-10)
PS C:\> Restore-AzPostgreSqlFlexibleServer -Name pg-restore -ResourceGroupName PowershellPostgreSqlTest -SourceServerName postgresql-test -Location eastus -RestorePointInTime $restorePointInTime -Subnet $subnet -PrivateDnsZone $DnsZone

Name           Location  SkuName         SkuTier        AdministratorLogin StorageSizeGb
----           --------  -------         -------        ------------------ -------------
pg-restore     East US   Standard_D2s_v3 GeneralPurpose daeunyim           128
```

Cmdlets ini memulihkan server PostgreSql menggunakan PointInTime Restore.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan.

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

### -Nama
Nama server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServerName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron.

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

### -PrivateDnsZone
Id zona dns privat yang sudah ada.
Anda bisa menggunakan zona dns privat dari grup sumber daya yang sama, grup sumber daya yang berbeda, atau langganan yang berbeda.
Akhiran zona dns harus sama dengan akhiran domain server yang sepenuhnya memenuhi syarat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya, Anda dapat memperoleh nilai ini dari API Azure Resource Manager atau portal.

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

### -RestorePointInTime
Titik dalam waktu untuk memulihkan dari (format ISO8601), misalnya, 2017-04-26T02:10:00+08:00.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceServerName
Nama server sumber.

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

### -Subnet
Id Subnet yang sudah ada, yang akan dibuat oleh server akses privat.
Harap perhatikan bahwa subnet akan didelegasikan ke Microsoft.DBforPostgreSQL/flexibleServers.
Setelah delegasi, subnet ini tidak dapat digunakan untuk tipe sumber daya Azure lainnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan yang mengidentifikasi langganan Azure.

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

### -Zone
Zona ketersediaan untuk menyediakan sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.PostgreSql.Models.Api20210601.IServerAutoGenerated

## CATATAN

ALIAS

## RELATED LINKS

