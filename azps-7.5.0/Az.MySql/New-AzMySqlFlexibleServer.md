---
external help file: ''
Module Name: Az.MySql
online version: https://docs.microsoft.com/powershell/module/az.mysql/new-azmysqlflexibleserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/New-AzMySqlFlexibleServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/New-AzMySqlFlexibleServer.md
ms.openlocfilehash: 318d0e8a918debd460e32ee29b3f5a005c6881a4
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145794410"
---
# New-AzMySqlFlexibleServer

## SYNOPSIS
Membuat server fleksibel MySQL baru.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.mysql/new-azmysqlflexibleserver) untuk informasi terbaru.

## SYNTAX

```
New-AzMySqlFlexibleServer [-Name <String>] [-ResourceGroupName <String>] [-SubscriptionId <String>]
 [-AdministratorLoginPassword <SecureString>] [-AdministratorUserName <String>] [-BackupRetentionDay <Int32>]
 [-HighAvailability <String>] [-Iops <Int32>] [-Location <String>] [-PrivateDnsZone <String>]
 [-PublicAccess <String>] [-Sku <String>] [-SkuTier <String>] [-StorageAutogrow <StorageAutogrow>]
 [-StorageInMb <Int32>] [-Subnet <String>] [-SubnetPrefix <String>] [-Tag <Hashtable>]
 [-Version <ServerVersion>] [-Vnet <String>] [-VnetPrefix <String>] [-Zone <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat server fleksibel MySQL baru.

## EXAMPLES

### Contoh 1: Membuat server fleksibel MySql baru dengan argumen
```powershell
New-AzMySqlFlexibleServer -Name mysql-test -ResourceGroupName PowershellMySqlTest \
-Location eastus -AdministratorUserName mysqltest -AdministratorLoginPassword $password -Sku Standard_D2ds_v4 -SkuTier Burstable -Version 12 -StorageInMb 20480 -PublicAccess none -Zone 1 -BackupRetentionDay 10 -StorageAutogrow Enabled -Iops 500 -HighAvailability ZoneRedundant
```

```output
Checking the existence of the resource group PowershellMySqlTest ...
Resource group PowershellMySqlTest exists ? : True
Creating MySQL server mysql-test in group MySqlTest...
Your server mysql-test is using sku Standard_B1ms (Paid Tier). Please refer to https://aka.ms/mysql-pricing for pricing details

Name         Location  SkuName             SkuTier           AdministratorLogin  Version StorageSizeGb
----         --------  -------             -------           ------------------  ------- -------------
mysql-test   East US   Standard_D2ds_v4    GeneralPurpose    admin                5.7     20

```



### Contoh 2: Membuat server fleksibel MySql baru dengan pengaturan default
```powershell
New-AzMySqlFlexibleServer
```

```output
Creating resource group group00000000...
Creating new vnet VNETserver00000000 in resource group group00000000
Creating new subnet Subnetserver00000000 in resource group group00000000 and delegating it to Microsoft.DBforMySQL/flexibleServers
Creating MySQL server server00000000 in group group00000000...
Your server mysql-test is using sku Standard_B1ms (Paid Tier). Please refer to https://aka.ms/mysql-pricing for pricing details
Creating database flexibleserverdb...

Name         Location  SkuName          SkuTier        AdministratorLogin Version StorageSizeGb
----         --------  -------          -------        ------------------ ------- -------------
mysql-test   West US 2 Standard_B1ms    Burstable      admin              5.7     32
```

Cmdlet ini membuat server fleksibel MySql dengan nilai parameter default dan menyediakan server di dalam jaringan virtual baru dan memiliki subnet yang didelegasikan ke server.
Nilai default lokasi adalah US Barat 2, Sku adalah Standard_B1ms, tingkat Sku burstable, dan ukuran penyimpanan adalah 10GiB.


Jika Anda ingin menemukan kata sandi yang dibuat otomatis untuk server Anda, gunakan ConvertFrom-SecureString untuk mengonversi properti 'SecuredPassword' menjadi teks biasa.

(Misalnya, $server. | SecuredPassword ConvertFrom-SecureString -AsPlainText)

### Contoh 3: Membuat server fleksibel MySql baru dengan Subnet yang ada
```powershell
$Subnet = '/subscriptions/00000000-0000-0000-0000-0000000000/resourceGroups/PowershellPostgreSqlTest/providers/Microsoft.Network/virtualNetworks/vnetname/subnets/subnetname'
$DnsZone = '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/postgresqltest/providers/Microsoft.Network/privateDnsZones/testserver.private.mysql.database.azure.com'
New-AzMySqlFlexibleServer  -ResourceGroupName postgresqltest -ServerName testserver -Subnet $Subnet -PrivateDnsZone $DnsZone
```

```output
Resource group PowershellPostgreSqlTest exists ? : True
You have supplied a subnet Id. Verifying its existence...
Creating PostgreSQL server testserver in group PowershellPostgreSqlTest...
Your server server00000000 is using sku Standard_B1ms (Paid Tier). Please refer to https://aka.ms/postgresql-pricing for pricing details
Creating database flexibleserverdb...

