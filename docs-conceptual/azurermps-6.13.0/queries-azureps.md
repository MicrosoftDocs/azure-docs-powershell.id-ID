---
title: Mengkueri output cmdlet Azure PowerShell
description: Cara mengkueri sumber daya di Azure dan memformat hasilnya.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 8878a4caa36efa5bf336e3cd972ad915ade359d7
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429353"
---
# <a name="query-output-of-azure-powershell-cmdlets"></a>Mengkueri output cmdlet Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Mengkueri di PowerShell dapat diselesaikan dengan menggunakan cmdlet bawaan. D PowerShell, nama cmdlet mengambil bentuk **_Kata kerja-Kata benda_**. Cmdlet menggunakan kata kerja **_Get_** adalah cmdlet kueri. Kata benda cmdlet adalah jenis sumber daya Azure yang ditindaklanjuti dengan kata kerja cmdlet.

## <a name="select-simple-properties"></a>Memilih properti sederhana

Azure PowerShell memiliki pemformatan default yang ditentukan untuk setiap cmdlet. Properti paling umum untuk setiap jenis sumber daya ditampilkan di tabel atau format daftar secara otomatis. Untuk informasi selengkapnya tentang output pemformatan, lihat [Hasil kueri pemformatan](formatting-output.md).

Gunakan cmdlet `Get-AzureRmVM` untuk mengkueri daftar VM di akun Anda.

```azurepowershell
Get-AzureRmVM
```

Output default diformat secara otomatis sebagai tabel.

```Output
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

Cmdlet `Select-Object` dapat digunakan untuk memilih properti tertentu yang Anda minati.

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

## <a name="select-complex-nested-properties"></a>Memilih properti berlapis kompleks

Jika properti yang Anda inginkan berlapis di output JSON, Anda harus menyediakan jalur lengkap ke properti. Contoh berikut menunjukkan cara memilih Nama VM dan jenisOS dari cmdlet `Get-AzureRmVM`.

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

## <a name="filter-results-with-the-where-object-cmdlet"></a>Hasil filter dengan cmdlet Where-Object

Cmdlet `Where-Object` memungkinkan Anda untuk memfilter hasil berdasarkan nilai properti. Dalam contoh berikut, filter hanya memilih VM yang memiliki teks "RGD" dalam namanya.

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

Dengan contoh berikutnya, hasil akan mengembalikan VM yang memiliki vmSize 'Standard_DS1_V2'.

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
