---
external help file: ''
Module Name: Az.PostgreSql
online version: https://docs.microsoft.com/powershell/module/az.postgresql/new-azpostgresqlflexibleserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PostgreSql/help/New-AzPostgreSqlFlexibleServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PostgreSql/help/New-AzPostgreSqlFlexibleServer.md
ms.openlocfilehash: 7a366efeb546909fdbc496c3dae130851c99e961
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136389460"
---
# New-AzPostgreSqlFlexibleServer

## SYNOPSIS
Membuat server baru.

## SYNTAX

```
New-AzPostgreSqlFlexibleServer [-Name <String>] [-ResourceGroupName <String>] [-SubscriptionId <String>]
 [-AdministratorLoginPassword <SecureString>] [-AdministratorUserName <String>] [-BackupRetentionDay <Int32>]
 [-HaEnabled <String>] [-Location <String>] [-PrivateDnsZone <String>] [-PublicAccess <String>]
 [-Sku <String>] [-SkuTier <String>] [-StorageInMb <Int32>] [-Subnet <String>] [-SubnetPrefix <String>]
 [-Tag <Hashtable>] [-Version <ServerVersion>] [-Vnet <String>] [-VnetPrefix <String>] [-Zone <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat server baru.

## EXAMPLES

### Contoh 1: Membuat server fleksibel PostgreSql baru dengan argumen
```powershell
PS C:\> New-AzPostgreSqlFlexibleServer -Name postgresql-test -ResourceGroupName PowershellPostgreSqlTest \
-Location eastus -AdministratorUserName postgresqltest -AdministratorLoginPassword $password -Sku Standard_D2s_v3 -SkuTier GeneralPurpose -Version 12 -StorageInMb 131072 -PublicAccess none

Checking the existence of the resource group PowershellPostgreSqlTest ...
Resource group PowershellPostgreSqlTest exists ? : True
Creating PostgreSQL server postgresql-test in group PostgreSqlTest...
Your server postgresql-test is using sku Standard_D2s_v3 (Paid Tier). Please refer to https://aka.ms/postgresql-pricing for pricing details

Name                Location  SkuName         SkuTier        AdministratorLogin StorageSizeGb
----                --------  -------         -------        ------------------ -------------
postgresql-test     East US   Standard_D2s_v3 GeneralPurpose daeunyim           128

```



### Contoh 2: Membuat server fleksibel PostgreSql baru dengan pengaturan default
```powershell
PS C:\> $server = New-AzPostgreSqlFlexibleServer

Creating resource group group00000000...
Creating PostgreSQL server server00000000 in group group00000000...
Your server postgresql-test is using sku Standard_D2s_v3 (Paid Tier). Please refer to https://aka.ms/postgresql-pricing for pricing details

Name                Location  SkuName         SkuTier        AdministratorLogin StorageSizeGb
----                --------  -------         -------        ------------------ -------------
postgresql-test     East US   Standard_D2s_v3 GeneralPurpose daeunyim           128
```

Cmdlet ini membuat server fleksibel PostgreSql dengan nilai parameter default dan menyediakan server dengan akses publik yang diaktifkan.
Nilai default lokasi adalah US Timur 2, Sku adalah Standard_D2s_v3, Sku tier adalah GeneralPurpose, dan ukuran penyimpanan adalah 128GiB.


Jika Anda ingin menemukan kata sandi yang dibuat secara otomatis untuk server Anda, gunakan ConvertFrom-SecureString untuk mengonversi properti 'SecuredPassword' menjadi teks biasa.
(Misalnya $server. SecuredPassword | ConvertFrom-SecureString -AsPlainText)

### Contoh 3: Membuat server fleksibel PostgreSql baru dengan Subnet yang sudah ada
```powershell
PS C:\> $Subnet = '/subscriptions/00000000-0000-0000-0000-0000000000/resourceGroups/PowershellPostgreSqlTest/providers/Microsoft.Network/virtualNetworks/vnetname/subnets/subnetname'
PS C:\> $DnsZone = '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/postgresqltest/providers/Microsoft.Network/privateDnsZones/testserver.private.postgres.database.azure.com'
PS C:\> New-AzPostgreSqlFlexibleServer  -ResourceGroupName postgresqltest -ServerName testserver -Subnet $Subnet -PrivateDnsZone $DnsZone

Resource group PowershellPostgreSqlTest exists ? : True
You have supplied a subnet Id. Verifying its existence...
Creating PostgreSQL server testserver in group PowershellPostgreSqlTest...
Your server server00000000 is using sku Standard_D2s_v3 (Paid Tier). Please refer to https://aka.ms/postgresql-pricing for pricing details
Creating database flexibleserverdb...

