---
external help file: ''
Module Name: Az.MariaDb
online version: https://docs.microsoft.com/powershell/module/az.mariadb/get-azmariadbconnectionstring
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MariaDb/help/Get-AzMariaDbConnectionString.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MariaDb/help/Get-AzMariaDbConnectionString.md
ms.openlocfilehash: 84809c76a141b0450d2870e9e42637feebe1e564
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136379436"
---
# Get-AzMariaDbConnectionString

## SYNOPSIS
Dapatkan string koneksi MariaDB di bawah kerangka kerja tertentu.

## SYNTAX

### ServerName (Default)
```
Get-AzMariaDbConnectionString -Client <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ServerObject
```
Get-AzMariaDbConnectionString -Client <String> -InputObject <IServer> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan string koneksi MariaDB di bawah kerangka kerja tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan string koneksi dari MariaDB
```powershell
PS C:\> Get-AzMariaDbConnectionString -ServerName mariadb-asd-01 -ResourceGroupName mariadb-test-qu5ov0 -Client ADO.NET

Server=mariadb-asd-01.mariadb.database.azure.com; Port=3306; Database={your_database}; Uid=adminuser@mariadb-asd-01; Pwd={your_password}; SslMode=Preferred;
```

Perintah ini mendapatkan string koneksi MariaDB.

### Contoh 2: Mendapatkan string koneksi dari MariaDB
```powershell
PS C:\> Get-AzMariaDbServer -Name mariadb-gp-t03 -ResourceGroupName lucas-manual-test | Get-AzMariaDbConnectionString -Client PHP

$con=mysqli_init();mysqli_ssl_set($con, NULL, NULL, {ca-cert filename}, NULL, NULL); mysqli_real_connect($con, "mariadb-gp-t03.mariadb.database.azure.com", "adminuser@mariadb-gp-t03", {your_password}, {your_database}, 3306);
```

Perintah ini mendapatkan string koneksi MariaDB.

## PARAMETERS

### -Client
Koneksi klien klien

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
DefaultParameters Kawasan Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MariaDb.Models.Api20180601Preview.IServer
Parameter Sets: ServerObject
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
Parameter Sets: ServerName
Aliases: ServerName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya tersebut.

```yaml
Type: System.String
Parameter Sets: ServerName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan

```yaml
Type: System.String
Parameter Sets: ServerName
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

### Microsoft.Azure.PowerShell.Cmdlets.MariaDb.Models.Api20180601Preview.IServer

## OUTPUTS

### System.String

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IServer> : Parameter Identitas
  - `Location <String>`: Lokasi tempat sumber daya berada.
  - `[Tag <ITrackedResourceTags>]`: Metadata khusus aplikasi dalam bentuk pasangan nilai kunci.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AdministratorLogin <String>]`: Nama masuk administrator server. Hanya dapat ditentukan saat server sedang dibuat (dan diperlukan untuk pembuatan).
  - `[EarliestRestoreDate <DateTime?>]`: Waktu pembuatan titik pemulihan paling awal (format ISO8601)
  - `[FullyQualifiedDomainName <String>]`: Nama domain yang sepenuhnya memenuhi syarat dari server.
  - `[IdentityType <IdentityType?>]`: Tipe identitas. Setel ini ke 'SystemAssigned' agar secara otomatis membuat dan menetapkan Azure Active Directory utama untuk sumber daya.
  - `[MasterServerId <String>]`: Id server master dari server replika.
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