Name         Location  SkuName          SkuTier        AdministratorLogin Version StorageSizeGb
----         --------  -------          -------        ------------------ ------- -------------
mysql-test   West US 2 Standard_B1ms    Burstable      admin              5.7     32

```

Cmdlet ini membuat server fleksibel PostgreSql dengan Id Subnet yang ada yang disediakan oleh pengguna.
Subnet akan didelegasikan ke server fleksibel PostgreSQL jika belum didelegasikan.
Anda tidak dapat menggunakan subnet yang didelegasikan ke layanan yang berbeda.

### Contoh 4: Membuat server fleksibel MySql baru dengan jaringan virtual dan nama subnet
```powershell
$DnsZone = '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/postgresqltest/providers/Microsoft.Network/privateDnsZones/testserver.private.mysql.database.azure.com'
New-AzMySqlFlexibleServer -Name mysql-test -ResourceGroupName PowershellMySqlTest -Vnet mysql-vnet -Subnet mysql-subnet -VnetPrefix 10.0.0.0/16 -SubnetPrefix 10.0.0.0/24 -PrivateDnsZone $DnsZone
```

```output
Resource group PowershellMySqlTest exists ? : True
Creating new vnet mysql-vnet in resource group PowershellMySqlTest
Creating new subnet mysql-subnet in resource group PowershellMySqlTest and delegating it to Microsoft.DBforMySQL/flexibleServers
Creating MySQL server mysql-test in group PowershellMySqlTest...
Your server mysql-test is using sku Standard_B1ms (Paid Tier). Please refer to https://aka.ms/mysql-pricing for pricing details
Creating database flexibleserverdb...

Name         Location  SkuName          SkuTier        AdministratorLogin Version StorageSizeGb
----         --------  -------          -------        ------------------ ------- -------------
mysql-test   West US 2 Standard_B1ms    Burstable      admin              5.7     32

```

Cmdlet ini membuat server fleksibel MySql dengan nama vnet, nama subnet, awalan vnet, dan awalan subnet.
Jika jaringan virtual dan subnet tidak ada, cmdlet akan membuatnya.

### Contoh 5: Membuat server fleksibel MySql baru dengan jaringan virtual
```powershell
$Vnet = 'vnetname'
$DnsZone = '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/postgresqltest/providers/Microsoft.Network/privateDnsZones/testserver.private.mysql.database.azure.com'
New-AzMySqlFlexibleServer -ResourceGroupName PowershellMySqlTest -Vnet $Vnet -PrivateDnsZone $DnsZone

or

$Vnet = '/subscriptions/00000000-0000-0000-0000-0000000000/resourceGroups/PowershellMySqlTest/providers/Microsoft.Network/virtualNetworks/vnetname'
New-AzMySqlFlexibleServer  -ResourceGroupName PowershellMySqlTest -Vnet $Vnet -PrivateDnsZone $DnsZone
```

```output
Resource group PowershellMySqlTest exists ? : True
You have supplied a vnet Id/name. Verifying its existence...
Creating new vnet vnetname in resource group PowershellMySqlTest
Creating new subnet Subnetserver00000000 in resource group PowershellMySqlTest and delegating it to Microsoft.DBforMySQL/flexibleServers
Creating MySQL server server00000000 in group PowershellMySqlTest...
Your server server00000000 is using sku Standard_B1ms (Paid Tier). Please refer to https://aka.ms/mysql-pricing for pricing details
Creating database flexibleserverdb...

Name         Location  SkuName          SkuTier        AdministratorLogin Version StorageSizeGb
----         --------  -------          -------        ------------------ ------- -------------
mysql-test   West US 2 Standard_B1ms    Burstable      admin              5.7     32

```

Cmdlet ini membuat server fleksibel MySql dengan id vnet atau nama vnet yang disediakan oleh pengguna.
Jika jaringan virtual tidak ada, cmdlet akan membuatnya.

### Contoh 6: Membuat server fleksibel MySql baru dengan akses publik ke semua IP
```powershell
New-AzMySqlFlexibleServer -Name mysql-test -ResourceGroupName PowershellMySqlTest -PublicAccess All
```

```output
Resource group PowershellMySqlTest exists ? : True
Creating MySQL server mysql-test in group PowershellMySqlTest...
Your server mysql-test is using sku Standard_B1ms (Paid Tier). Please refer to https://aka.ms/mysql-pricing for pricing details
Creating database flexibleserverdb...
Configuring server firewall rule to accept connections from 0.0.0.0 to 255.255.255.255

