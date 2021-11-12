---
external help file: Microsoft.Azure.Commands.RedisCache.dll-Help.xml
Module Name: AzureRM.RedisCache
ms.assetid: 81179AFE-6524-4F59-8BC2-3E152F51D1DD
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.rediscache/new-azurermrediscache
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RedisCache/Commands.RedisCache/help/New-AzureRmRedisCache.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RedisCache/Commands.RedisCache/help/New-AzureRmRedisCache.md
ms.openlocfilehash: bbba6372be7176b8ac1aec553a9abbbf83c7da31
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420770"
---
# New-AzureRmRedisCache

## SYNOPSIS
Membuat Cache Redis.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmRedisCache -ResourceGroupName <String> -Name <String> -Location <String> [-RedisVersion <String>]
 [-Size <String>] [-Sku <String>] [-MaxMemoryPolicy <String>] [-RedisConfiguration <Hashtable>]
 [-EnableNonSslPort <Boolean>] [-TenantSettings <Hashtable>] [-ShardCount <Int32>] [-VirtualNetwork <String>]
 [-Subnet <String>] [-SubnetId <String>] [-StaticIP <String>] [-Tag <Hashtable>] [-Zone <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmRedisCache** membuat Cache Azure Redis.

## EXAMPLES

### Contoh 1: Membuat Cache Redis
```
PS C:\>New-AzureRmRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "North Central US"

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
PS C:\>New-AzureRmRedisCache -ResourceGroupName "MyGroup" -Name "MyCache" -Location "North Central US" -Size 250MB -Sku "Standard" -RedisConfiguration @{"maxmemory-policy" = "allkeys-random"} -Force

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

Perintah ini akan membuat Cache Redis.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

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
Type: Boolean
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
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxCyPolicy
Parameter ini sudah tidak berlaku.
Gunakan parameter *RedisConfiguration* untuk mengatur maxrig-policy.
Misalnya: 

`-RedisConfiguration @{"maxmemory-policy" = "allkeys-lru"}`

```yaml
Type: String
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
Type: String
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

Untuk informasi selengkapnya, lihat Mengelola Cache Azure Redis dengan Azure PowerShell https://go.microsoft.com/fwlink/?LinkId=800051 ( https://go.microsoft.com/fwlink/?LinkId=800051) .

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RedisVersion
Parameter ini sudah tidak berlaku dan akan dihapus dari rilis mendatang.

```yaml
Type: String
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
Type: String
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
Type: Int32
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

Nilai default adalah 1GB atau C1.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: P1, P2, P3, P4, C0, C1, C2, C3, C4, C5, C6, 250MB, 1GB, 2.5GB, 6GB, 13GB, 26GB, 53GB

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
- Premium

Nilai defaultnya adalah Standar.

```yaml
Type: String
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
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subnet
Menentukan nama subnet untuk menyebarkan Cache Redis.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubnetId
```yaml
Type: String
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
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TenantSettings
Parameter ini sudah tidak berlaku.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetwork
Menentukan ID sumber daya jaringan virtual untuk menyebarkan Cache Redis.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
Daftar zona.

```yaml
Type: String[]
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
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Anda dapat pipa input ke cmdlet ini menurut nama, tetapi tidak menurut nilai.

## OUTPUTS

### Microsoft.Azure.Commands.RedisCache.Models.RedisCacheAttributesWithAccessKeys
Cmdlet ini mengembalikan semua atribut Cache Redis, termasuk tombol akses primer dan sekunder.

## CATATAN

## RELATED LINKS

[Get-AzureRmRedisCache](./Get-AzureRmRedisCache.md)

[Remove-AzureRmRedisCache](./Remove-AzureRmRedisCache.md)

[Set-AzureRmRedisCache](./Set-AzureRmRedisCache.md)


