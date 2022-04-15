---
external help file: ''
Module Name: Az.RedisEnterpriseCache
online version: https://docs.microsoft.com/powershell/module/az.redisenterprisecache/new-azredisenterprisecache
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisEnterpriseCache/help/New-AzRedisEnterpriseCache.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisEnterpriseCache/help/New-AzRedisEnterpriseCache.md
ms.openlocfilehash: 5295104fd69ce536d8dac283f680d788dd85063e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142464767"
---
# New-AzRedisEnterpriseCache

## SYNOPSIS
Membuat singgahan Redis Enterprise.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.redisenterprisecache/new-azredisenterprisecache) untuk informasi terbaru.

## SYNTAX

### CreateClusterWithDatabase (Default)
```
New-AzRedisEnterpriseCache -ClusterName <String> -ResourceGroupName <String> -Location <String> -Sku <SkuName>
 [-SubscriptionId <String>] [-AofPersistenceEnabled] [-AofPersistenceFrequency <AofFrequency>]
 [-Capacity <Int32>] [-ClientProtocol <Protocol>] [-ClusteringPolicy <ClusteringPolicy>]
 [-EvictionPolicy <EvictionPolicy>] [-MinimumTlsVersion <TlsVersion>] [-Module <IModule[]>] [-Port <Int32>]
 [-RdbPersistenceEnabled] [-RdbPersistenceFrequency <RdbFrequency>] [-Tag <Hashtable>] [-Zone <String[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### CreateClusterOnly
```
New-AzRedisEnterpriseCache -ClusterName <String> -ResourceGroupName <String> -Location <String> -Sku <SkuName>
 -NoDatabase [-SubscriptionId <String>] [-Capacity <Int32>] [-MinimumTlsVersion <TlsVersion>]
 [-Tag <Hashtable>] [-Zone <String[]>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui kluster singgahan yang sudah ada (timpa/buat ulang, dengan potensi waktu henti) dengan database terkait.

## EXAMPLES

### Contoh 1: Membuat cache Redis Enterprise
```powershell
PS C:\> New-AzRedisEnterpriseCache -Name "MyCache" -ResourceGroupName "MyGroup" -Location "West US" -Sku "Enterprise_E10"

Location Name    Type                            Zone Database
-------- ----    ----                            ---- --------
West US  MyCache Microsoft.Cache/redisEnterprise      {default}

```

Perintah ini membuat singgahan Redis Enterprise bernama MyCache dengan database terkait bernama default.

### Contoh 2: Membuat cache Redis Enterprise menggunakan beberapa parameter opsional
```powershell
PS C:\> New-AzRedisEnterpriseCache -Name "MyCache" -ResourceGroupName "MyGroup" -Location "East US" -Sku "Enterprise_E20" -Capacity 4 -MinimumTlsVersion "1.2" -Zone "1","2","3" -Tag @{"tag1" = "value1"} -Module "{name:RedisBloom, args:`"ERROR_RATE 0.00 INITIAL_SIZE 400`"}","{name:RedisTimeSeries, args:`"RETENTION_POLICY 20`"}","{name:RediSearch}" -ClientProtocol "Plaintext" -EvictionPolicy "NoEviction" -ClusteringPolicy "EnterpriseCluster" -AofPersistenceEnabled -AofPersistenceFrequency "1s"

Location Name    Type                            Zone      Database
-------- ----    ----                            ----      --------
East US  MyCache Microsoft.Cache/redisEnterprise {1, 2, 3} {default}

```

Perintah ini membuat singgahan Redis Enterprise bernama MyCache dengan database terkait bernama default, menggunakan beberapa parameter opsional.

### Contoh 3: Advanced - Create a Redis Enterprise cache cluster without an associated database
```powershell
PS C:\> New-AzRedisEnterpriseCache -Name "MyCache" -ResourceGroupName "MyGroup" -Location "East US" -Sku "EnterpriseFlash_F300" -NoDatabase

Location Name    Type                            Zone Database
-------- ----    ----                            ---- --------
East US  MyCache Microsoft.Cache/redisEnterprise      {}

```

Peringatan: Perintah ini membuat kluster cache Redis Enterprise bernama MyCache tanpa database terkait untuk menyimpan data.

## PARAMETERS

### -AofPersistenceEnabled
[Pratinjau] Mengatur apakah persistensi AOF diaktifkan.
Setelah mengaktifkan persistensi AOF, Anda tidak akan dapat menonaktifkannya.
Dukungan untuk menonaktifkan persistensi AOF setelah mengaktifkan akan ditambahkan di kemudian hari.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CreateClusterWithDatabase
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AofPersistenceFrequency
[Pratinjau] Mengatur frekuensi saat data ditulis ke disk jika persistensi AOF diaktifkan.
Nilai yang diperbolehkan: 1s, selalu

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Support.AofFrequency
Parameter Sets: CreateClusterWithDatabase
Aliases:

Required: False
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

### -Kapasitas
Ukuran klaster Redis Enterprise - default ke 2 atau 3 tergantung pada SKU.
Nilai yang diperbolehkan adalah (2, 4, 6, ...) untuk SKU Perusahaan dan (3, 9, 15, ...) untuk SKU Flash.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: SkuCapacity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientProtocol
Menentukan apakah klien redis dapat tersambung menggunakan protokol redis terenkripsi TLS atau plaintext - defaultnya adalah nilai Terenkripsi Yang Diperbolehkan: Terenkripsi, Plaintext

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Support.Protocol
Parameter Sets: CreateClusterWithDatabase
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusteringPolicy
Kebijakan kluster - defaultnya adalah OSSCluster Yang Ditentukan saat membuat waktu.
Nilai yang diperbolehkan: EnterpriseCluster, OSSCluster

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Support.ClusteringPolicy
Parameter Sets: CreateClusterWithDatabase
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName
Nama kluster Redis Enterprise.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

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

### -EvictionPolicy
Kebijakan penggusuran Redis - default adalah nilai yang diizinkan VolatileLRU: AllKeysLFU, AllKeysLRU, AllKeysRandom, VolatileLRU, VolatileLFU, VolatileTTL, VolatileRandom, NoEviction

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Support.EvictionPolicy
Parameter Sets: CreateClusterWithDatabase
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi geografis tempat sumber daya berada.

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

### -MinimumTlsVersion
Versi TLS minimum untuk didukung kluster - defaultnya adalah 1,2 Nilai yang diperbolehkan: 1.0, 1.1, 1.2

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Support.TlsVersion
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Module
Rangkaian modul redis opsional untuk diaktifkan dalam database ini - modul hanya dapat ditambahkan pada waktu pembuatan.
Untuk membangun, lihat bagian CATATAN untuk properti MODULE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Models.Api20210301.IModule[]
Parameter Sets: CreateClusterWithDatabase
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoDatabase
Tingkat Lanjut - Jangan membuat database default secara otomatis.
Peringatan: Cache tidak akan dapat digunakan hingga Anda membuat database.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CreateClusterOnly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -Port
Port TCP dari titik akhir database - default ke port yang tersedia Ditentukan saat membuat waktu.

```yaml
Type: System.Int32
Parameter Sets: CreateClusterWithDatabase
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RdbPersistenceEnabled
[Pratinjau] Mengatur apakah persistensi RDB diaktifkan.
Setelah mengaktifkan persistensi RDB, Anda tidak akan dapat menonaktifkannya.
Dukungan untuk menonaktifkan kegigihan RDB setelah mengaktifkan akan ditambahkan di kemudian hari.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CreateClusterWithDatabase
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RdbPersistenceFrequency
[Pratinjau] Mengatur frekuensi pembuatan snapshot database jika persistensi RDB diaktifkan.
Nilai yang diperbolehkan: 1h, 6h, 12h

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Support.RdbFrequency
Parameter Sets: CreateClusterWithDatabase
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

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

### -Sku
Tipe klaster Redis Enterprise untuk disebarkan.
Nilai yang diperbolehkan: Enterprise_E10, Enterprise_E20, Enterprise_E50, Enterprise_E100, EnterpriseFlash_F300, EnterpriseFlash_F700, EnterpriseFlash_F1500

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Support.SkuName
Parameter Sets: (All)
Aliases: SkuName

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

### -Tag
Tag sumber daya kluster.

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

### -Zona
Availability Zones tempat kluster ini akan disebarkan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Models.Api20210301.ICluster

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


MODULE <IModule[]>: Rangkaian modul redis opsional untuk diaktifkan dalam database ini - modul hanya dapat ditambahkan pada waktu pembuatan.
  - `Name <String>`: Nama modul, misalnya 'RedisBloom', 'RediSearch', 'RedisTimeSeries'
  - `[Arg <String>]`: Opsi konfigurasi untuk modul, misalnya 'ERROR_RATE 0.00 INITIAL_SIZE 400'.

## RELATED LINKS

