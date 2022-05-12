---
description: Cara mengkueri sumber daya di Azure dan memformat hasilnya.
ms.custom: devx-track-azurepowershell
ms.date: 05/11/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Mengkueri output cmdlet Azure PowerShell
ms.openlocfilehash: 4142602dbdddd245e40302907f5be6cb96895fc4
ms.sourcegitcommit: 97a10cac523612de4dbece96f25bd7e3f2431276
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/12/2022
ms.locfileid: "144957524"
---
# <a name="query-output-of-azure-powershell"></a>Mengkueri output Azure PowerShell

Hasil dari setiap cmdlet Azure PowerShell adalah objek Azure PowerShell. Bahkan cmdlet yang secara eksplisit bukan operasi `Get-` dapat mengembalikan nilai yang dapat diperiksa, untuk memberikan informasi tentang sumber daya yang dibuat atau dimodifikasi. Sementara sebagian besar cmdlet mengembalikan objek tunggal, beberapa cmdlet mengembalikan array yang harus diiterasi.

Dalam hampir semua kasus, Anda mengkueri output dari Azure PowerShell dengan cmdlet [Select-Object](/powershell/module/Microsoft.PowerShell.Utility/Select-Object). Output dapat difilter dengan [Where-Object](/powershell/module/Microsoft.PowerShell.Core/Where-Object).

## <a name="select-simple-properties"></a>Memilih properti sederhana

Dalam format tabel default, cmdlet Azure PowerShell tidak menampilkan semua properti yang tersedia. Anda dapat mendapatkan properti lengkap menggunakan cmdlet [Format-List](/powershell/module/microsoft.powershell.utility/format-list), atau dengan mengeluarkan output ke `Select-Object -Property *`:

```azurepowershell-interactive
Get-AzVM -Name TestVM -ResourceGroupName TestGroup |
  Select-Object -Property *
```

```Output
ResourceGroupName        : TESTGROUP
Id                       : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/TESTGROUP/providers/Micro
                           soft.Compute/virtualMachines/TestVM
VmId                     : 00000000-0000-0000-0000-000000000000
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
RequestId                : 00000000-0000-0000-0000-000000000000
StatusCode               : OK
```

Secara Anda mengetahui nama properti yang Anda minati, Anda dapat menggunakan nama properti tersebut dengan `Select-Object` untuk mendapatkannya secara langsung:

```azurepowershell-interactive
Get-AzVM -Name TestVM -ResourceGroupName TestGroup |
  Select-Object -Property Name, VmId, ProvisioningState
```

```Output
Name   VmId                                 ProvisioningState
----   ----                                 -----------------
TestVM 00000000-0000-0000-0000-000000000000 Succeeded
```

Output dari penggunaan `Select-Object` selalu diformat untuk menampilkan informasi yang diminta. Untuk mempelajari tentang menggunakan pemformatan sebagai bagian dari mengkueri hasil cmdlet, lihat [Memformat output cmdlet Azure PowerShell](formatting-output.md).

## <a name="select-nested-properties"></a>Memilih properti berlapis

Beberapa properti dalam output cmdlet Azure PowerShell menggunakan objek berlapis, seperti properti `StorageProfile` dari output `Get-AzVM`. Untuk mendapatkan nilai dari properti berlapis, berikan nama tampilan dan jalur lengkap ke nilai yang ingin Anda periksa sebagai bagian dari argumen kamus untuk `Select-Object`:

```azurepowershell-interactive
Get-AzVM -ResourceGroupName TestGroup |
  Select-Object -Property Name, @{label='OSType'; expression={$_.StorageProfile.OSDisk.OSType}}
```

```Output
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
Get-AzVM -ResourceGroupName TestGroup |
  Where-Object {$_.StorageProfile.OSDisk.OSType -eq 'Linux'}
```

```Output
ResourceGroupName    Name Location          VmSize OsType        NIC ProvisioningState Zone
-----------------    ---- --------          ------ ------        --- ----------------- ----
TestGroup          TestVM  westus2 Standard_D2s_v3  Linux  testvm299         Succeeded
TestGroup         TestVM2  westus2 Standard_D2s_v3  Linux testvm2669         Succeeded
```

Anda dapat mengeluarkan hasil `Select-Object` dan `Where-Object` ke satu sama lain. Untuk tujuan performa, selalu disarankan untuk menempatkan operasi `Where-Object` sebelum `Select-Object`:

```azurepowershell-interactive
Get-AzVM -ResourceGroupName TestGroup |
  Where-Object {$_.StorageProfile.OsDisk.OsType -eq 'Linux'} |
  Select-Object -Property Name, VmID, ProvisioningState
```

```Output
Name    VmId                                  ProvisioningState
----    ----                                  -----------------
TestVM  00000000-0000-0000-0000-000000000000  Succeeded
TestVM2 00000000-0000-0000-0000-000000000000  Succeeded
```
