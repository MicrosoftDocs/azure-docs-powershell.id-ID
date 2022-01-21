---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RedisCache.dll-Help.xml
Module Name: Az.RedisCache
ms.assetid: 81179AFE-6524-4F59-8BC2-3E152F51D1DD
online version: https://docs.microsoft.com/powershell/module/az.rediscache/new-azrediscache
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/New-AzRedisCache.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/New-AzRedisCache.md
ms.openlocfilehash: bcfef76a59d60598dc3a96c15a3f132e1b61fee6
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136536893"
---
# New-AzRedisCache

## SYNOPSIS
Membuat Cache Redis.

## SYNTAX

```
New-AzRedisCache -ResourceGroupName <String> -Name <String> -Location <String> [-Size <String>] [-Sku <String>]
 [-RedisConfiguration <Hashtable>] [-EnableNonSslPort <Boolean>] [-TenantSettings <Hashtable>]
 [-ShardCount <Int32>] [-MinimumTlsVersion <String>] [-SubnetId <String>] [-StaticIP <String>]
 [-Tag <Hashtable>] [-Zone <String[]>] [-RedisVersion <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRedisCache** membuat Cache Azure Redis.

## EXAMPLES

### Contoh 1: Membuat Cache Redis
```
PS C:\>New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "North Central US"

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/mycache
          Location           : North Central US
          Name               : MyCache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net 
          Port               : 6379
          ProvisioningState  : creating
          SslPort            : 6380
          RedisConfiguration : {}
          EnableNonSslPort   : False
          RedisVersion       : 2.8
          Size               : 1GB
          Sku                : Standard
          Tag                : {}
          Zone               : []
```

Perintah ini akan membuat Cache Redis.

### Contoh 2: Membuat Cache Redis SKU Standar
```
PS C:\>New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "North Central US" -Size 250MB -Sku "Standard" -RedisConfiguration @{"maxmemory-policy" = "allkeys-random"} -Force

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : North Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : creating
          SslPort            : 6380
          RedisConfiguration : {[maxmemory-policy, allkeys-random]} 
          EnableNonSslPort   : False
          RedisVersion       : 2.8
          Size               : 250MB
          Sku                : Standard
          Tag                : {}
          Zone               : []
```

Cmdlet ini membuat cache menggunakan Cache Azure untuk Redis.

### Contoh 3: Membuat Cache Tak Perlu Zona 

```
PS C:\> New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "Central US" -Size P1 -Sku "Premium" -Zone @("1","2")

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : creating
          SslPort            : 6380
          RedisConfiguration : {[maxmemory-policy, allkeys-random], [maxclients, 7500], [maxmemory-reserved, 200],
                                [maxfragmentationmemory-reserved, 300]...} 
          EnableNonSslPort   : False
          RedisVersion       : 4.0.14
          Size               : 6GB
          Sku                : Premium
          Tag                : {}
          Zone               : {1, 2}
```
Perintah ini membuat cache Azure untuk instans Redis dalam beberapa zona.

### Contoh 4: Buat Jaringan Virtual aktifkan Cache

Persyaratan untuk membuat Jaringan Virtual mengaktifkan cache.
1. Buat jaringan virtual dalam grup sumber daya yang sama tempat Anda ingin membuat cache redis. Anda bisa membuat jaringan virtual dari [perintah powershell New-AzVirtualNetwork.](./../../../Network/Network/help/New-AzVirtualNetwork.md)
1. Anda akan memerlukan SubnetID untuk VNET yang mengaktifkan cache. Sintaks SubnetID diberikan di bawah ini.

Format SubnetID: /subscriptions/{subid}/resourceGroups/{resourceGroupName}/providers/Microsoft.ClassicNetwork/VirtualNetworks/{vnetName}/subnets/{subnetName}

```
PS C:\> New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "Central US" -Size P1 -Sku "Premium" -SubnetId "/subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Network/virtualNetworks/MyNet/subnets/MySubnet"

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : creating
          SslPort            : 6380
          RedisConfiguration : {[maxmemory-policy, allkeys-random], [maxclients, 7500], [maxmemory-reserved, 200],
                                [maxfragmentationmemory-reserved, 300]...} 
          EnableNonSslPort   : False
          RedisVersion       : 4.0.14
          Size               : 6GB
          Sku                : Premium
          SubnetId           : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Network/virtualNetworks/MyNet/subnets/MySubnet
          StaticIP           : 10.0.0.4  
          Tag                : {}
          Zone               : []
