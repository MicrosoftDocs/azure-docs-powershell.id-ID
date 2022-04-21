---
external help file: Microsoft.Azure.Commands.RedisCache.dll-Help.xml
Module Name: AzureRM.RedisCache
ms.assetid: 81179AFE-6524-4F59-8BC2-3E152F51D1DD
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.rediscache/new-azurermrediscache
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RedisCache/Commands.RedisCache/help/New-AzureRmRedisCache.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RedisCache/Commands.RedisCache/help/New-AzureRmRedisCache.md
ms.openlocfilehash: 6b2239e09a35ada6b756e58cf2c3a09ed891e730
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142725220"
---
# New-AzureRmRedisCache

## SYNOPSIS
Membuat Singgahan Redis.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmRedisCache -ResourceGroupName <String> -Name <String> -Location <String> [-Size <String>]
 [-Sku <String>] [-RedisConfiguration <Hashtable>] [-EnableNonSslPort <Boolean>] [-TenantSettings <Hashtable>]
 [-ShardCount <Int32>] [-SubnetId <String>] [-StaticIP <String>] [-Tag <Hashtable>] [-Zone <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmRedisCache** membuat Cache Azure Redis.

## EXAMPLES

### Contoh 1: Membuat Singgahan Redis
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

Perintah ini membuat Singgahan Redis.

### Contoh 2: Create a Standard SKU Redis Cache
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

Perintah ini membuat Singgahan Redis.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
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

### -Lokasi
Menentukan lokasi untuk membuat Singgahan Redis.
Nilai yang valid adalah: 
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

### -Nama
Menentukan nama Singgahan Redis untuk dibuat.

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
Menentukan pengaturan konfigurasi Redis.
Nilai yang dapat diterima untuk parameter ini adalah:
- rdb-backup-enabled.
Menentukan bahwa Redis persistensi data diaktifkan.
Premium tingkat saja.
- rdb-storage-connection-string.
Menentukan string koneksi ke akun Storage untuk persistensi data Redis.
Premium tingkat saja.
- rdb-backup-frequency.
Menentukan frekuensi cadangan untuk persistensi data Redis.
Premium tingkat saja. 
- maxmemory-reserved.
Mengonfigurasi memori yang dipesan untuk proses non-cache.
Tingkat standar dan Premium. 
- maxmemory-policy.
Mengonfigurasi kebijakan penggalian untuk singgahan.
Semua tingkat harga. 
- notify-keyspace-events.
Mengonfigurasi pemberitahuan keyspace.
Tingkat standar dan premium. 
- hash-max-ziplist-entries.
Mengonfigurasi optimisasi memori untuk tipe data agregat kecil.
Tingkat standar dan Premium. 
- hash-max-ziplist-value.
Mengonfigurasi optimisasi memori untuk tipe data agregat kecil.
Tingkat standar dan Premium. 
- set-max-intset-entries.
Mengonfigurasi optimisasi memori untuk tipe data agregat kecil.
Tingkat standar dan Premium. 
- zset-max-ziplist-entries.
Mengonfigurasi optimisasi memori untuk tipe data agregat kecil.
Tingkat standar dan Premium. 
- zset-max-ziplist-value.
Mengonfigurasi optimisasi memori untuk tipe data agregat kecil.
Tingkat standar dan Premium. 
- Database.
Mengonfigurasi jumlah database.
Properti ini hanya dapat dikonfigurasi pada pembuatan cache.
Tingkat standar dan Premium.
Untuk informasi selengkapnya, lihat Mengelola Singgahan Azure Redis dengan Azure PowerShellhttps://go.microsoft.com/fwlink/?LinkId=800051 (https://go.microsoft.com/fwlink/?LinkId=800051).

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

### -ResourceGroupName
Menentukan nama grup sumber daya untuk membuat Singgahan Redis.

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
Menentukan jumlah shard yang akan dibuat pada singgahan klaster Premium.
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
Menentukan ukuran Singgahan Redis.
Nilai yang valid adalah: 
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
- 2,5 GB
- 6GB
- 13GB
- 26GB
- 53GB Nilai defaultnya adalah 1GB atau C1.

```yaml
Type: System.String
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
Menentukan SKU Singgahan Redis untuk dibuat.
Nilai yang valid adalah: 
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
Menentukan alamat IP unik dalam subnet untuk Singgahan Redis.
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
Parameter ini telah ditolak.

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

### -Zona
Daftar zona.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Hashtable

### System.Nullable'1[[System.Boolean, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

### System.Nullable'1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

### System.String[]

## OUTPUTS

### Microsoft.Azure.Commands.RedisCache.Models.RedisCacheAttributesWithAccessKeys

## NOTES

## RELATED LINKS

[Get-AzureRmRedisCache](./Get-AzureRmRedisCache.md)

[Hapus-AzureRmRedisCache](./Remove-AzureRmRedisCache.md)

[Set-AzureRmRedisCache](./Set-AzureRmRedisCache.md)


