---
title: Output kueri cmdlet Azure PowerShell kueri
description: Cara membuat kueri untuk sumber daya di Azure dan memformat hasilnya.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 8878a4caa36efa5bf336e3cd972ad915ade359d7
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429353"
---
# <a name="query-output-of-azure-powershell-cmdlets"></a>Output kueri cmdlet Azure PowerShell kueri

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Membuat kueri di PowerShell dapat diselesaikan dengan cmdlet bawaan. Di PowerShell, nama cmdlet berbentuk **_Kata Kerja-Kata Benda._** Cmdlet yang menggunakan kata **_kerja Get_** adalah cmdlet kueri. Kata benda cmdlet adalah tipe sumber daya Azure yang bertindak berdasarkan kata kerja cmdlet.

## <a name="select-simple-properties"></a>Pilih properti sederhana

Azure PowerShell memiliki pemformatan default yang ditentukan untuk setiap cmdlet. Properti paling umum untuk setiap tipe sumber daya ditampilkan dalam format tabel atau daftar secara otomatis. Untuk informasi selengkapnya tentang output pemformatan, lihat [Pemformatan hasil kueri.](formatting-output.md)

Gunakan `Get-AzureRmVM` cmdlet untuk membuat kueri untuk daftar VM di akun Anda.

```azurepowershell
Get-AzureRmVM
```

Output default secara otomatis diformat sebagai tabel.

```Output
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

Cmdlet `Select-Object` dapat digunakan untuk memilih properti spesifik yang menarik bagi Anda.

```azurepowershell
Get-AzureRmVM |
  Select -Property Name, ResourceGroupName, Location
```

```Output
Name          ResourceGroupName Location
----          ----------------- --------
MyUnbuntu1610 MYWESTEURG        westeurope
MyWin2016VM   MYWESTEURG        westeurope
```

## <a name="select-complex-nested-properties"></a>Pilih properti bertum tersedia yang kompleks

Jika properti yang diinginkan ditumpuk dalam output JSON, Anda harus menyediakan jalur lengkap ke properti. Contoh berikut ini memperlihatkan cara memilih Nama VM dan tipe OS dari `Get-AzureRmVM` cmdlet.

```azurepowershell
Get-AzureRmVM |
  Select -Property Name, @{Name='OSType'; Expression={$_.StorageProfile.OSDisk.OSType}}
```

```Output
Name           OSType
----           ------
MyUnbuntu1610   Linux
MyWin2016VM   Windows
```

## <a name="filter-results-with-the-where-object-cmdlet"></a>Memfilter hasil dengan Where-Object cmdlet

Cmdlet `Where-Object` memungkinkan Anda memfilter hasil berdasarkan nilai properti apa pun. Dalam contoh berikut, filter hanya memilih VM yang memiliki teks "RGD" dalam namanya.

```azurepowershell
Get-AzureRmVM |
  Where-Object ResourceGroupName -like RGD* |
    Select-Object -Property ResourceGroupName, Name
```

```Output
ResourceGroupName  Name
-----------------  ----
RGDEMO001          KBDemo001VM
RGDEMO001          KBDemo020
```

Dengan contoh berikutnya, hasil akan mengembalikan VM yang memiliki 'vmSize 'Standard_DS1_V2'.

```azurepowershell
Get-AzureRmVM |
  Where-Object vmSize -eq Standard_DS1_V2
```

```Output
ResourceGroupName          Name     Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----     --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610   westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM   westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```
