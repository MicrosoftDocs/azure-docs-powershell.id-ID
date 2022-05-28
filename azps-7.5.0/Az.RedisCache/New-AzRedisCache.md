---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RedisCache.dll-Help.xml
Module Name: Az.RedisCache
ms.assetid: 81179AFE-6524-4F59-8BC2-3E152F51D1DD
online version: https://docs.microsoft.com/powershell/module/az.rediscache/new-azrediscache
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/New-AzRedisCache.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/New-AzRedisCache.md
ms.openlocfilehash: 60b603a4e8a1aa46fc4d9d3441fb29ac2f5367af
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145646640"
---
# New-AzRedisCache

## SYNOPSIS
Membuat Redis Cache.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.rediscache/new-azrediscache) untuk informasi terbaru.

## SYNTAX

```
New-AzRedisCache -ResourceGroupName <String> -Name <String> -Location <String> [-Size <String>] [-Sku <String>]
 [-RedisConfiguration <Hashtable>] [-EnableNonSslPort <Boolean>] [-TenantSettings <Hashtable>]
 [-ShardCount <Int32>] [-MinimumTlsVersion <String>] [-SubnetId <String>] [-StaticIP <String>]
 [-Tag <Hashtable>] [-Zone <String[]>] [-RedisVersion <String>] [-IdentityType <String>]
 [-UserAssignedIdentity <String[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRedisCache** membuat Azure Redis Cache.

## EXAMPLES

### Contoh 1: Membuat Cache Redis
```powershell
New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "North Central US"
```

```output
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

Perintah ini membuat Redis Cache.

### Contoh 2: Membuat Cache Redis SKU Standar
```powershell
New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "North Central US" -Size 250MB -Sku "Standard" -RedisConfiguration @{"maxmemory-policy" = "allkeys-random"}
```

```output
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

Cmdlet ini membuat cache menggunakan Azure Cache for Redis.

### Contoh 3: Membuat Singgahan Zona Redundan

```powershell
New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "Central US" -Size P1 -Sku "Premium" -Zone @("1","2")
```

```output
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

Perintah ini membuat instans Azure cache for Redis di zona mutliple.

### Contoh 4: Membuat Virtual Network mengaktifkan Cache

Persyaratan untuk membuat Virtual Network mengaktifkan cache.
1. Buat jaringan virtual dalam grup sumber daya yang sama tempat Anda ingin membuat cache redis Anda. Anda dapat membuat jaringan virtual dari perintah [powershell New-AzVirtualNetwork](/powershell/module/az.network/new-azvirtualnetwork) .
1. Anda akan memerlukan SubnetID untuk cache berkemampuan VNET. Sintaks SubnetID diberikan di bawah ini.

Format SubnetID: /subscriptions/{subid}/resourceGroups/{resourceGroupName}/providers/Microsoft.ClassicNetwork/VirtualNetworks/{vnetName}/subnets/{subnetName}

```powershell
New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "Central US" -Size P1 -Sku "Premium" -SubnetId "/subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Network/virtualNetworks/MyNet/subnets/MySubnet"
```

```output
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

### Contoh 5: Mengonfigurasi persistensi data untuk Premium Azure Cache for Redis

Persistence menulis data Redis ke akun Microsoft Azure Storage yang Anda miliki dan kelola. Jadi sebelum mengonfigurasi persistensi data, Anda harus memiliki [akun penyimpanan](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-create?tabs=azure-powershell) dalam grup sumber daya yang sama. Pilih akun penyimpanan di wilayah dan langganan yang sama dengan cache, dan akun Microsoft Azure Storage Premium direkomendasikan karena penyimpanan premium memiliki throughput yang lebih tinggi.

Setelah membuat akun penyimpanan, dapatkan string koneksi akun penyimpanan menggunakan prosedur ini.

1. Jalankan perintah ini **Get-AzStorageAccountKey -ResourceGroupName $resourceGroupName -Name $storageAccountName** di powershell.
1. Dari output di atas, salin kunci apa pun.
1. Masukkan kunci akun penyimpanan dan nama akun penyimpanan dalam format di bawah ini untuk mendapatkan string koneksi akun penyimpanan Anda.

Format String Koneksi :- "DefaultEndpointsProtocol=https; AccountName={storageAccountName}; AccountKey={storageAccountKey}; EndpointSuffix=core.windows.net"</br>

Anda harus memiliki pengaturan konfigurasi Redis tertentu untuk mengaktifkan persistensi data.

Untuk mengaktifkan pencadangan RDB
-  rdb-backup-enabled (Set true atau false)
-  rdb-storage-connection-string (Berikan string koneksi dalam format di atas.)
-  rdb-backup-frequency (Atur interval cadangan dalam hitungan menit. Anda hanya dapat memilih dari - 15, 30, 60, 360, 720 dan 1440 menit.)



```powershell
New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "Central US" -Size P1 -Sku "Premium" -RedisConfiguration @{"rdb-backup-enabled" = "true"; "rdb-storage-connection-string" = "DefaultEndpointsProtocol=https;AccountName=mystorageaccount;AccountKey=pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=;EndpointSuffix=core.windows.net"; "rdb-backup-frequency" = "30"}
```

```output
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

### Contoh 6: Mengonfigurasi persistensi data untuk Premium Azure Cache for Redis - Pencadangan AOF diaktifkan

