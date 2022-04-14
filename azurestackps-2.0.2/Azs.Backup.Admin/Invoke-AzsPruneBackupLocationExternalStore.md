---
external help file: ''
Module Name: Azs.Backup.Admin
online version: https://docs.microsoft.com/powershell/module/azs.backup.admin/invoke-azsprunebackuplocationexternalstore
schema: 2.0.0
ms.openlocfilehash: 961ffb01fd2217fe15983acd8143e2185717801b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142238090"
---
# Invoke-AzsPruneBackupLocationExternalStore

## SYNOPSIS
Pangkas penyimpanan cadangan eksternal.

## SYNTAX

### PruneExpanded (Default)
```
Invoke-AzsPruneBackupLocationExternalStore [-Location <String>] [-ResourceGroupName <String>]
 [-SubscriptionId <String>] [-OperationType <PruneBackupStoreOperationType>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Memangkas
```
Invoke-AzsPruneBackupLocationExternalStore -Option <IPruneBackupStoreOperationOptionModel>
 [-Location <String>] [-ResourceGroupName <String>] [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### PruneViaIdentity
```
Invoke-AzsPruneBackupLocationExternalStore -InputObject <IBackupAdminIdentity>
 -Option <IPruneBackupStoreOperationOptionModel> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### PruneViaIdentityExpanded
```
Invoke-AzsPruneBackupLocationExternalStore -InputObject <IBackupAdminIdentity>
 [-OperationType <PruneBackupStoreOperationType>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Pangkas penyimpanan cadangan eksternal.

## EXAMPLES

### Contoh 1: Prune external store
```powershell
PS C:\> Invoke-AzsPruneBackupLocationExternalStore

masbackup/progressivebackup/garbage
```

Pangkas bursa eksternal

### Contoh 2: Melakukan dry run yang tidak benar-benar menghapus sampah
```powershell
PS C:\> Invoke-AzsPruneBackupLocationExternalStore -OperationType DryRun

masbackup/progressivebackup/garbage

```

Melakukan dry run yang tidak benar-benar menghilangkan sampah

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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
Pangkas model operasi penyimpanan cadangan.
Untuk membangun, lihat bagian CATATAN untuk properti OPTION dan membuat tabel hash.

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
Mengembalikan true ketika perintah berhasil

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
Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

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

###  Microsoft.Azure.PowerShell.Cmdlets.BackupAdmin.Models.Api20180901.IPruneBackupStoreOperationOptionModel

### Microsoft.Azure.PowerShell.Cmdlets.BackupAdmin.Models.IBackupAdminIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.BackupAdmin.Models.Api20180901.IPruneModel

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT \<IBackupAdminIdentity>: Parameter Identitas
  - `[Backup <String>]`: Nama cadangan.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama lokasi cadangan.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik. ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

OPTION \<IPruneBackupStoreOperationOptionModel>: Pangkas model operasi penyimpanan cadangan.
  - `[OperationType <PruneBackupStoreOperationType?>]`: Jenis operasi.

## RELATED LINKS

