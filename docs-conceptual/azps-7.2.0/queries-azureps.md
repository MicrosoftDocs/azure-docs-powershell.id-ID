---
description: Cara mengkueri sumber daya di Azure dan memformat hasilnya.
ms.custom: devx-track-azurepowershell
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Output kueri cmdlet Azure PowerShell
ms.openlocfilehash: 0cc5845f7a1f00e8b544ff1c8520f0ce987f6b3d
ms.sourcegitcommit: cdca0d3199eb118c98aafb63ffcacc3dd080f0d4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "138855225"
---
# <a name="query-output-of-azure-powershell"></a>Output kueri Azure PowerShell

Hasil setiap cmdlet Azure PowerShell adalah objek yang Azure PowerShell. Bahkan cmdlet yang tidak secara `Get-` eksplisit beroperasi dapat mengembalikan nilai yang dapat diperiksa, untuk memberikan informasi tentang sumber daya yang dibuat atau dimodifikasi. Sementara sebagian besar cmdlet mengembalikan satu objek, beberapa mengembalikan array yang harus di-iterasi.

Dalam hampir semua kasus, Anda meminta output dari Azure PowerShell dengan cmdlet [Select-Object](/powershell/module/Microsoft.PowerShell.Utility/Select-Object). Output dapat difilter dengan [Where-Object](/powershell/module/Microsoft.PowerShell.Core/Where-Object).

## <a name="select-simple-properties"></a>Pilih properti sederhana

Dalam format tabel default, cmdlet Azure PowerShell tidak menampilkan semua properti yang tersedia. Anda bisa mendapatkan properti lengkap menggunakan cmdlet [Format-List](/powershell/module/microsoft.powershell.utility/format-list) , atau dengan menyalurkan output ke `Select-Object -Property *`:

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

Setelah mengetahui nama-nama properti yang Anda minati, Anda dapat menggunakan nama-nama properti tersebut untuk mendapatkannya secara `Select-Object` langsung:

```azurepowershell-interactive
Get-AzVM -Name TestVM -ResourceGroupName TestGroup |
  Select-Object -Property Name, VmId, ProvisioningState
```

```Output
Name   VmId                                 ProvisioningState
----   ----                                 -----------------
TestVM 711d8ed1-b888-4c52-8ab9-66f07b87eb6b Succeeded
```

Output dari penggunaan `Select-Object` selalu diformat untuk menampilkan informasi yang diminta. Untuk mempelajari tentang menggunakan pemformatan sebagai bagian dari kueri hasil cmdlet, lihat [Memformat Azure PowerShell output cmdlet](formatting-output.md).

## <a name="select-nested-properties"></a>Pilih properti bersarang

Beberapa properti dalam output cmdlet Azure PowerShell menggunakan objek bersarang, seperti `StorageProfile` properti `Get-AzVM` output. Untuk mendapatkan nilai dari properti bersarang, berikan nama tampilan dan jalur lengkap ke nilai yang ingin Anda periksa sebagai bagian dari argumen kamus untuk `Select-Object`:

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

Setiap argumen kamus memilih satu properti dari objek. Properti untuk mengekstrak harus menjadi bagian dari ekspresi.

## <a name="filter-results"></a>Memfilter hasil

Cmdlet `Where-Object` memungkinkan Anda memfilter hasil berdasarkan nilai properti apa pun, termasuk properti bersarang. Contoh berikutnya menunjukkan cara menggunakan `Where-Object` untuk menemukan VM Linux dalam grup sumber daya.

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

Anda dapat pipa hasil `Select-Object` dan `Where-Object` satu sama lain. Untuk tujuan kinerja, selalu disarankan untuk menempatkan `Where-Object` operasi sebelum `Select-Object`:

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
