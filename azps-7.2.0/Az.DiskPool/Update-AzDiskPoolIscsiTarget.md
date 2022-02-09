---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.diskpool/update-azdiskpooliscsitarget
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Update-AzDiskPoolIscsiTarget.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Update-AzDiskPoolIscsiTarget.md
ms.openlocfilehash: 7d006133f22413b05202feeefd539774eeda480e
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138288924"
---
# Update-AzDiskPoolIscsiTarget

## SYNOPSIS
Memperbarui Target iSCSI.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzDiskPoolIscsiTarget -DiskPoolName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-Lun <IIscsiLun[]>] [-ManagedBy <String>] [-ManagedByExtended <String[]>]
 [-StaticAcl <IAcl[]>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzDiskPoolIscsiTarget -InputObject <IDiskPoolIdentity> [-Lun <IIscsiLun[]>] [-ManagedBy <String>]
 [-ManagedByExtended <String[]>] [-StaticAcl <IAcl[]>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui Target iSCSI.

## EXAMPLES

### Contoh 1: Memperbarui target iSCSI
```powershell
PS C:\> $lun0 = New-AzDiskPoolIscsiLunObject -ManagedDiskAzureResourceId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/storagepool-rg-test/providers/Microsoft.Compute/disks/disk1" -Name "lun0"
PS C:\> Update-AzDiskPoolIscsiTarget -Name 'target0' -DiskPoolName 'disk-pool-5' -ResourceGroupName 'storagepool-rg-test' -Lun @($lun0)

Name               Type
----               ----
target0 Microsoft.StoragePool/diskPools/iscsiTargets
```

Perintah ini memperbarui target iSCSI.

### Contoh 2: Memperbarui target iSCSI menurut objek
```powershell
PS C:\> $lun0 = New-AzDiskPoolIscsiLunObject -ManagedDiskAzureResourceId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/storagepool-rg-test/providers/Microsoft.Compute/disks/disk1" -Name "lun0"
PS C:\> Get-AzDiskPoolIscsiTarget -ResourceGroupName 'storagepool-rg-test' -DiskPoolName 'disk-pool-5' -Name 'target0' | Update-AzDiskPoolIscsiTarget -Lun @($lun0)

Name               Type
----               ----
target0 Microsoft.StoragePool/diskPools/iscsiTargets
```

Perintah ini memperbarui target iSCSI menurut objek.

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

### -DiskPoolName
Nama Disk Pool.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.IDiskPoolIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lun
Daftar LUN yang akan diekspos melalui Target iSCSI.
Untuk membuat, lihat bagian CATATAN untuk properti LUN dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IIscsiLun[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedBy
Id sumber daya Azure. Menunjukkan apakah sumber daya ini dikelola oleh sumber daya Azure lain.

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

### -ManagedByExtended
Daftar id sumber daya Azure yang mengelola sumber daya ini.

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

### -Nama
Nama Target iSCSI.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: IscsiTargetName

Required: True
Position: Named
Default value: None
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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticAcl
Daftar Kontrol Akses (ACL, Access Control List) untuk Target iSCSI; menentukan kebijakan masker LUN Untuk membangun, lihat bagian CATATAN untuk properti STATICACL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IAcl[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.IDiskPoolIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IIscsiTarget

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDiskPoolIdentity>: Parameter Identitas
  - `[DiskPoolName <String>]`: Nama Disk Pool.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[IscsiTargetName <String>]`: Nama Target iSCSI.
  - `[Location <String>]`: Lokasi sumber daya.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.

LUN <IIscsiLun[]>: Daftar LUN yang akan diekspos melalui Target iSCSI.
  - `ManagedDiskAzureResourceId <String>`: ID Sumber Daya Azure dari Disk yang Dikelola.
  - `Name <String>`: Nama yang ditentukan pengguna untuk iSCSI LUN; contoh: "lun0"

STATICACL <IAcl[]>: Access Control List (ACL) untuk Target iSCSI; menentukan kebijakan masker LUN
  - `InitiatorIqn <String>`: iSCSI inisiator IQN (Nama yang Memenuhi Syarat iSCSI); contoh: "iqn.2005-03.org.iscsi:client".
  - `MappedLun <String[]>`: Daftar nama LUN yang dipetakan ke ACL.

## RELATED LINKS