Name                Location  SkuName         SkuTier        AdministratorLogin StorageSizeGb
----                --------  -------         -------        ------------------ -------------
postgresql-test     East US   Standard_D2s_v3 GeneralPurpose daeunyim           128

```

Cmdlet ini membuat server fleksibel PostgreSql dengan Id Subnet yang sudah ada yang disediakan oleh pengguna.
Subnet akan didelegasikan ke server fleksibel PostgreSQL jika belum didelegasikan.
Anda tidak dapat menggunakan subnet yang didelegasikan ke layanan berbeda.
subnet bisa berada dalam grup sumber daya berbeda.

### Contoh 4: Membuat server fleksibel PostgreSql baru dengan nama jaringan virtual dan subnet
```powershell
PS C:\> New-AzPostgreSqlFlexibleServer -Name postgresql-test -ResourceGroupName PowershellPostgreSqlTest -Vnet postgresql-vnet -Subnet postgresql-subnet -VnetPrefix 10.0.0.0/16 -SubnetPrefix 10.0.0.0/24 -PrivateDnsZone /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/PowershellPostgreSqlTest/providers/Microsoft.Network/privateDnsZones/postgresql-test.private.postgres.database.azure.com

Resource group PowershellPostgreSqlTest exists ? : True
Creating new vnet postgresql-vnet in resource group PowershellPostgreSqlTest
Creating new subnet postgresql-subnet in resource group PowershellPostgreSqlTest and delegating it to Microsoft.DBforPostgreSQL/flexibleServers
Creating PostgreSQL server postgresql-test in group PowershellPostgreSqlTest...
Your server postgresql-test is using sku Standard_D2s_v3 (Paid Tier). Please refer to https://aka.ms/postgresql-pricing for pricing details
Creating database flexibleserverdb...

Name                Location  SkuName         SkuTier        AdministratorLogin StorageSizeGb
----                --------  -------         -------        ------------------ -------------
postgresql-test     East US   Standard_D2s_v3 GeneralPurpose daeunyim           128

```

Cmdlet ini membuat server fleksibel PostgreSql dengan nama vnet, nama subnet, prefiks vnet, dan prefiks subnet.
Jika jaringan virtual dan subnet tidak ada, cmdlet akan membuatnya.

### Contoh 5: Membuat server fleksibel PostgreSql baru dengan jaringan virtual
```powershell
PS C:\> $Vnet = 'vnetname'
PS C:\> New-AzPostgreSqlFlexibleServer -ResourceGroupName PowershellPostgreSqlTest -Vnet $Vnet -PrivateDnsZone /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/PowershellPostgreSqlTest/providers/Microsoft.Network/privateDnsZones/testserver.private.postgres.database.azure.com

or

PS C:\> $Vnet = '/subscriptions/00000000-0000-0000-0000-0000000000/resourceGroups/PowershellPostgreSqlTest/providers/Microsoft.Network/virtualNetworks/vnetname'
PS C:\> New-AzPostgreSqlFlexibleServer  -ResourceGroupName PowershellPostgreSqlTest -Vnet $Vnet -PrivateDnsZone /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/PowershellPostgreSqlTest/providers/Microsoft.Network/privateDnsZones/testserver.private.postgres.database.azure.com

Resource group PowershellPostgreSqlTest exists ? : True
You have supplied a vnet Id/name. Verifying its existence...
Creating new vnet vnetname in resource group PowershellPostgreSqlTest
Creating new subnet Subnetserver00000000 in resource group PowershellPostgreSqlTest and delegating it to Microsoft.DBforPostgreSQL/flexibleServers
Creating PostgreSQL server server00000000 in group PowershellPostgreSqlTest...
Your server server00000000 is using sku Standard_D2s_v3 (Paid Tier). Please refer to https://aka.ms/postgresql-pricing for pricing details
Creating database flexibleserverdb...

Name                Location  SkuName         SkuTier        AdministratorLogin StorageSizeGb
----                --------  -------         -------        ------------------ -------------
postgresql-test     East US   Standard_D2s_v3 GeneralPurpose daeunyim           128
```

Cmdlet ini membuat server fleksibel PostgreSql dengan id vnet atau nama vnet yang disediakan oleh pengguna.
Jika jaringan virtual tidak ada, cmdlet akan membuat.

### Contoh 6: Membuat server fleksibel PostgreSql baru dengan akses publik ke semua IP
```powershell
PS C:\> New-AzPostgreSqlFlexibleServer -Name postgresql-test -ResourceGroupName PowershellPostgreSqlTest -PublicAccess All

