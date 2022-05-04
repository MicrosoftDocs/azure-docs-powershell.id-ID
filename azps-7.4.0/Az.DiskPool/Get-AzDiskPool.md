---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.diskpool/get-azdiskpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPool.md
ms.openlocfilehash: 9f417c4d95c330650f77a071e9a39276969edbad
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144728241"
---
# Get-AzDiskPool

## SYNOPSIS
Mendapatkan kumpulan Disk.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.diskpool/get-azdiskpool) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzDiskPool [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzDiskPool -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDiskPool -InputObject <IDiskPoolIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzDiskPool -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan kumpulan Disk.

## EXAMPLES

### Contoh 1: Mencantumkan semua Kumpulan Disk dalam grup sumber daya
```powershell
Get-AzDiskPool -ResourceGroupName 'storagepool-rg-test'
```

```output
Name             Location    Status    ProvisioningState AvailabilityZone
----             --------    ------    ----------------- ----------------
disk-pool-1      eastus2euap Running   Succeeded         {3}
disk-pool-5      eastus2euap Running   Succeeded         {3}
```

Perintah ini mencantumkan semua Kumpulan Disk dalam grup sumber daya

### Contoh 2: Mendapatkan Kumpulan Disk
```powershell
Get-AzDiskPool -ResourceGroupName 'storagepool-rg-test' -Name 'disk-pool-1'
```

```output
Name             Location    Status    ProvisioningState AvailabilityZone
----             --------    ------    ----------------- ----------------
disk-pool-1      eastus2euap Running   Succeeded         {3}
```

Perintah ini mendapatkan Kumpulan Disk.

### Contoh 3: Mencantumkan semua Kumpulan Disk di bawah langganan
```powershell
Get-AzDiskPool
```

```output
Name             Location    Status    ProvisioningState AvailabilityZone
----             --------    ------    ----------------- ----------------
disk-pool-1      eastus2euap Running   Succeeded         {3}
disk-pool-5      eastus2euap Running   Succeeded         {3}
```

Perintah ini mencantumkan semua Kumpulan Disk dalam langganan.

### Contoh 4: Mendapatkan Kumpulan Disk berdasarkan objek
```powershell
New-AzDiskPool -Name 'disk-pool-1' -ResourceGroupName 'storagepool-rg-test' -Location 'westeurope' -SkuName 'Standard' -SkuTier 'Standard' -SubnetId '/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/storagepool-rg-test/providers/Microsoft.Network/virtualNetworks/disk-pool-vnet/subnets/default' -AvailabilityZone "1" | Get-AzDiskPool
```

```output
Name             Location    Status    ProvisioningState AvailabilityZone
----             --------    ------    ----------------- ----------------
disk-pool-1      eastus2euap Running   Succeeded         {3}
```

Perintah ini mendapatkan Kumpulan Disk berdasarkan objek.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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

### -Name
Nama Kumpulan Disk.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: DiskPoolName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: Get, List1
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
Parameter Sets: Get, List, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.IDiskPoolIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IDiskPool

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDiskPoolIdentity>: Parameter Identitas
  - `[DiskPoolName <String>]`: Nama Kumpulan Disk.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[IscsiTargetName <String>]`: Nama Target iSCSI.
  - `[Location <String>]`: Lokasi sumber daya.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar/kecil.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

