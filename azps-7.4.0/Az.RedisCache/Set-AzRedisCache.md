---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RedisCache.dll-Help.xml
Module Name: Az.RedisCache
ms.assetid: 6234F211-6ED4-443F-9B83-DEB9AC51B763
online version: https://docs.microsoft.com/powershell/module/az.rediscache/set-azrediscache
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/Set-AzRedisCache.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisCache/RedisCache/help/Set-AzRedisCache.md
ms.openlocfilehash: 2fd8177518d2d8f7d63d0048319d3970f5950c01
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144676960"
---
# Set-AzRedisCache

## SYNOPSIS
Memodifikasi Azure Cache for Redis.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.rediscache/set-azrediscache) untuk informasi terbaru.

## SYNTAX

```
Set-AzRedisCache [-ResourceGroupName <String>] -Name <String> [-Size <String>] [-Sku <String>]
 [-RedisConfiguration <Hashtable>] [-EnableNonSslPort <Boolean>] [-TenantSettings <Hashtable>]
 [-ShardCount <Int32>] [-MinimumTlsVersion <String>] [-RedisVersion <String>] [-Tag <Hashtable>]
 [-IdentityType <String>] [-UserAssignedIdentity <String[]>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzRedisCache** memodifikasi Azure Cache for Redis.

## EXAMPLES

### Contoh 1: Mengubah Azure Cache for Redis
```powershell
Set-AzRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -RedisConfiguration @{"maxmemory-policy" = "allkeys-random"}
```

```output
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

Perintah ini memperbarui kebijakan maxmemory untuk Azure Cache fo Redis Bernama *MyCache*.

### Contoh 2: Ubah Azure Cache for Redis - Jika Anda ingin Menonaktifkan Persistensi Data RDB atau AOF.
```powershell
Set-AzRedisCache -Name "MyCache"  -RedisConfiguration @{"rdb-backup-enabled" = "false"}
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

    

Cmdlet ini menonaktifkan persistensi data cadangan RDB untuk Azure Cache for Redis. Anda juga dapat menonaktifkan cache persisten cadangan AOF.

### Contoh 3: Ubah Azure Cache for Redis - Jika Anda ingin menambahkan persistensi data setelah cache azure redis dibuat.
```powershell
Set-AzRedisCache -Name "MyCache" -RedisConfiguration @{"rdb-backup-enabled" = "true"; "rdb-storage-connection-string" = "DefaultEndpointsProtocol=https;AccountName=mystorageaccount;AccountKey=pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=;EndpointSuffix=core.windows.net"; "rdb-backup-frequency" = "30"}
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

Cmdlet ini memungkinkan persistensi cadangan rdb pada cache yang sudah ada. Anda juga dapat mengaktifkan persistensi cadangan aof.

### Contoh 4: Ubah Azure Cache for Redis - Jika Anda ingin mengubah frekuensi pencadangan rdb.

Misalnya - Saat ini Anda mengambil rekam jepret RDB dalam setiap 30 menit, tetapi Anda ingin mengubah untuk mengambil rekam jepret 15 menit.

```powershell
Set-AzRedisCache -Name "MyCache" -RedisConfiguration @{"rdb-backup-frequency" = "15"}
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

### Contoh 5: Ubah Azure Cache for Redis - Jika Anda ingin mengubah persistensi data cadangan AOF menjadi cadangan RDB.

```powershell
Set-AzRedisCache -Name "MyCache"  -RedisConfiguration @{"aof-backup-enabled"= "false"; "rdb-backup-enabled" = "true"; "rdb-storage-connection-string" = "DefaultEndpointsProtocol=https;AccountName=mystorageaccount;AccountKey=pJ+jruGKPHDKsEC8kmoybobH3TZx2njBR3ipEsquZFo=;EndpointSuffix=core.windows.net"; "rdb-backup-frequency" = "30"}
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

### Contoh 6: Skalakan Instans Azure Cache for Redis - Perbarui ke ukuran yang berbeda.

```powershell
Set-AzRedisCache -Name "MyCache" -Size "P2" -Sku "Premium"
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

Perintah ini meningkatkan atau mengurangi ukuran memori instans Anda.

### Contoh 7: Menskalakan Instans Azure Cache for Redis - Perbarui ke tingkat yang berbeda.

```powershell
Set-AzRedisCache -Name "MyCache" -Size "P1" -Sku "Premium" 
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

Perintah ini membantu Anda mengubah tingkat cache Anda. Anda dapat mengubah dari Dasar ke Standar, atau Standar ke Premium.

### Contoh 8: Menskalakan Instans Azure Cache for Redis - Aktifkan Pengklusteran Redis.

```powershell
Set-AzRedisCache -Name "MyCache" -ShardCount 1
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

Cmdlet ini membantu Anda mengaktifkan pengklusteran untuk instans Azure Cache for Redis Anda. Untuk meningkatkan jumlah shard, harus mengaktifkan pengklusteran terlebih dahulu.

### Contoh 9: Menskalakan Instans Azure Cache for Redis - Gunakan Kluster Redis untuk menskalakan masuk/keluar.

```powershell
Set-AzRedisCache -Name "MyCache" -ShardCount 2
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

Perintah ini menambah atau mengurangi ukuran kluster.

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
Menentukan nama Azure Cache for Redis yang akan diperbarui.

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
Menentukan nama grup sumber daya yang berisi Redis Cache.

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

### -ShardCount
Menentukan jumlah pecahan yang akan dibuat pada cache kluster Premium.

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
- 53GB
- 120GB Nilai defaultnya adalah 1GB atau C1.

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

## OUTPUTS

### Microsoft.Azure.Commands.RedisCache.Models.RedisCacheAttributesWithAccessKeys

## NOTES

## RELATED LINKS

[Get-AzRedisCache](./Get-AzRedisCache.md)

[New-AzRedisCache](./New-AzRedisCache.md)

[Remove-AzRedisCache](./Remove-AzRedisCache.md)


