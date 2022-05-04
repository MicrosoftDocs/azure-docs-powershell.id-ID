---
external help file: ''
Module Name: Az.PostgreSql
online version: https://docs.microsoft.com/powershell/module/az.postgresql/get-azpostgresqlconnectionstring
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PostgreSql/help/Get-AzPostgreSqlConnectionString.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PostgreSql/help/Get-AzPostgreSqlConnectionString.md
ms.openlocfilehash: 3a080db919801a7c7a034c121b21ffb2a0665401
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144731786"
---
# Get-AzPostgreSqlConnectionString

## SYNOPSIS
Dapatkan string koneksi sesuai dengan penyedia koneksi klien.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.postgresql/get-azpostgresqlconnectionstring) untuk informasi terbaru.

## SYNTAX

### Dapatkan (Default)
```
Get-AzPostgreSqlConnectionString -Client <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzPostgreSqlConnectionString -Client <String> -InputObject <IServer> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan string koneksi sesuai dengan penyedia koneksi klien.

## EXAMPLES

### Contoh 1: Mendapatkan string koneksi server PostgreSql menurut grup sumber daya dan nama server
```powershell
Get-AzPostgreSqlConnectionString -Client ADO.NET -Name PostgreSqlTestServer -ResourceGroupName PostgreSqlTestRG
```

```output
Server=postgresqltestserver.postgres.database.azure.com;Database={your_database};Port=5432;User Id=pwsh@postgresqltestserver;Password={your_password};Ssl Mode=Require;
```

Cmdlet ini mendapatkan string koneksi server PostgreSql menurut grup sumber daya dan nama server.

### Contoh 2: Mendapatkan string koneksi server PostgreSql berdasarkan identitas
```powershell
Get-AzPostgreSqlServer -ResourceGroupName PostgreSqlTestRG -ServerName PostgreSqlTestServer | Get-AzPostgreSqlConnectionString -Client PHP
```

```output
host=postgresqltestserver.postgres.database.azure.com port=5432 dbname={your_database} user=pwsh@postgresqltestserver password={your_password} sslmode=require
```

Cmdlet ini mendapatkan string koneksi server PostgreSql berdasarkan identitas.

## PARAMETERS

### -Klien
Penyedia koneksi klien.

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

### -InputObject
Server untuk string koneksi Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.PostgreSql.Models.Api20171201.IServer
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama server.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: ServerName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya, Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan yang mengidentifikasi langganan Azure.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.PostgreSql.Models.Api20171201.IServer

## OUTPUTS

### System.String

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IServer>: Server untuk string koneksi
  - `Location <String>`: Lokasi geografis tempat sumber daya berada
  - `[Tag <ITrackedResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AdministratorLogin <String>]`: Nama masuk administrator server. Hanya dapat ditentukan ketika server sedang dibuat (dan diperlukan untuk pembuatan).
  - `[EarliestRestoreDate <DateTime?>]`: Waktu pembuatan titik pemulihan paling awal (format ISO8601)
  - `[FullyQualifiedDomainName <String>]`: Nama domain server yang sepenuhnya memenuhi syarat.
  - `[IdentityType <IdentityType?>]`: Jenis identitas. Atur ini ke 'SystemAssigned' untuk membuat dan menetapkan prinsipal Azure Active Directory secara otomatis untuk sumber daya.
  - `[InfrastructureEncryption <InfrastructureEncryption?>]`: Status memperlihatkan apakah enkripsi infrastruktur yang diaktifkan server.
  - `[MasterServerId <String>]`: Id server master dari server replika.
  - `[MinimalTlsVersion <MinimalTlsVersionEnum?>]`: Terapkan versi Tls minimal untuk server.
  - `[PublicNetworkAccess <PublicNetworkAccessEnum?>]`: Apakah akses jaringan publik diizinkan atau tidak untuk server ini. Nilai bersifat opsional tetapi jika diteruskan, harus 'Diaktifkan' atau 'Dinonaktifkan'
  - `[ReplicaCapacity <Int32?>]`: Jumlah maksimum replika yang dapat dimiliki server master.
  - `[ReplicationRole <String>]`: Peran replikasi server.
  - `[SkuCapacity <Int32?>]`: Kapasitas peningkatan/peluasan skala, mewakili unit komputasi server.
  - `[SkuFamily <String>]`: Keluarga perangkat keras.
  - `[SkuName <String>]`: Nama sku, biasanya, tingkat + keluarga + inti, misalnya B_Gen4_1, GP_Gen5_8.
  - `[SkuSize <String>]`: Kode ukuran, yang akan ditafsirkan oleh sumber daya sebagaimana mewajibkan.
  - `[SkuTier <SkuTier?>]`: Tingkat SKU tertentu, misalnya Dasar.
  - `[SslEnforcement <SslEnforcementEnum?>]`: Aktifkan penegakan ssl atau tidak saat tersambung ke server.
  - `[StorageProfileBackupRetentionDay <Int32?>]`: Hari retensi cadangan untuk server.
  - `[StorageProfileGeoRedundantBackup <GeoRedundantBackup?>]`: Aktifkan Geo-redundan atau tidak untuk pencadangan server.
  - `[StorageProfileStorageAutogrow <StorageAutogrow?>]`: Aktifkan Storage Auto Grow.
  - `[StorageProfileStorageMb <Int32?>]`: Penyimpanan maks yang diizinkan untuk server.
  - `[UserVisibleState <ServerState?>]`: Status server yang terlihat oleh pengguna.
  - `[Version <ServerVersion?>]`: Versi server.

## RELATED LINKS

