---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RedisCache.dll-Help.xml
Module Name: Az.RedisCache
ms.assetid: 6234F211-6ED4-443F-9B83-DEB9AC51B763
online version: https://docs.microsoft.com/powershell/module/az.rediscache/set-azrediscache
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/Set-AzRedisCache.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/Set-AzRedisCache.md
ms.openlocfilehash: 62b6e3f1f3f6bdb3ac54451ca5e6e1501e710378
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139969755"
---
# Set-AzRedisCache

## SYNOPSIS
Mengubah Cache Azure untuk Redis.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.rediscache/set-azrediscache) untuk informasi terkini.

## SYNTAX

```
Set-AzRedisCache [-ResourceGroupName <String>] -Name <String> [-Size <String>] [-Sku <String>]
 [-RedisConfiguration <Hashtable>] [-EnableNonSslPort <Boolean>] [-TenantSettings <Hashtable>]
 [-ShardCount <Int32>] [-MinimumTlsVersion <String>] [-RedisVersion <String>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzRedisCache** mengubah Cache Azure untuk Redis.

## EXAMPLES

### Contoh 1: Modifikasi Cache Azure untuk Redis
```
PS C:\>Set-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -RedisConfiguration @{"maxmemory-policy" = "allkeys-random"}

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : mygroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/myCache
          Location           : North Central US
          Name               : MyCache
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

Perintah ini memperbarui kebijakan max azure untuk Cache Azure fo Redis bernama *MyCache*.

### Contoh 2: Modifikasi Cache Azure untuk Redis - Jika Anda ingin Menonaktifkan RDB atau Ke persistensi Data AOF.
```
PS C:\>Set-AzRedisCache -Name "MyCache"  -RedisConfiguration @{"rdb-backup-enabled" = "false"}

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : Succeeded
          SslPort            : 6380
          RedisConfiguration : {[maxmemory-policy, allkeys-random], [maxclients, 7500], [maxmemory-reserved, 200],
                                [maxfragmentationmemory-reserved, 300], [rdb-backup-enabled, false]...} 
          EnableNonSslPort   : False
          RedisVersion       : 4.0.14
          Size               : 6GB
          Sku                : Premium
          Tag                : {}
          Zone               : []
```    

Cmdlet ini menonaktifkan persistensi data cadangan RDB untuk Cache Azure untuk Redis. Anda juga bisa menonaktifkan singgahan persisten cadangan AOF.

### Contoh 3: Modifikasi Cache Azure untuk Redis - Jika Anda ingin menambahkan persistensi data setelah cache Azure Redis dibuat.
```
PS C:\>Set-AzRedisCache -Name "MyCache" -RedisConfiguration @{"rdb-backup-enabled" = "true"; "rdb-storage-connection-string" = "DefaultEndpointsProtocol=https;AccountName=mystorageaccount;AccountKey=pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=;EndpointSuffix=core.windows.net"; "rdb-backup-frequency" = "30"}

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : Succeeded
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
Cmdlet ini mengaktifkan persistensi rdb-backup pada cache yang sudah ada. Anda juga bisa mengaktifkan persistensi aof-cadangan.

### Contoh 4: Modifikasi Cache Azure untuk Redis - Jika Anda ingin mengubah frekuensi cadangan rdb.

Misalnya - Saat ini Anda mengambil snapshot RDB setiap 30 menit, tapi Anda ingin mengubah untuk mengambil snapshot 15 menit.

```
PS C:\>Set-AzRedisCache -Name "MyCache" -RedisConfiguration @{"rdb-backup-frequency" = "15"}

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : Succeeded
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

### Contoh 5: Modifikasi Cache Azure untuk Redis - Jika Anda ingin mengubah AOF mencadangkan persistensi data ke cadangan RDB.

```
PS C:\>Set-AzRedisCache -Name "MyCache"  -RedisConfiguration @{"aof-backup-enabled"= "false"; "rdb-backup-enabled" = "true"; "rdb-storage-connection-string" = "DefaultEndpointsProtocol=https;AccountName=mystorageaccount;AccountKey=pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=;EndpointSuffix=core.windows.net"; "rdb-backup-frequency" = "30"}

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : Succeeded
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
Cmdlet ini membantu dalam mengubah metode persistensi.


### Contoh 6: Menskalakan Cache Azure untuk Instans Redis - Pembaruan ke ukuran berbeda.

```
PS C:\>Set-AzRedisCache -Name "MyCache" -Size "P2" -Sku "Premium"

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : Scaling
          SslPort            : 6380
          RedisConfiguration : {[maxmemory-policy, allkeys-random], [maxclients, 7500], [maxmemory-reserved, 200],
                                [maxfragmentationmemory-reserved, 300]....} 
          EnableNonSslPort   : False
          RedisVersion       : 4.0.14
          Size               : 6GB
          Sku                : Premium
          Tag                : {}
          Zone               : []
