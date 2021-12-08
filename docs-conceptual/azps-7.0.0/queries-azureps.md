---
title: Output kueri cmdlet Azure PowerShell kueri
description: Cara membuat kueri untuk sumber daya di Azure dan memformat hasilnya.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 12/07/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 0b698139b176802b59930b66a208eb740d39c7c9
ms.sourcegitcommit: 2a404a7aac28f6568e0e17912814e4403ea5d0d9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/08/2021
ms.locfileid: "134110973"
---
# <a name="query-output-of-azure-powershell"></a>Output kueri Azure PowerShell

Hasil dari setiap Azure PowerShell cmdlet merupakan objek Azure PowerShell. Bahkan cmdlet yang tidak operasinya tidak secara eksplisit mungkin mengembalikan nilai yang dapat diperiksa, untuk memberikan informasi tentang `Get-` sumber daya yang dibuat atau diubah. Sementara sebagian besar cmdlet mengembalikan sebuah objek, beberapa mengembalikan array yang harus iterated melaluinya.

Dalam hampir semua kasus, Anda membuat output kueri Azure PowerShell dengan cmdlet [Select-Object.](/powershell/module/Microsoft.PowerShell.Utility/Select-Object) Output bisa difilter dengan [Where-Object](/powershell/module/Microsoft.PowerShell.Core/Where-Object).

## <a name="select-simple-properties"></a>Pilih properti sederhana

Dalam format tabel default, cmdlet Azure PowerShell tidak menampilkan semua properti yang tersedia. Anda dapat memperoleh properti penuh menggunakan cmdlet [Format-List,](/powershell/module/microsoft.powershell.utility/format-list) atau dengan pemipaan output `Select-Object -Property *` ke:

```azurepowershell-interactive
Get-AzVM -Name TestVM -ResourceGroupName TestGroup |
  Select-Object -Property *
```

```Output
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

Setelah mengetahui nama properti yang diminati, Anda dapat menggunakan nama properti tersebut `Select-Object` untuk langsung mendapatkannya:

```azurepowershell-interactive
Get-AzVM -Name TestVM -ResourceGroupName TestGroup |
  Select-Object -Property Name, VmId, ProvisioningState
```

```Output
Name   VmId                                 ProvisioningState
----   ----                                 -----------------
TestVM 711d8ed1-b888-4c52-8ab9-66f07b87eb6b Succeeded
```

Output dari menggunakan `Select-Object` selalu diformat untuk menampilkan informasi yang diminta. Untuk mempelajari tentang cara menggunakan pemformatan sebagai bagian dari hasil cmdlet kueri, lihat [Memformat Azure PowerShell output cmdlet](formatting-output.md).

## <a name="select-nested-properties"></a>Pilih properti bertum tersedia

Beberapa properti dalam Azure PowerShell output cmdlet menggunakan objek bertumpuk, `StorageProfile` seperti properti `Get-AzVM` output. Untuk mendapatkan nilai dari properti bertumbat, sediakan nama tampilan dan jalur lengkap ke nilai yang ingin Anda periksa sebagai bagian dari argumen kamus untuk `Select-Object` :

```azurepowershell-interactive
Get-AzVM -ResourceGroupName TestGroup |
  Select-Object -Property Name, @{Name='OSType'; Expression={$_.StorageProfile.OSDisk.OSType}}
```

```Output
Name     OSType
----     ------
TestVM    Linux
TestVM2   Linux
WinVM   Windows
```

Setiap argumen kamus memilih satu properti dari objek. Properti yang akan diekstrak harus merupakan bagian dari ekspresi.

## <a name="filter-results"></a>Memfilter hasil

Cmdlet `Where-Object` memungkinkan Anda memfilter hasil berdasarkan nilai properti apa pun, termasuk properti bertumpuk. Contoh berikutnya memperlihatkan cara penggunaan `Where-Object` untuk menemukan VM Linux dalam grup sumber daya.

```azurepowershell-interactive
Get-AzVM -ResourceGroupName TestGroup |
  Where-Object {$_.StorageProfile.OSDisk.OSType -eq 'Linux'}
```

```Output
ResourceGroupName    Name Location          VmSize OsType        NIC ProvisioningState Zone
-----------------    ---- --------          ------ ------        --- ----------------- ----
TestGroup          TestVM  westus2 Standard_D2s_v3  Linux  testvm299         Succeeded
TestGroup         TestVM2  westus2 Standard_D2s_v3  Linux testvm2669         Succeeded
```

Anda bisa pipetkan hasil `Select-Object` dari dan satu sama `Where-Object` lain. Untuk tujuan kinerja, sebaiknya selalu dilakukan operasi `Where-Object` `Select-Object` sebelum:

```azurepowershell-interactive
Get-AzVM -ResourceGroupName TestGroup |
  Where-Object {$_.StorageProfile.OsDisk.OsType -eq 'Linux'} |
  Select-Object -Property Name, VmID, ProvisioningState
```

```Output
Name    VmId                                 ProvisioningState
----    ----                                 -----------------
TestVM  711d8ed1-b888-4c52-8ab9-66f07b87eb6  Succeeded
TestVM2 cbcee769-dd78-45e3-a14d-2ad11c647d0  Succeeded
```