Untuk pencadangan AOF diaktifkan.
-  aof-backup-enabled (Set true atau false),
-  aof-storage-connection-string-0 (Berikan string koneksi dalam format di atas.)
-  aof-storage-connection-string-1 (Anda dapat mengonfigurasi akun penyimpanan lain secara opsional. Jika akun penyimpanan kedua dikonfigurasi, tulisan ke cache replika ditulis ke akun penyimpanan kedua ini.)

```powershell
New-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "Central US" -Size P1 -Sku "Premium" -RedisConfiguration @{"aof-backup-enabled" = "true"; "aof-storage-connection-string-0" = "DefaultEndpointsProtocol=https;AccountName=mystorageaccount;AccountKey=pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=;EndpointSuffix=core.windows.net"}
```

```output
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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Nilai default adalah $False (port non-SSL dinonaktifkan).

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

### -IdentityType
Menentukan jenis identitas yang digunakan untuk Azure Cache for Redis. Nilai yang valid: "SystemAssigned" atau "UserAssigned" atau "SystemAssignedUserAssigned" atau "None"

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

### -Lokasi
Menentukan lokasi untuk membuat Redis Cache.
Nilai yang valid adalah:
- US Tengah Utara
- US Tengah Selatan
- US Tengah
- Eropa Barat
- Eropa Utara
- US Barat
- AS Timur
- US Timur 2
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
Tentukan versi TLS yang diperlukan oleh klien untuk menyambungkan ke cache.

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

### -Name
Menentukan nama Redis Cache yang akan dibuat.

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
Tentukan pengaturan konfigurasi Redis.
Nilai yang dapat diterima untuk parameter ini adalah:
- rdb-backup-enabled.
Menentukan bahwa persistensi data Redis diaktifkan.
Premium tingkat saja.
- rdb-storage-connection-string.
Menentukan string koneksi ke akun Storage untuk persistensi data Redis.
Premium tingkat saja.
- frekuensi pencadangan rdb.
Menentukan frekuensi pencadangan untuk persistensi data Redis.
Premium tingkat saja.
- maxmemory-reserved.
Mengonfigurasi memori yang dicadangkan untuk proses non-cache.
Tingkat standar dan Premium.
- kebijakan maxmemory.
Mengonfigurasi kebijakan pengeluaran untuk cache.
Semua tingkat harga.
- notify-keyspace-events.
Mengonfigurasi pemberitahuan keyspace.
Tingkat standar dan premium.
- hash-max-ziplist-entries.
Mengonfigurasi pengoptimalan memori untuk jenis data agregat kecil.
Tingkat standar dan Premium.
- hash-max-ziplist-value.
Mengonfigurasi pengoptimalan memori untuk jenis data agregat kecil.
Tingkat standar dan Premium.
- set-max-intset-entries.
Mengonfigurasi pengoptimalan memori untuk jenis data agregat kecil.
Tingkat standar dan Premium.
- zset-max-ziplist-entries.
Mengonfigurasi pengoptimalan memori untuk jenis data agregat kecil.
Tingkat standar dan Premium.
- zset-max-ziplist-value.
Mengonfigurasi pengoptimalan memori untuk jenis data agregat kecil.
Tingkat standar dan Premium.
- Database.
Konfigurasikan jumlah database.
Properti ini hanya dapat dikonfigurasi pada pembuatan cache.
Tingkat standar dan Premium.
Untuk informasi selengkapnya, lihat Mengelola Azure Redis Cache dengan Azure PowerShellhttp://go.microsoft.com/fwlink/?LinkId=800051 (http://go.microsoft.com/fwlink/?LinkId=800051).

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
Versi Redis. Nilai yang valid: 4, 6

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
Menentukan nama grup sumber daya untuk membuat Redis Cache.

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

### -ShardCount
Menentukan jumlah pecahan yang akan dibuat pada cache kluster Premium.
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

### -Ukuran
Menentukan ukuran Redis Cache.
Nilai yang valid adalah:
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
- 53GB Nilai defaultnya adalah 1GB atau C1.

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
Menentukan SKU Redis Cache untuk dibuat.
Nilai yang valid adalah:
- Dasar
- Standard
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
Menentukan alamat IP unik di subnet untuk Redis Cache.
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
ID sumber daya lengkap subnet di jaringan virtual untuk menyebarkan Azure Cache for Redis.
Contoh format: /subscriptions/{subid}/resourceGroups/{resourceGroupName}/Microsoft. {Network| ClassicNetwork}/VirtualNetworks/{vnetName}/subnets/{subnetName}

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
Parameter ini tidak digunakan lagi.

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

### -UserAssignedIdentity
Menentukan satu atau beberapa identitas pengguna yang dipisahkan koma yang akan dikaitkan dengan Azure Cache for Redis. Referensi identitas pengguna akan menjadi id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

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

### -Zona
Daftar wilayah Azure dengan [Zona ketersediaan](https://docs.microsoft.com/en-us/azure/availability-zones/az-region#azure-services-supporting-availability-zones).

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### System.String

### System.Collections.Hashtable

### System.Nullable'1[[System.Boolean, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.String[]

## OUTPUTS

### Microsoft.Azure.Commands.RedisCache.Models.RedisCacheAttributesWithAccessKeys

## NOTES

## RELATED LINKS

[Get-AzRedisCache](./Get-AzRedisCache.md)

[Remove-AzRedisCache](./Remove-AzRedisCache.md)

[Set-AzRedisCache](./Set-AzRedisCache.md)


