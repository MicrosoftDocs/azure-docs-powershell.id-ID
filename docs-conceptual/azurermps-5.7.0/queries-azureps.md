---
title: Output kueri cmdlet Azure PowerShell kueri
description: Cara membuat kueri untuk sumber daya di Azure dan memformat hasilnya.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/08/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 664829721843020745cf24a913e1d09a4e68a3da
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422887"
---
# <a name="query-output-of-azure-powershell-cmdlets"></a>Output kueri cmdlet Azure PowerShell kueri

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Membuat kueri di PowerShell dapat diselesaikan dengan cmdlet bawaan. Di PowerShell, nama cmdlet berbentuk **_Kata Kerja-Kata Benda._** Cmdlet yang menggunakan kata **_kerja Get_** adalah cmdlet kueri. Kata benda cmdlet adalah tipe sumber daya Azure yang bertindak berdasarkan kata kerja cmdlet.

## <a name="select-simple-properties"></a>Pilih properti sederhana

Azure PowerShell memiliki pemformatan default yang ditentukan untuk setiap cmdlet. Properti paling umum untuk setiap tipe sumber daya ditampilkan dalam format tabel atau daftar secara otomatis. Untuk informasi selengkapnya tentang output pemformatan, lihat [Pemformatan hasil kueri.](formatting-output.md)

Gunakan `Get-AzureRmVM` cmdlet untuk membuat kueri untuk daftar VM di akun Anda.

```azurepowershell-interactive
Get-AzureRmVM
```

Output default secara otomatis diformat sebagai tabel.

```output
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

Cmdlet `Select-Object` dapat digunakan untuk memilih properti spesifik yang menarik bagi Anda.

```azurepowershell-interactive
Get-AzureRmVM | Select Name,ResourceGroupName,Location
```

```output
Name          ResourceGroupName Location
----          ----------------- --------
MyUnbuntu1610 MYWESTEURG        westeurope
MyWin2016VM   MYWESTEURG        westeurope
```

## <a name="select-complex-nested-properties"></a>Pilih properti bertum tersedia yang kompleks

Jika properti yang ingin dipilih merupakan kedalaman bertumpuk dalam output JSON, Anda harus menyediakan jalur lengkap ke properti bertumpuk tersebut. Contoh berikut ini memperlihatkan cara memilih Nama VM dan tipe OS dari `Get-AzureRmVM` cmdlet.

```azurepowershell-interactive
Get-AzureRmVM | Select Name,@{Name='OSType'; Expression={$_.StorageProfile.OSDisk.OSType}}
```

```output
Name           OSType
----           ------
MyUnbuntu1610   Linux
MyWin2016VM   Windows
```

## <a name="filter-results-with-the-where-object-cmdlet"></a>Memfilter hasil dengan Where-Object cmdlet

Cmdlet `Where-Object` memungkinkan Anda memfilter hasil berdasarkan nilai properti apa pun. Dalam contoh berikut, filter hanya memilih VM yang memiliki teks "RGD" dalam namanya.

```azurepowershell-interactive
Get-AzureRmVM | Where ResourceGroupName -like RGD* | Select ResourceGroupName,Name
```

```output
ResourceGroupName  Name
-----------------  ----
RGDEMO001          KBDemo001VM
RGDEMO001          KBDemo020
```

Dengan contoh berikutnya, hasil akan mengembalikan VM yang memiliki 'vmSize 'Standard_DS1_V2'.

```azurepowershell-interactive
Get-AzureRmVM | Where vmSize -eq Standard_DS1_V2
```

```output
ResourceGroupName          Name     Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----     --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610   westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM   westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```