```
Perintah ini akan menambah atau mengurangi ukuran memori instans Anda.


### Contoh 7: Menskalakan Cache Azure untuk Instans Redis - Pembaruan ke tingkatan berbeda.

```
PS C:\>Set-AzRedisCache -Name "MyCache" -Size "P1" -Sku "Premium" 

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : Scaling
          SslPort            : 6380
          RedisConfiguration : {[maxmemory-policy, allkeys-random], [maxclients, 7500], [maxmemory-reserved, 200],
                                [maxfragmentationmemory-reserved, 300]....} 
          EnableNonSslPort   : False
          RedisVersion       : 4.0.14
          Size               : 1GB
          Sku                : Standard
          Tag                : {}
          Zone               : []
```
Perintah ini membantu Anda mengubah tingkatan cache. Anda bisa mengubah dari Dasar ke Standar, atau Standar Premium.

### Contoh 8: Menskalakan Cache Azure untuk Instans Redis - Mengaktifkan Kluster Redis.

```
PS C:\>Set-AzRedisCache -Name "MyCache" -ShardCount 1

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : Scaling
          SslPort            : 6380
          RedisConfiguration : {[maxmemory-policy, allkeys-random], [maxclients, 7500], [maxmemory-reserved, 200],
                                [maxfragmentationmemory-reserved, 300]....} 
          EnableNonSslPort   : False
          RedisVersion       : 4.0.14
          Size               : 6GB
          Sku                : Premium
          ShardCount         :
          Tag                : {}
          Zone               : []
```
Cmdlet ini membantu Anda dalam mengaktifkan kluster untuk instans Azure Cache untuk Merah. Untuk menambah jumlah lokasi, harus mengaktifkan kluster terlebih dahulu.


### Contoh 9: Menskalakan Cache Azure untuk Instans Redis - Gunakan Kluster Redis untuk menyesuaikan/mengeluarkan skala.

```
PS C:\>Set-AzRedisCache -Name "MyCache" -ShardCount 2

          PrimaryKey         : pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          SecondaryKey       : sJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=
          ResourceGroupName  : MyGroup
          Id                 : /subscriptions/a559b6fd-3a84-40bb-a450-b0db5ed37dfe/resourceGroups/mygroup/providers/Microsoft.Cache/Redis/MyCache
          Location           : Central US
          Name               : mycache
          Type               : Microsoft.Cache/Redis
          HostName           : mycache.redis.cache.windows.net
          Port               : 6379
          ProvisioningState  : Scaling
          SslPort            : 6380
          RedisConfiguration : {[maxmemory-policy, allkeys-random], [maxclients, 7500], [maxmemory-reserved, 200],
                                [maxfragmentationmemory-reserved, 300]....} 
          EnableNonSslPort   : False
          RedisVersion       : 4.0.14
          Size               : 6GB
          Sku                : Premium
          ShardCount         : 1
          Tag                : {}
          Zone               : []
```
Perintah ini akan menambah atau mengurangi ukuran kluster.


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
Menentukan nama Singgahan Azure untuk Redis untuk diperbarui.

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
Menentukan string koneksi ke akun Storage untuk Redis persistensi data.
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
Untuk informasi selengkapnya, lihat Mengelola Cache Azure Redis dengan Azure PowerShellhttp://go.microsoft.com/fwlink/?LinkId=800051 (http://go.microsoft.com/fwlink/?LinkId=800051).

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
Menentukan nama grup sumber daya yang berisi Cache Redis.

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

### -ScountCount
Menentukan jumlah s node untuk dibuat pada cache kluster Premium baru.

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
- 53GB
- 120GB Nilai default adalah 1GB atau C1.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Hashtable

### System.Nullable'1[[System.Boolean, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.RedisCache.Models.RedisCacheAttributesWithAccessKeys

## CATATAN

## RELATED LINKS

[Get-AzRedisCache](./Get-AzRedisCache.md)

[New-AzRedisCache](./New-AzRedisCache.md)

[Remove-AzRedisCache](./Remove-AzRedisCache.md)


