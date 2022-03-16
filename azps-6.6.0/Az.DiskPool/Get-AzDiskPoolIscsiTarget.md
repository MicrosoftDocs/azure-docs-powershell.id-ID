---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.diskpool/get-azdiskpooliscsitarget
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolIscsiTarget.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolIscsiTarget.md
ms.openlocfilehash: 4ccabe744af01c0fc49b42bceeb553be71760b95
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139939795"
---
# Get-AzDiskPoolIscsiTarget

## SYNOPSIS
Dapatkan Target iSCSI.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.diskpool/get-azdiskpooliscsitarget) untuk informasi terkini.

## SYNTAX

### Daftar (Default)
```
Get-AzDiskPoolIscsiTarget -DiskPoolName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzDiskPoolIscsiTarget -DiskPoolName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDiskPoolIscsiTarget -InputObject <IDiskPoolIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan Target iSCSI.

## EXAMPLES

### Contoh 1: List iSCSI targets in a Disk Pool
```powershell
PS C:\> Get-AzDiskPoolIscsiTarget -ResourceGroupName 'storagepool-rg-test' -DiskPoolName 'disk-pool-5'

Name               Type
----               ----
target0 Microsoft.StoragePool/diskPools/iscsiTargets
```

Perintah ini mencantumkan semua target iSCSI di Disk Pool.

### Contoh 2: Dapatkan target iSCSI
```powershell
PS C:\> Get-AzDiskPoolIscsiTarget -ResourceGroupName 'storagepool-rg-test' -DiskPoolName 'disk-pool-5' -Name 'target0'

Name               Type
----               ----
target0 Microsoft.StoragePool/diskPools/iscsiTargets
```

Perintah ini mendapatkan target iSCSI.

### Contoh 3: Dapatkan target iSCSI menurut objek
```powershell
PS C:\> New-AzDiskPoolIscsiTarget -DiskPoolName 'disk-pool-5' -Name 'target1' -ResourceGroupName 'storagepool-rg-test' -AclMode 'Dynamic' | Get-AzDiskPoolIscsiTarget

Name               Type
----               ----
target1 Microsoft.StoragePool/diskPools/iscsiTargets
```

Perintah ini mendapatkan target iSCSI berdasarkan objek.

## PARAMETERS

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
Parameter Sets: Get, List
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
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Target iSCSI.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: IscsiTargetName

Required: True
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
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

## RELATED LINKS

