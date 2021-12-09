---
external help file: ''
Module Name: Azs.Backup.Admin
online version: https://docs.microsoft.com/powershell/module/azs.backup.admin/invoke-azsprunebackuplocationexternalstore
schema: 2.0.0
ms.openlocfilehash: 961ffb01fd2217fe15983acd8143e2185717801b
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "134505411"
---
# Invoke-AzsPruneBackupLocationExternalStore

## SYNOPSIS
Dimensi toko cadangan eksternal.

## SYNTAX

### UalneExpanded (Default)
```
Invoke-AzsPruneBackupLocationExternalStore [-Location <String>] [-ResourceGroupName <String>]
 [-SubscriptionId <String>] [-OperationType <PruneBackupStoreOperationType>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Innsbruckne
```
Invoke-AzsPruneBackupLocationExternalStore -Option <IPruneBackupStoreOperationOptionModel>
 [-Location <String>] [-ResourceGroupName <String>] [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### besViaIdentity
```
Invoke-AzsPruneBackupLocationExternalStore -InputObject <IBackupAdminIdentity>
 -Option <IPruneBackupStoreOperationOptionModel> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### ViaIdentityExpanded
```
Invoke-AzsPruneBackupLocationExternalStore -InputObject <IBackupAdminIdentity>
 [-OperationType <PruneBackupStoreOperationType>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Dimensi toko cadangan eksternal.

## EXAMPLES

### Contoh 1: Data dari external store
```powershell
PS C:\> Invoke-AzsPruneBackupLocationExternalStore

masbackup/progressivebackup/garbage
```

Toko eksternal External External Store

### Contoh 2: Jalankan proses kering yang tidak benar-benar menghapus sampah
```powershell
PS C:\> Invoke-AzsPruneBackupLocationExternalStore -OperationType DryRun

masbackup/progressivebackup/garbage

```

Menjalankan proses kering yang tidak benar-benar menghapus sampah

## PARAMETERS

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.BackupAdmin.Models.IBackupAdminIdentity
Parameter Sets: PruneViaIdentity, PruneViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Nama lokasi cadangan.

```yaml
Type: System.String
Parameter Sets: Prune, PruneExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### -OperationType
Jenis operasi.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.BackupAdmin.Support.PruneBackupStoreOperationType
Parameter Sets: PruneExpanded, PruneViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Option
Model operasi penyimpanan cadangan Database database.
Untuk membuat, lihat bagian CATATAN untuk properti OPTION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.BackupAdmin.Models.Api20180901.IPruneBackupStoreOperationOptionModel
Parameter Sets: Prune, PruneViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

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
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Prune, PruneExpanded
Aliases:

Required: False
Position: Named
Default value: "system.$((Get-AzLocation)[0].Location)"
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure Anda.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: Prune, PruneExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  Microsoft.Azure.PowerShell.Cmdlets.BackupAdmin.Models.Api20180901.IPruneBackupStoreOperationOptionModel

### Microsoft.Azure.PowerShell.Cmdlets.BackupAdmin.Models.IBackupAdminIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.BackupAdmin.Models.Api20180901.IPruneModel

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT \<IBackupAdminIdentity> : Parameter Identitas
  - `[Backup <String>]`: Nama cadangan.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama lokasi cadangan.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

OPTION \<IPruneBackupStoreOperationOptionModel> : Model operasi penyimpanan cadangan Kode 365.
  - `[OperationType <PruneBackupStoreOperationType?>]`: Tipe operasi.

## RELATED LINKS

