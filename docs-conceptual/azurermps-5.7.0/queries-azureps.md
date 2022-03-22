---
title: Mengkueri output cmdlet Azure PowerShell
description: Cara mengkueri sumber daya di Azure dan memformat hasilnya.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/08/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 664829721843020745cf24a913e1d09a4e68a3da
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422887"
---
# <a name="query-output-of-azure-powershell-cmdlets"></a>Mengkueri output cmdlet Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Mengkueri di PowerShell dapat diselesaikan dengan menggunakan cmdlet bawaan. D PowerShell, nama cmdlet mengambil bentuk **_Kata kerja-Kata benda_**. Cmdlet menggunakan kata kerja **_Get_** adalah cmdlet kueri. Kata benda cmdlet adalah jenis sumber daya Azure yang ditindaklanjuti dengan kata kerja cmdlet.

## <a name="select-simple-properties"></a>Memilih properti sederhana

Azure PowerShell memiliki pemformatan default yang ditentukan untuk setiap cmdlet. Properti paling umum untuk setiap jenis sumber daya ditampilkan di tabel atau format daftar secara otomatis. Untuk informasi selengkapnya tentang output pemformatan, lihat [Hasil kueri pemformatan](formatting-output.md).

Gunakan cmdlet `Get-AzureRmVM` untuk mengkueri daftar VM di akun Anda.

```azurepowershell-interactive
Get-AzureRmVM
```

Output default diformat secara otomatis sebagai tabel.

```output
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

Cmdlet `Select-Object` dapat digunakan untuk memilih properti tertentu yang Anda minati.

```azurepowershell-interactive
Get-AzureRmVM | Select Name,ResourceGroupName,Location
```

```output
Name          ResourceGroupName Location
----          ----------------- --------
MyUnbuntu1610 MYWESTEURG        westeurope
MyWin2016VM   MYWESTEURG        westeurope
```

## <a name="select-complex-nested-properties"></a>Memilih properti berlapis kompleks

Jika properti yang Anda ingin pilih berlapis jauh di dalam output JSON, Anda harus menyediakan jalur lengkap ke properti berlapis tersebut. Contoh berikut menunjukkan cara memilih Nama VM dan jenisOS dari cmdlet `Get-AzureRmVM`.

```azurepowershell-interactive
Get-AzureRmVM | Select Name,@{Name='OSType'; Expression={$_.StorageProfile.OSDisk.OSType}}
```

```output
Name           OSType
----           ------
MyUnbuntu1610   Linux
MyWin2016VM   Windows
```

## <a name="filter-results-with-the-where-object-cmdlet"></a>Hasil filter dengan cmdlet Where-Object

Cmdlet `Where-Object` memungkinkan Anda untuk memfilter hasil berdasarkan nilai properti. Dalam contoh berikut, filter hanya memilih VM yang memiliki teks "RGD" dalam namanya.

```azurepowershell-interactive
Get-AzureRmVM | Where ResourceGroupName -like RGD* | Select ResourceGroupName,Name
```

```output
ResourceGroupName  Name
-----------------  ----
RGDEMO001          KBDemo001VM
RGDEMO001          KBDemo020
```

Dengan contoh berikutnya, hasil akan mengembalikan VM yang memiliki vmSize 'Standard_DS1_V2'.

```azurepowershell-interactive
Get-AzureRmVM | Where vmSize -eq Standard_DS1_V2
```

```output
ResourceGroupName          Name     Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----     --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610   westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM   westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```
