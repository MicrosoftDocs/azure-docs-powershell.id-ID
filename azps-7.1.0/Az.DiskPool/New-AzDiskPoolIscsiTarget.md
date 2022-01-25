---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.diskpool/new-azdiskpooliscsitarget
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiTarget.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiTarget.md
ms.openlocfilehash: 45bc0ba98efe892ad26d263c3cae668dfd8e4545
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136756159"
---
# New-AzDiskPoolIscsiTarget

## SYNOPSIS
Buat atau Perbarui Target iSCSI.

## SYNTAX

```
New-AzDiskPoolIscsiTarget -DiskPoolName <String> -Name <String> -ResourceGroupName <String>
 -AclMode <IscsiTargetAclMode> [-SubscriptionId <String>] [-Lun <IIscsiLun[]>] [-ManagedBy <String>]
 [-ManagedByExtended <String[]>] [-StaticAcl <IAcl[]>] [-TargetIqn <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Buat atau Perbarui Target iSCSI.

## EXAMPLES

### Contoh 1: Membuat target iSCSI
```powershell
PS C:\> New-AzDiskPoolIscsiTarget -DiskPoolName 'disk-pool-1' -Name 'target1' -ResourceGroupName 'storagepool-rg-test' -AclMode 'Dynamic'

Name               Type
----               ----
target1 Microsoft.StoragePool/diskPools/iscsiTargets
```

Perintah ini akan membuat target iSCSI.

## PARAMETERS

### -AclMode
Mode untuk konektivitas Target.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Support.IscsiTargetAclMode
Parameter Sets: (All)
Aliases:

Required: True
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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetIqn
iSCSI Target IQN (nama yang Memenuhi Syarat iSCSI); contoh: "iqn.2005-03.org.iscsi:server".

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IIscsiTarget

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LUN <IIscsiLun[]>: Daftar LUN yang akan diekspos melalui Target iSCSI.
  - `ManagedDiskAzureResourceId <String>`: ID Sumber Daya Azure dari Disk yang Dikelola.
  - `Name <String>`: Nama yang ditentukan pengguna untuk iSCSI LUN; contoh: "lun0"

STATICACL <IAcl[]>: Access Control List (ACL) untuk Target iSCSI; menentukan kebijakan masker LUN
  - `InitiatorIqn <String>`: iSCSI inisiator IQN (Nama yang Memenuhi Syarat iSCSI); contoh: "iqn.2005-03.org.iscsi:client".
  - `MappedLun <String[]>`: Daftar nama LUN yang dipetakan ke ACL.

## RELATED LINKS

