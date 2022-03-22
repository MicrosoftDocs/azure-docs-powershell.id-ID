---
title: Mengkueri output cmdlet Azure PowerShell
description: Cara mengkueri sumber daya di Azure dan memformat hasilnya.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/10/2019
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 71de99fec7de36cf8cc0fe3e8840fb55cedc5db7
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421099"
---
# <a name="query-output-of-azure-powershell"></a>Mengkueri output Azure PowerShell 

Hasil dari setiap cmdlet Azure PowerShell adalah objek Azure PowerShell. Bahkan cmdlet yang secara eksplisit bukan operasi `Get-` dapat mengembalikan nilai yang dapat diperiksa, untuk memberikan informasi tentang sumber daya yang dibuat atau dimodifikasi. Sementara sebagian besar cmdlet mengembalikan objek tunggal, beberapa cmdlet mengembalikan array yang harus diiterasi.

Dalam hampir semua kasus, Anda mengkueri output dari Azure PowerShell dengan cmdlet [Select-Object](/powershell/module/Microsoft.PowerShell.Utility/Select-Object), sering disingkat menjadi `select`. Output dapat difilter dengan [Where-Object](/powershell/module/Microsoft.PowerShell.Core/Where-Object), atau aliasnya `where`.

## <a name="select-simple-properties"></a>Memilih properti sederhana

Dalam format tabel default, cmdlet Azure PowerShell tidak menampilkan semua properti yang tersedia. Anda dapat mendapatkan properti lengkap dengan menggunakan cmdlet [Format-List](/powershell/module/microsoft.powershell.utility/format-list), atau dengan mengeluarkan output ke `Select-Object *`:

```azurepowershell-interactive
Get-AzVM -Name TestVM -ResourceGroupName TestGroup | Select-Object *
```

```output
ResourceGroupName        : TESTGROUP
Id                       : /subscriptions/711d8ed1-b888-4c52-8ab9-66f07b87eb6b/resourceGroups/TESTGROUP/providers/Micro
                           soft.Compute/virtualMachines/TestVM
VmId                     : 711d8ed1-b888-4c52-8ab9-66f07b87eb6b
Name                     : TestVM
Type                     : Microsoft.Compute/virtualMachines
Location                 : westus2
LicenseType              :
Tags                     : {}
AvailabilitySetReference :
DiagnosticsProfile       :
Extensions               : {}
HardwareProfile          : Microsoft.Azure.Management.Compute.Models.HardwareProfile
InstanceView             :
NetworkProfile           : Microsoft.Azure.Management.Compute.Models.NetworkProfile
OSProfile                : Microsoft.Azure.Management.Compute.Models.OSProfile
Plan                     :
ProvisioningState        : Succeeded
StorageProfile           : Microsoft.Azure.Management.Compute.Models.StorageProfile
DisplayHint              : Compact
Identity                 :
Zones                    : {}
FullyQualifiedDomainName :
AdditionalCapabilities   :
RequestId                : 711d8ed1-b888-4c52-8ab9-66f07b87eb6b
StatusCode               : OK
```

Secara Anda mengetahui nama properti yang Anda minati, Anda dapat menggunakan nama properti tersebut dengan `Select-Object` untuk mendapatkannya secara langsung:

```azurepowershell-interactive
Get-AzVM -Name TestVM -ResourceGroupName TestGroup | Select-Object Name,VmId,ProvisioningState
```

```output
Name   VmId                                 ProvisioningState
----   ----                                 -----------------
TestVM 711d8ed1-b888-4c52-8ab9-66f07b87eb6b Succeeded
```

Output dari penggunaan `Select-Object` selalu diformat untuk menampilkan informasi yang diminta. Untuk mempelajari tentang menggunakan pemformatan sebagai bagian dari mengkueri hasil cmdlet, lihat [Memformat output cmdlet Azure PowerShell](formatting-output.md).

## <a name="select-nested-properties"></a>Memilih properti berlapis

Beberapa properti dalam output cmdlet Azure PowerShell menggunakan objek berlapis, seperti properti `StorageProfile` dari output `Get-AzVM`. Untuk mendapatkan nilai dari properti berlapis, berikan nama tampilan dan jalur lengkap ke nilai yang ingin Anda periksa sebagai bagian dari argumen kamus untuk `Select-Object`:

```azurepowershell-interactive
Get-AzVM -ResourceGroupName TestGroup | `
    Select-Object Name,@{Name="OSType"; Expression={$_.StorageProfile.OSDisk.OSType}}
```

```output
Name     OSType
----     ------
TestVM    Linux
TestVM2   Linux
WinVM   Windows
```

Setiap argumen kamus memilih satu properti dari objek. Properti yang akan diekstraksi harus menjadi bagian dari ekspresi.

## <a name="filter-results"></a>Memfilter hasil 

Cmdlet `Where-Object` memungkinkan Anda memfilter hasil berdasarkan nilai properti apa pun, termasuk properti berlapis. Contoh berikutnya menunjukkan cara menggunakan `Where-Object` untuk menemukan VM Linux dalam grup sumber daya.

```azurepowershell-interactive
Get-AzVM -ResourceGroupName TestGroup | `
    Where-Object {$_.StorageProfile.OSDisk.OSType -eq "Linux"}
```

```output
ResourceGroupName    Name Location          VmSize OsType        NIC ProvisioningState Zone
-----------------    ---- --------          ------ ------        --- ----------------- ----
TestGroup          TestVM  westus2 Standard_D2s_v3  Linux  testvm299         Succeeded
TestGroup         TestVM2  westus2 Standard_D2s_v3  Linux testvm2669         Succeeded
```

Anda dapat mengeluarkan hasil `Select-Object` dan `Where-Object` ke satu sama lain. Untuk tujuan performa, selalu disarankan untuk menempatkan operasi `Where-Object` sebelum `Select-Object`:

```azurepowershell-interactive
Get-AzVM -ResourceGroupName TestGroup | `
    Where-Object {$_.StorageProfile.OsDisk.OsType -eq "Linux"} | `
    Select-Object Name,VmID,ProvisioningState
```

```output
Name    VmId                                 ProvisioningState
----    ----                                 -----------------
TestVM  711d8ed1-b888-4c52-8ab9-66f07b87eb6  Succeeded
TestVM2 cbcee769-dd78-45e3-a14d-2ad11c647d0  Succeeded
```
