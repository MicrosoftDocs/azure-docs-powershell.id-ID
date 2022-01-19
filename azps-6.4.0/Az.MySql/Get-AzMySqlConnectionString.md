---
external help file: ''
Module Name: Az.MySql
online version: https://docs.microsoft.com/powershell/module/az.mysql/get-azmysqlconnectionstring
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Get-AzMySqlConnectionString.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Get-AzMySqlConnectionString.md
ms.openlocfilehash: e31f1fdfc8fdddfa71ccc5877e9f21b0ee346ce4
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136170162"
---
# Get-AzMySqlConnectionString

## SYNOPSIS
Dapatkan string koneksi menurut penyedia koneksi klien.

## SYNTAX

### Dapatkan (Default)
```
Get-AzMySqlConnectionString -Client <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzMySqlConnectionString -Client <String> -InputObject <IServer> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan string koneksi menurut penyedia koneksi klien.

## EXAMPLES

### Contoh 1: Dapatkan string koneksi server MySql menurut grup sumber daya dan nama server
```powershell
PS C:\> Get-AzMySqlConnectionString -Client ADO.NET -Name mysql-test -ResourceGroupName PowershellMySqlTest

Server=mysql-test.mysql.database.azure.com; Port=3306; Database={your_database}; Uid=mysql_test@mysql-test; Pwd={your_password};
```

Cmdlet ini mendapatkan string koneksi server MySql menurut grup sumber daya dan nama server.

### Contoh 2: Dapatkan string koneksi server MySql menurut identitas
```powershell
PS C:\> Get-AzMySqlServer -ResourceGroupName PowershellMySqlTest -ServerName mysql-test | Get-AzMySqlConnectionString -Client PHP

$con=mysqli_init(); mysqli_real_connect($con, "mysql-test.mysql.database.azure.com", "mysql_test@mysql-test", {your_password}, {your_database}, 3306);
```

Cmdlet ini mendapatkan string koneksi server MySql menurut identitas.

## PARAMETERS

### -Client
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
Server untuk string koneksi.
Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20171201.IServer
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
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
Nama grup sumber daya yang berisi sumber daya, Anda dapat memperoleh nilai ini dari API Azure Resource Manager atau portal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20171201.IServer

## OUTPUTS

### System.String

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IServer> : Server untuk string koneksi.
  - `Location <String>`: Lokasi geo-lokasi tempat sumber daya berada
  - `[Tag <ITrackedResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AdministratorLogin <String>]`: Nama masuk administrator server. Hanya dapat ditentukan saat server sedang dibuat (dan diperlukan untuk pembuatan).
  - `[EarliestRestoreDate <DateTime?>]`: Waktu pembuatan titik pemulihan paling awal (format ISO8601)
  - `[FullyQualifiedDomainName <String>]`: Nama domain yang sepenuhnya memenuhi syarat dari server.
  - `[IdentityType <IdentityType?>]`: Tipe identitas. Setel ini ke 'SystemAssigned' agar secara otomatis membuat dan menetapkan Azure Active Directory utama untuk sumber daya.
  - `[InfrastructureEncryption <InfrastructureEncryption?>]`: Status memperlihatkan apakah enkripsi infrastruktur yang diaktifkan server.
  - `[MasterServerId <String>]`: Id server master dari server replika.
  - `[MinimalTlsVersion <MinimalTlsVersionEnum?>]`: Terapkan versi Tls minimal untuk server.
  - `[PublicNetworkAccess <PublicNetworkAccessEnum?>]`: Mengizinkan atau tidak akses jaringan publik untuk server ini. Nilai bersifat opsional tetapi jika diberikan di, harus 'Diaktifkan' atau 'Dinonaktifkan'
  - `[ReplicaCapacity <Int32?>]`: Jumlah maksimum replika yang bisa ada di server master.
  - `[ReplicationRole <String>]`: Replikasi peran server.
  - `[SkuCapacity <Int32?>]`: Skalakan kapasitas, mewakili unit perhitungan server.
  - `[SkuFamily <String>]`: Keluarga perangkat keras.
  - `[SkuName <String>]`: Nama sku, biasanya, tier + keluarga + inti, misalnya B_Gen4_1, GP_Gen5_8.
  - `[SkuSize <String>]`: Kode ukuran, akan diinterpretasikan menurut sumber daya yang tepat.
  - `[SkuTier <SkuTier?>]`: Tingkatan SKU tertentu, misalnya Dasar.
  - `[SslEnforcement <SslEnforcementEnum?>]`: Mengaktifkan penerapan ssl atau tidak saat tersambung ke server.
  - `[StorageProfileBackupRetentionDay <Int32?>]`: Waktu penyimpanan cadangan untuk server.
  - `[StorageProfileGeoRedundantBackup <GeoRedundantBackup?>]`: Mengaktifkan geo-redundan atau tidak untuk pencadangan server.
  - `[StorageProfileStorageAutogrow <StorageAutogrow?>]`: Aktifkan Storage Auto Grow.
  - `[StorageProfileStorageMb <Int32?>]`: Maksimum penyimpanan yang diperbolehkan untuk server.
  - `[UserVisibleState <ServerState?>]`: Status server yang terlihat oleh pengguna.
  - `[Version <ServerVersion?>]`: Versi server.

## RELATED LINKS