Name         Location  SkuName          SkuTier        AdministratorLogin Version StorageSizeGb
----         --------  -------          -------        ------------------ ------- -------------
mysql-test   West US 2 Standard_B1ms    Burstable      admin              5.7     32
```

Cmdlet ini membuat server fleksibel MySql terbuka untuk semua alamat IP.

### Contoh 7: Membuat server fleksibel MySql baru dengan firewall
```powershell
New-AzMySqlFlexibleServer -Name mysql-test -ResourceGroupName PowershellMySqlTest -PublicAccess 10.10.10.10-10.10.10.12
```

```output
Resource group PowershellMySqlTest exists ? : True
Creating MySQL server mysql-test in group PowershellMySqlTest...
Your server mysql-test is using sku Standard_B1ms (Paid Tier). Please refer to https://aka.ms/mysql-pricing for pricing details
Creating database flexibleserverdb...
Configuring server firewall rule to accept connections from 10.10.10.10 to 10.10.10.12

Name         Location  SkuName          SkuTier        AdministratorLogin Version StorageSizeGb
----         --------  -------          -------        ------------------ ------- -------------
mysql-test   West US 2 Standard_B1ms    Burstable      admin              5.7     32

```

Cmdlet ini membuat server fleksibel MySql terbuka ke alamat IP tertentu.

## PARAMETERS

### -AdministratorLoginPassword
Kata sandi administrator.
Minimal 8 karakter dan maksimum 128 karakter.
Sandi Anda harus berisi karakter dari tiga kategori berikut: huruf besar bahasa Inggris, huruf kecil bahasa Inggris, angka, dan karakter non-alfanumerik.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdministratorUserName
Nama pengguna administrator untuk server.
Setelah diatur, itu tidak dapat diubah.

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

### -AsJob
Jalankan perintah sebagai pekerjaan.

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

### -BackupRetentionDay
Hari retensi cadangan untuk server.
Jumlah hari adalah antara 1 dan 35.

```yaml
Type: System.Int32
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

### -HighAvailability
Mengaktifkan atau menonaktifkan fitur ketersediaan tinggi.
Nilai yang diizinkan adalah 'ZoneRedundant', 'SameZone', dan 'Disabled'.
Nilai defaultnya adalah Dinonaktifkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: HaEnabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Iops
Jumlah IOPS yang akan dialokasikan untuk server ini.
Anda akan mendapatkan sejumlah IOPS gratis berdasarkan komputasi dan penyimpanan yang disediakan.
Nilai default untuk IOPS adalah IOPS gratis.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya berada.

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

### -Name
Nama server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServerName

Required: False
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
Akhiran zona dns harus sama dengan domain server yang sepenuhnya memenuhi syarat.

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

### -PublicAccess
Menentukan akses publik.
Nilai yang diizinkan: Semua, Tidak Ada, rentang alamat IP (misalnya, 1.1.1.1-1.1.5, 1.1.1.1) Menentukan 0.0.0.0 memungkinkan akses publik dari sumber daya apa pun yang disebarkan dalam Azure untuk mengakses server Anda.
Menentukan tidak ada alamat IP yang mengatur server dalam mode akses publik tetapi tidak membuat aturan firewall.

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
Nama grup sumber daya yang berisi sumber daya, Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.

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

### -Sku
Nama sku, biasanya, tingkat + keluarga + inti, misalnya Standard_B1ms, Standard_D2ds_v4.

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

### -SkuTier
Tingkat komputasi server.
Nilai yang diterima: Burstable, GeneralPurpose, Memory Optimized.
Default: Burstable.

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

### -StorageAutogrow
Aktifkan atau nonaktifkan Storage Pertumbuhan Otomatis.
Nilai defaultnya adalah Dinonaktifkan

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MySql.Support.StorageAutogrow
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageInMb
Penyimpanan maks yang diizinkan untuk server.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Nama atau Id subnet atau nama baru yang sudah ada untuk dibuat.
Gunakan ID sumber daya jika Anda ingin menggunakan subnet dari grup sumber daya yang berbeda.
Harap dicatat bahwa subnet akan didelegasikan ke Microsoft.DBforMySQL/flexibleServers.
Setelah delegasi, subnet ini tidak dapat digunakan untuk jenis sumber daya Azure lainnya.

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

### -SubnetPrefix
Awalan alamat IP subnet yang akan digunakan saat membuat vnet baru dalam format CIDR.
Nilai defaultnya adalah 10.0.0.0/24.

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

### -Tag
Metadata khusus aplikasi dalam bentuk pasangan kunci-nilai.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Versi
Versi server.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MySql.Support.ServerVersion
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vnet
Nama atau Id jaringan virtual yang ada atau nama yang baru untuk dibuat.
Nama harus antara 2 hingga 64 karakter.
Nama harus diawali dengan huruf atau angka, diakhiri dengan huruf, angka atau garis bawah, dan hanya boleh berisi huruf, angka, garis bawah, titik, atau tanda hubung.

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

### -VnetPrefix
Awalan alamat IP yang akan digunakan saat membuat vnet baru dalam format CIDR.
Nilai defaultnya adalah 10.0.0.0/16.

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

### -Zona
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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20210501.IServerAutoGenerated

## NOTES

ALIAS

## RELATED LINKS

