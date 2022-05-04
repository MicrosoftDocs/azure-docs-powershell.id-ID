---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.diskpool/new-azdiskpooliscsitarget
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiTarget.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/New-AzDiskPoolIscsiTarget.md
ms.openlocfilehash: ea1607b027bc4ba4dd9e5cc5bafd3afe17bb2ea0
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144700592"
---
# New-AzDiskPoolIscsiTarget

## SYNOPSIS
Membuat atau Memperbarui Target iSCSI.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.diskpool/new-azdiskpooliscsitarget) untuk informasi terbaru.

## SYNTAX

```
New-AzDiskPoolIscsiTarget -DiskPoolName <String> -Name <String> -ResourceGroupName <String>
 -AclMode <IscsiTargetAclMode> [-SubscriptionId <String>] [-Lun <IIscsiLun[]>] [-ManagedBy <String>]
 [-ManagedByExtended <String[]>] [-StaticAcl <IAcl[]>] [-TargetIqn <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau Memperbarui Target iSCSI.

## EXAMPLES

### Contoh 1: Membuat target iSCSI
```powershell
New-AzDiskPoolIscsiTarget -DiskPoolName 'disk-pool-1' -Name 'target1' -ResourceGroupName 'storagepool-rg-test' -AclMode 'Dynamic'
```

```output
Name               Type
----               ----
target1 Microsoft.StoragePool/diskPools/iscsiTargets
```

Perintah ini membuat target iSCSI.

## PARAMETERS

### -AclMode
Mode untuk Konektivitas target.

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
Nama Kumpulan Disk.

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
Untuk membuat, lihat bagian CATATAN untuk properti LUN dan buat tabel hash.

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

### -Name
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
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

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
Access Control List (ACL) untuk Target iSCSI; menentukan kebijakan masking LUN Untuk membangun, lihat bagian NOTES untuk properti STATICACL dan membuat tabel hash.

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
iSCSI Target IQN (Nama Yang Memenuhi Syarat iSCSI); contoh: "iqn.2005-03.org.iscsi:server".

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IIscsiTarget

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LUN <IIscsiLun[]>: Daftar LUN yang akan diekspos melalui Target iSCSI.
  - `ManagedDiskAzureResourceId <String>`: ID Sumber Daya Azure dari Disk Terkelola.
  - `Name <String>`: Nama yang ditentukan pengguna untuk iSCSI LUN; contoh: "lun0"

STATICACL <IAcl[]>: Access Control List (ACL) untuk Target iSCSI; menentukan kebijakan masking LUN
  - `InitiatorIqn <String>`: inisiator iSCSI IQN (Nama Yang Memenuhi Syarat iSCSI); contoh: "iqn.2005-03.org.iscsi:client".
  - `MappedLun <String[]>`: Daftar nama LUN yang dipetakan ke ACL.

## RELATED LINKS