```

### Contoh 5: Mengonfigurasi persistensi data untuk suatu Premium Cache Azure untuk Redis

Persistensi menulis Redis data ke akun Azure Storage yang Anda miliki dan kelola. Jadi sebelum mengonfigurasi persistensi data Anda harus memiliki akun [penyimpanan di](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-create?tabs=azure-powershell) grup sumber daya yang sama. Pilih akun penyimpanan di kawasan dan langganan yang sama dengan cache, lalu akun Premium Storage direkomendasikan karena penyimpanan premium memiliki throughput yang lebih tinggi.

Setelah membuat akun penyimpanan, dapatkan string koneksi akun penyimpanan menggunakan prosedur ini.

1. Jalankan perintah ini **Get-AzStorageAccountKey -ResourceGroupName $resourceGroupName -Name $storageAccountName** di powershell.
1. Dari output di atas, salin kunci apa pun.
1. Masukkan kunci akun penyimpanan dan nama akun penyimpanan dalam format di bawah ini untuk mendapatkan string koneksi akun penyimpanan Anda.

Format String Koneksi :- "DefaultEndpointsProtocol=https; AccountName={storageAccountName}; AccountKey={storageAccountKey}; Endpoint Vefix=core.windows.net"</br>

Anda harus memiliki pengaturan konfigurasi Redis tertentu untuk mengaktifkan persistensi data.  

Untuk mengaktifkan cadangan RDB
-  rdb-backup-enabled (Set true atau false)
-  rdb-storage-connection-string (Beri string koneksi dalam format di atas.)    
-  rdb-backup-frequency (Mengatur interval pencadangan dalam menit. Anda hanya dapat memilih dari - 15, 30, 60, 360, 720 dan 1440 menit.)  
    
```
PS C:\> New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "Central US" -Size P1 -Sku "Premium" -RedisConfiguration @{"rdb-backup-enabled" = "true"; "rdb-storage-connection-string" = "DefaultEndpointsProtocol=https;AccountName=mystorageaccount;AccountKey=pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=;EndpointSuffix=core.windows.net"; "rdb-backup-frequency" = "30"}

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : creating
          SslPort            : 6380
          RedisConfiguration : {[maxmemory-policy, allkeys-random], [maxclients, 7500], [maxmemory-reserved, 200],
                                [maxfragmentationmemory-reserved, 300], [rdb-backup-enabled, true]....} 
          EnableNonSslPort   : False
          RedisVersion       : 4.0.14
          Size               : 6GB
          Sku                : Premium
          Tag                : {}
          Zone               : []
```

### Contoh 6: Mengonfigurasi persistensi data untuk suatu Premium Azure untuk Redis - Cadangan AOF diaktifkan

Untuk cadangan AOF yang diaktifkan.
-  aof-backup-enabled (Set true or false),
-  aof-storage-connection-string-0 (Berikan string koneksi dalam format di atas.)
-  aof-storage-connection-string-1 (Secara opsional Anda bisa mengonfigurasi akun penyimpanan lain. Jika akun penyimpanan kedua dikonfigurasi, tulisan di ke singgahan replika ditulis ke akun penyimpanan kedua.) 

```
PS C:\> New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "Central US" -Size P1 -Sku "Premium" -RedisConfiguration @{"aof-backup-enabled" = "true"; "aof-storage-connection-string-0" = "DefaultEndpointsProtocol=https;AccountName=mystorageaccount;AccountKey=pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=;EndpointSuffix=core.windows.net"}

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : creating
          SslPort            : 6380
          RedisConfiguration : {[maxmemory-policy, allkeys-random], [maxclients, 7500], [maxmemory-reserved, 200],
                                [maxfragmentationmemory-reserved, 300], [aof-backup-enabled, true]...} 
          EnableNonSslPort   : False
          RedisVersion       : 4.0.14
          Size               : 6GB
          Sku                : Premium
          Tag                : {}
          Zone               : []
