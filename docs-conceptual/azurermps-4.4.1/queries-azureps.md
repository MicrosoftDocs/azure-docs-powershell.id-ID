---
title: Mengkueri untuk sumber daya Azure dan hasil pemformatan | Microsoft Docs
description: Cara mengkueri sumber daya di Azure dan memformat hasilnya.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/30/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 7c8bac8430c4e1f1ad2067a68aa7768f4683d6b7
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421092"
---
# <a name="querying-for-azure-resources"></a>Mengkueri untuk sumber daya Azure

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Mengkueri di PowerShell dapat diselesaikan dengan menggunakan cmdlet bawaan. Di PowerShell, nama cmdlet mengambil bentuk **_Kata kerja-Kata benda_**. Cmdlet menggunakan kata kerja **_Get_** adalah cmdlet kueri. Kata benda cmdlet adalah jenis sumber daya Azure yang ditindaklanjuti dengan kata kerja cmdlet.

## <a name="selecting-simple-properties"></a>Memilih properti sederhana

Azure PowerShell memiliki pemformatan default yang ditentukan untuk setiap cmdlet. Properti paling umum untuk setiap jenis sumber daya ditampilkan di tabel atau format daftar secara otomatis. Untuk informasi selengkapnya tentang output pemformatan, lihat [Hasil kueri pemformatan](formatting-output.md).

Gunakan cmdlet `Get-AzureRmVM` untuk mengkueri daftar VM di akun Anda.

```powershell-interactive
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

```powershell-interactive
Get-AzureRmVM | Select Name,ResourceGroupName,Location
```

```output
Name          ResourceGroupName Location
----          ----------------- --------
MyUnbuntu1610 MYWESTEURG        westeurope
MyWin2016VM   MYWESTEURG        westeurope
```

## <a name="selecting-complex-nested-properties"></a>Memilih properti berlapis kompleks

Jika properti yang Anda ingin pilih berlapis jauh di dalam output JSON, Anda harus menyediakan jalur lengkap ke properti berlapis tersebut. Contoh berikut menunjukkan cara memilih Nama VM dan jenis OS dari cmdlet `Get-AzureRmVM`.

```powershell-interactive
Get-AzureRmVM | Select Name,@{Name='OSType'; Expression={$_.StorageProfile.OSDisk.OSType}}
```

```output
Name           OSType
----           ------
MyUnbuntu1610   Linux
MyWin2016VM   Windows
```

## <a name="filter-result-using-the-where-object-cmdlet"></a>Hasil filter menggunakan cmdlet Where-Object

Cmdlet `Where-Object` memungkinkan Anda untuk memfilter hasil berdasarkan nilai properti. Dalam contoh berikut, filter hanya memilih VM yang memiliki teks "RGD" dalam namanya.

```powershell-interactive
Get-AzureRmVM | Where ResourceGroupName -like RGD* | Select ResourceGroupName,Name
```

```output
ResourceGroupName  Name
-----------------  ----
RGDEMO001          KBDemo001VM
RGDEMO001          KBDemo020
```

Dengan contoh berikutnya, hasil akan mengembalikan VM yang memiliki vmSize 'Standard_DS1_V2'.

```powershell-interactive
Get-AzureRmVM | Where vmSize -eq Standard_DS1_V2
```

```output
ResourceGroupName          Name     Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----     --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610   westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM   westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```