Resource group PowershellPostgreSqlTest exists ? : True
Creating PostgreSQL server postgresql-test in group PowershellPostgreSqlTest...
Your server postgresql-test is using sku Standard_D2s_v3 (Paid Tier). Please refer to https://aka.ms/postgresql-pricing for pricing details
Creating database flexibleserverdb...
Configuring server firewall rule to accept connections from 0.0.0.0 to 255.255.255.255

Name                Location  SkuName         SkuTier        AdministratorLogin StorageSizeGb
----                --------  -------         -------        ------------------ -------------
postgresql-test     East US   Standard_D2s_v3 GeneralPurpose daeunyim           128
```

Cmdlet ini membuat server fleksibel PostgreSql terbuka ke semua alamat IP.

### Contoh 7: Membuat server fleksibel PostgreSql baru dengan firewall
```powershell
PS C:\> New-AzPostgreSqlFlexibleServer -Name postgresql-test -ResourceGroupName PowershellPostgreSqlTest -PublicAccess 10.10.10.10-10.10.10.12

Resource group PowershellPostgreSqlTest exists ? : True
Creating PostgreSQL server postgresql-test in group PowershellPostgreSqlTest...
Your server postgresql-test is using sku Standard_D2s_v3 (Paid Tier). Please refer to https://aka.ms/postgresql-pricing for pricing details
Creating database flexibleserverdb...
Configuring server firewall rule to accept connections from 10.10.10.10 to 10.10.10.12

Name                Location  SkuName         SkuTier        AdministratorLogin StorageSizeGb
----                --------  -------         -------        ------------------ -------------
postgresql-test     East US   Standard_D2s_v3 GeneralPurpose daeunyim           128

```

Cmdlet ini membuat server fleksibel PostgreSql terbuka ke alamat IP tertentu.

## PARAMETERS

### -AdministratorLoginPassword
Kata sandi administrator.
Minimal 8 karakter dan maksimal 128 karakter.
Kata sandi harus berisi karakter dari tiga kategori berikut: huruf besar Bahasa Inggris, huruf kecil Bahasa Inggris, angka, dan karakter non-alfanumerik.

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
Setelah ditetapkan, pengaturan tidak dapat diubah.

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

### -BackupRetentionDay
Pencadangan hari penyimpanan untuk server.
Hitungan hari antara 7 dan 35.

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

### -HaEnabled
Mengaktifkan atau menonaktifkan fitur ketersediaan tinggi.
Nilai yang diperbolehkan: Diaktifkan, Dinonaktifkan

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

### -Lokasi
Lokasi tempat sumber daya berada.

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

### -Nama
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

### -PublicAccess
Menentukan akses publik.
Masukkan satu atau beberapa rentang alamat IP untuk disertakan dalam daftar IP yang diperbolehkan.
Rentang alamat IP harus memiliki garis putus-putus dan tidak berisi spasi.
Menentukan 0.0.0.0 memungkinkan akses publik dari sumber daya apa pun yang digunakan dalam Azure untuk mengakses server Anda.
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
Nama grup sumber daya yang berisi sumber daya, Anda dapat memperoleh nilai ini dari API Azure Resource Manager atau portal.

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
Nama sku, biasanya, tier + keluarga + inti, misalnya Standard_B1ms, Standard_D2s_v3.

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
Menghitung tingkatan server.
Nilai yang diterima: Rentetan, GeneralPurpose, Memory Optimized.
Default: Rentetan.

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

### -StorageInMb
Penyimpanan maks diperbolehkan untuk server.

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
Nama atau Id Subnet atau nama Subnet yang sudah ada untuk dibuat.
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

### -SubnetPrefix
Prefiks alamat IP subnet untuk digunakan ketika membuat vnet baru dalam format CIDR.
Nilai default adalah 10.0.0.0/24.

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
Metadata khusus aplikasi dalam bentuk pasangan nilai kunci.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.PostgreSql.Support.ServerVersion
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vnet
Nama atau Id jaringan virtual yang sudah ada atau nama jaringan virtual yang baru untuk dibuat.
Nama harus antara 2 hingga 64 karakter.
Nama harus diawali dengan huruf atau angka, diakhiri dengan huruf, angka atau garis bawah, dan mungkin hanya berisi huruf, angka, garis bawah, titik, atau tanda hubung.

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
Prefiks alamat IP yang digunakan ketika membuat vnet baru dalam format CIDR.
Nilai default adalah 10.0.0.0/16.

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