```

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

### -EnableNonSslPort
Menunjukkan apakah port non-SSL diaktifkan.
Nilai default dinonaktifkan $False (port non-SSL dinonaktifkan).

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi untuk membuat Cache Redis.
Nilai valid adalah: 
- As Tengah Utara
- As Tengah Selatan
- AS Tengah
- Eropa Barat
- Eropa Utara
- AS Barat
- AS Timur
- AS Timur 2
- Jepang Timur
- Jepang Barat
- Brasil Selatan
- Asia Tenggara
- Asia Timur
- Australia Timur
- Australia Tenggara

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumTlsVersion
Tentukan versi TLS yang diperlukan oleh klien untuk disambungkan ke cache.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama Cache Redis untuk dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RedisConfiguration
Menentukan Pengaturan konfigurasi Redis.
Nilai yang dapat diterima untuk parameter ini adalah:
- rdb-backup-enabled.
Menentukan bahwa Redis data persistensi diaktifkan.
Premium tier saja.
- rdb-storage-connection-string.
Menentukan string koneksi ke akun Storage untuk Persistensi data Redis.
Premium tier saja.
- rdb-backup-frequency.
Menentukan frekuensi pencadangan untuk persistensi data Redis.
Premium tier saja. 
- max reserved.
Mengonfigurasi memori yang dicadangkan untuk proses non-cache.
Standar dan Premium tingkat. 
- max cookie-policy.
Mengonfigurasi kebijakan pembatalan untuk cache.
Semua tingkatan harga. 
- notify-keyspace-events.
Mengonfigurasi pemberitahuan keyspace.
Tingkatan standar dan premium. 
- hash-max-ziplist-entries.
Mengonfigurasi optimisasi memori untuk tipe data agregat kecil.
Standar dan Premium tingkat. 
- hash-max-ziplist-value.
Mengonfigurasi optimisasi memori untuk tipe data agregat kecil.
Standar dan Premium tingkat. 
- set-max-intset-entries.
Mengonfigurasi optimisasi memori untuk tipe data agregat kecil.
Standar dan Premium tingkat. 
- zset-max-ziplist-entries.
Mengonfigurasi optimisasi memori untuk tipe data agregat kecil.
Standar dan Premium tingkat. 
- zset-max-ziplist-value.
Mengonfigurasi optimisasi memori untuk tipe data agregat kecil.
Standar dan Premium tingkat. 
- database anda.
Mengonfigurasi jumlah database.
Properti ini hanya dapat dikonfigurasi di pembuatan singgahan.
Standar dan Premium tingkat.
Untuk informasi selengkapnya, lihat Mengelola Cache Azure Redis dengan Azure PowerShell http://go.microsoft.com/fwlink/?LinkId=800051 ( http://go.microsoft.com/fwlink/?LinkId=800051) .

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RedisVersion
Versi Redis. Nilai valid: 4, 6

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya untuk membuat Cache Redis.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScountCount
Menentukan jumlah s node untuk dibuat pada cache kluster Premium baru.
Nilai yang dapat diterima untuk parameter ini adalah:
- 1
- 2
- 3
- 4
- 5
- 6
- 7
- 8
- 9 
- 10

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Size
Menentukan ukuran Cache Redis.
Nilai valid adalah: 
- P1
- P2
- P3
- P4
- P5
- C0
- C1
- C2
- C3
- C4
- C5
- C6
- 250MB
- 1GB
- 2,5GB
- 6GB
- 13GB
- 26GB
- 53GB Nilai default adalah 1GB atau C1.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
Menentukan SKU Cache Redis untuk dibuat.
Nilai valid adalah: 
- Dasar
- Standar
- Premium Nilai defaultnya adalah Standar.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, Standard, Premium

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StaticIP
Menentukan alamat IP unik dalam subnet untuk Cache Redis.
Jika Anda tidak menentukan nilai untuk parameter ini, cmdlet ini memilih alamat IP dari subnet.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubnetId
ID sumber daya penuh subnet dalam jaringan virtual untuk menyebarkan Cache Azure untuk Redis di.
Format contoh: /subscriptions/{subid}/resourceGroups/{resourceGroupName}/Microsoft. {Network| ClassicNetwork}/VirtualNetworks/{vnetName}/subnets/{subnetName}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Tabel hash yang mewakili tag.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TenantSettings
Parameter ini sudah tidak berlaku lagi.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
Daftar kawasan Azure [dengan zona Ketersediaan.](https://docs.microsoft.com/en-us/azure/availability-zones/az-region#azure-services-supporting-availability-zones)

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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

### System.String

### System.Collections.Hashtable

### System.Nullable'1[[System.Boolean, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.String[]

## OUTPUTS

### Microsoft.Azure.Commands.RedisCache.Models.RedisCacheAttributesWithAccessKeys

## CATATAN

## RELATED LINKS

[Get-AzRedisCache](./Get-AzRedisCache.md)

[Remove-AzRedisCache](./Remove-AzRedisCache.md)

[Set-AzRedisCache](./Set-AzRedisCache.md)


