---
external help file: ''
Module Name: Az.MariaDb
online version: https://docs.microsoft.com/powershell/module/az.mariadb/restore-azmariadbserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MariaDb/help/Restore-AzMariaDbServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MariaDb/help/Restore-AzMariaDbServer.md
ms.openlocfilehash: 218dccbf8fc20d4c495da28b462f433a2a942cac
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146607664"
---
# Restore-AzMariaDbServer

## SYNOPSIS
Pulihkan MariaDB dari MariaDB yang ada.

## SYNTAX

```
Restore-AzMariaDbServer -Name <String> -RestorePointInTime <DateTime> [-InputObject <IServer>]
 [-ResourceGroupName <String>] [-ServerName <String>] [-SubscriptionId <String>] [-Location <String>]
 [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Pulihkan MariaDB dari MariaDB yang ada.

## EXAMPLES

### Contoh 1: Pulihkan PointInTime MariaDB berdasarkan nama server.
```powershell
Restore-AzMariaDbServer -Name restore-db01 -ServerName mariadb-test-usegeo -ResourceGroupName mariadb-test-4rih5z -RestorePointInTime $(Get-Date) -Location eastus
```

```output
Name         Location AdministratorLogin Version StorageProfileStorageMb SkuName   SkuTier        SslEnforcement
----         -------- ------------------ ------- ----------------------- -------   -------        --------------
restore-db01 eastus   adminuser          10.2    5120                    GP_Gen5_4 GeneralPurpose Enabled
```

Perintah ini memulihkan PointInTime MariaDB berdasarkan nama server.

### Contoh 2: Memulihkan PointInTime MariaDB menurut objek server
```powershell
$db = Get-AzMariaDbServer -Name mariadb-test-usegeo -ResourceGroupName mariadb-test-4rih5z
Restore-AzMariaDbServer -Name restore-db02 -InputObject $db -RestorePointInTime $(Get-Date) -Location eastus
```

```output
Name         Location AdministratorLogin Version StorageProfileStorageMb SkuName   SkuTier        SslEnforcement
----         -------- ------------------ ------- ----------------------- -------   -------        --------------
restore-db02 eastus   adminuser          10.2    5120                    GP_Gen5_4 GeneralPurpose Enabled
```

Perintah ini memulihkan PointInTime MariaDB menurut objek server.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
wilayah DefaultParameters Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.MariaDb.Models.Api20180601Preview.IServer
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Name
Nama server dest untuk dipulihkan.

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

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya.
Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.

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

### -RestorePointInTime
region PointInTimeRestore Lokasi sumber daya berada.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Nama server sumber untuk dipulihkan.

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
Mendapatkan Id langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan adalah bagian dari URI untuk setiap panggilan layanan.

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

### Microsoft.Azure.PowerShell.Cmdlets.MariaDb.Models.Api20180601Preview.IServer

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MariaDb.Models.Api20180601Preview.IServer

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IServer>`: Objek server sumber untuk dipulihkan.
  - `Location <String>`: Lokasi tempat sumber daya berada.
  - `[Tag <ITrackedResourceTags>]`: Metadata khusus aplikasi dalam bentuk pasangan kunci-nilai.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AdministratorLogin <String>]`: Nama masuk administrator server. Hanya dapat ditentukan ketika server sedang dibuat (dan diperlukan untuk pembuatan).
  - `[EarliestRestoreDate <DateTime?>]`: Waktu pembuatan titik pemulihan paling awal (format ISO8601)
  - `[FullyQualifiedDomainName <String>]`: Nama domain server yang sepenuhnya memenuhi syarat.
  - `[IdentityType <IdentityType?>]`: Jenis identitas. Atur ini ke 'SystemAssigned' untuk membuat dan menetapkan prinsipal Azure Active Directory secara otomatis untuk sumber daya.
  - `[MasterServerId <String>]`: Id server master dari server replika.
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

