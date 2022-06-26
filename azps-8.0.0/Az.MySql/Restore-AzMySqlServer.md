---
external help file: ''
Module Name: Az.MySql
online version: https://docs.microsoft.com/powershell/module/az.mysql/restore-azmysqlserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Restore-AzMySqlServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MySql/help/Restore-AzMySqlServer.md
ms.openlocfilehash: b36a99c018d75f4d8332e17bd04b682f9352aff8
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146638894"
---
# Restore-AzMySqlServer

## SYNOPSIS
Memulihkan server dari cadangan yang ada

## SYNTAX

### GeoRestore (Default)
```
Restore-AzMySqlServer -Name <String> -ResourceGroupName <String> -InputObject <IServer> -UseGeoRestore
 [-SubscriptionId <String>] [-Location <String>] [-Sku <String>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### PointInTimeRestore
```
Restore-AzMySqlServer -Name <String> -ResourceGroupName <String> -InputObject <IServer>
 -RestorePointInTime <DateTime> -UsePointInTimeRestore [-SubscriptionId <String>] [-Location <String>]
 [-Sku <String>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Memulihkan server dari cadangan yang ada

## EXAMPLES

### Contoh 1: Memulihkan server MySql menggunakan Pemulihan GeoReplika
```powershell
Get-AzMySqlServer -ResourceGroupName PowershellMySqlTest -ServerName mysql-test-replica | Restore-AzMySqlServer -Name mysql-test -ResourceGroupName PowershellMySqlTest -UseGeoRestore 
```

```output
Name          Location AdministratorLogin Version StorageProfileStorageMb SkuName   SkuTier        SslEnforcement
----          -------- ------------------ ------- ----------------------- -------   -------        --------------
mysql-test-11 eastus   mysql_test         5.7     10240                   GP_Gen5_4 GeneralPurpose Disabled
```

Cmdlet ini memulihkan server MySql menggunakan Pemulihan GeoReplika.

### Contoh 2: Memulihkan server MySql menggunakan Pemulihan PointInTime
```powershell
$restorePointInTime = (Get-Date).AddMinutes(-10)
Get-AzMySqlServer -ResourceGroupName PowershellMySqlTest -ServerName mysql-test | Restore-AzMySqlServer -Name mysql-test-restore -ResourceGroupName PowershellMySqlTest -RestorePointInTime $restorePointInTime -UsePointInTimeRestore
```

```output
Name               Location AdministratorLogin Version StorageProfileStorageMb SkuName   SkuTier        SslEnforcement
----               -------- ------------------ ------- ----------------------- -------   -------        --------------
mysql-test-restore eastus   mysql_test         5.7     10240                   GP_Gen5_4 GeneralPurpose Disabled
```

Cmdlet ini memulihkan server MySql menggunakan Pemulihan PointInTime.

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

### -InputObject
Objek server sumber untuk dipulihkan.
Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20171201.IServer
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya berada.

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

### -Name
Nama server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServerName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -RestorePointInTime
Lokasi sumber daya berada.

```yaml
Type: System.DateTime
Parameter Sets: PointInTimeRestore
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

### -Tag
Metadata khusus aplikasi dalam bentuk pasangan kunci-nilai.

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

### -UseGeoRestore
Menggunakan mode Geo untuk memulihkan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GeoRestore
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsePointInTimeRestore
Gunakan mode PointInTime untuk memulihkan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PointInTimeRestore
Aliases:

Required: True
Position: Named
Default value: None
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

### Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20171201.IServer

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MySql.Models.Api20171201.IServer

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IServer>`: Objek server sumber untuk dipulihkan.
  - `Location <String>`: Lokasi geografis tempat sumber daya berada
  - `[Tag <ITrackedResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AdministratorLogin <String>]`: Nama masuk administrator server. Hanya dapat ditentukan ketika server sedang dibuat (dan diperlukan untuk pembuatan).
  - `[EarliestRestoreDate <DateTime?>]`: Waktu pembuatan titik pemulihan paling awal (format ISO8601)
  - `[FullyQualifiedDomainName <String>]`: Nama domain server yang sepenuhnya memenuhi syarat.
  - `[IdentityType <IdentityType?>]`: Jenis identitas. Atur ini ke 'SystemAssigned' untuk membuat dan menetapkan prinsipal Azure Active Directory untuk sumber daya secara otomatis.
  - `[InfrastructureEncryption <InfrastructureEncryption?>]`: Status memperlihatkan apakah enkripsi infrastruktur yang diaktifkan server.
  - `[MasterServerId <String>]`: Id server master dari server replika.
  - `[MinimalTlsVersion <MinimalTlsVersionEnum?>]`: Terapkan versi Tls minimal untuk server.
  - `[PublicNetworkAccess <PublicNetworkAccessEnum?>]`: Apakah akses jaringan publik diizinkan untuk server ini atau tidak. Nilai bersifat opsional tetapi jika diteruskan, harus 'Diaktifkan' atau 'Dinonaktifkan'
  - `[ReplicaCapacity <Int32?>]`: Jumlah maksimum replika yang dapat dimiliki server master.
  - `[ReplicationRole <String>]`: Peran replikasi server.
  - `[SkuCapacity <Int32?>]`: Kapasitas peningkatan/peluasan skala, mewakili unit komputasi server.
  - `[SkuFamily <String>]`: Keluarga perangkat keras.
  - `[SkuName <String>]`: Nama sku, biasanya, tingkat + keluarga + inti, misalnya B_Gen4_1, GP_Gen5_8.
  - `[SkuSize <String>]`: Kode ukuran, yang akan ditafsirkan oleh sumber daya yang sesuai.
  - `[SkuTier <SkuTier?>]`: Tingkat SKU tertentu, misalnya Dasar.
  - `[SslEnforcement <SslEnforcementEnum?>]`: Aktifkan penegakan ssl atau tidak saat terhubung ke server.
  - `[StorageProfileBackupRetentionDay <Int32?>]`: Hari retensi cadangan untuk server.
  - `[StorageProfileGeoRedundantBackup <GeoRedundantBackup?>]`: Aktifkan Geo-redundan atau tidak untuk pencadangan server.
  - `[StorageProfileStorageAutogrow <StorageAutogrow?>]`: Aktifkan Storage Pertumbuhan Otomatis.
  - `[StorageProfileStorageMb <Int32?>]`: Penyimpanan maks yang diizinkan untuk server.
  - `[UserVisibleState <ServerState?>]`: Status server yang terlihat oleh pengguna.
  - `[Version <ServerVersion?>]`: Versi server.

## RELATED LINKS

