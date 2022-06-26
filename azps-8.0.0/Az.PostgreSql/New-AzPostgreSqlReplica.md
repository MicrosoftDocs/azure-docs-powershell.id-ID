---
external help file: ''
Module Name: Az.PostgreSql
online version: https://docs.microsoft.com/powershell/module/az.postgresql/new-azpostgresqlreplica
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PostgreSql/help/New-AzPostgreSqlReplica.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PostgreSql/help/New-AzPostgreSqlReplica.md
ms.openlocfilehash: 5541bcd0bbd5ca0e20d79bccb02bfe8497df51cd
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146625286"
---
# New-AzPostgreSqlReplica

## SYNOPSIS
Membuat replika baru dari database yang sudah ada.

## SYNTAX

```
New-AzPostgreSqlReplica -ReplicaName <String> -ResourceGroupName <String> -Master <IServer>
 [-SubscriptionId <String>] [-Location <String>] [-Sku <String>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat replika baru dari database yang sudah ada.

## EXAMPLES

### Contoh 1: Membuat replika server PostgreSql baru
```powershell
Get-AzPostgreSqlServer -ResourceGroupName PostgreSqlTestRG -ServerName PostgreSqlTestServer | New-AzPostgreSqlReplica -ReplicaName PostgreSqlTestServerReplica -ResourceGroupName PostgreSqlTestRG
```

```output
Name                        Location AdministratorLogin Version StorageProfileStorageMb SkuName   SkuTier        SslEnforcement
----                        -------- ------------------ ------- ----------------------- -------   -------        --------------
postgresqltestserverreplica eastus   pwsh               9.6     5120                    GP_Gen5_4 GeneralPurpose Enabled
```

Cmdlet ini membuat replika server PostgreSql baru.

### Contoh 2: Membuat replika server PostgreSql baru
```powershell
$pgDb = Get-AzPostgreSqlServer -ResourceGroupName PostgreSqlTestRG -ServerName PostgreSqlTestServer 
New-AzPostgreSqlReplica -Master $pgDb -ReplicaName PostgreSqlTestServerReplica -ResourceGroupName PostgreSqlTestRG
```

```output
Name                        Location AdministratorLogin Version StorageProfileStorageMb SkuName   SkuTier        SslEnforcement
----                        -------- ------------------ ------- ----------------------- -------   -------        --------------
postgresqltestserverreplica eastus   pwsh               9.6     5120                    GP_Gen5_4 GeneralPurpose Enabled
```

Cmdlet ini membuat replika server PostgreSql baru.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan.

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

### -Lokasi
Lokasi tempat sumber daya berada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Master
Objek server sumber untuk membuat replika.
Untuk membuat, lihat bagian CATATAN untuk properti MASTER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.PostgreSql.Models.Api20171201.IServer
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron.

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

### -ReplicaName
Nama server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ReplicaServerName, Name

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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sku
Nama sku, biasanya, tingkat + keluarga + inti, misalnya B_Gen4_1, GP_Gen5_8.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan yang mengidentifikasi langganan Azure.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.PostgreSql.Models.Api20171201.IServer

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.PostgreSql.Models.Api20171201.IServer

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


MASTER `<IServer>`: Objek server sumber untuk membuat replika.
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

