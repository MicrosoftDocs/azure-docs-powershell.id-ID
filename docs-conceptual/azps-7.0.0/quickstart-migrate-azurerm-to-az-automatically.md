---
title: Melakukan migrasi skrip PowerShell secara otomatis dari AzureRM ke modul Az PowerShell
description: Pelajari cara melakukan migrasi skrip PowerShell secara otomatis dari AzureRM ke modul Az PowerShell.
author: mikefrobbins
ms.service: azure-powershell
ms.topic: quickstart
ms.custom: devx-track-azurepowershell, mode-api
ms.author: mirobb
ms.date: 11/02/2021
ms.openlocfilehash: 4dc9d86386af2838a2e55690ecd41a334fcf6c03
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "134026039"
---
# <a name="quickstart-automatically-migrate-powershell-scripts-from-azurerm-to-the-az-powershell-module"></a>Mulai cepat: Melakukan migrasi skrip PowerShell secara otomatis dari AzureRM ke modul Az PowerShell

Di artikel ini, Anda akan mempelajari cara menggunakan modul Az.Tools.Migration PowerShell untuk memutakhirkan skrip Dan modul skrip PowerShell Anda secara otomatis dari AzureRM ke modul Az PowerShell. Untuk opsi migrasi tambahan, lihat [Melakukan Azure PowerShell dari AzureRM ke Az](/powershell/azure/migrate-from-azurerm-to-az).

## <a name="requirements"></a>Persyaratan

* Memperbarui skrip PowerShell yang sudah ada ke versi terbaru modul [PowerShell AzureRM (6.13.1).](https://github.com/Azure/azure-powershell/releases/tag/v6.13.1-November2018)
* Instal modul PowerShell Az.Tools.Migration.

  ```powershell
  Install-Module -Name Az.Tools.Migration
  ```

## <a name="step-1-generate-an-upgrade-plan"></a>Langkah 1: Buat paket pemutakhiran

You use the **`New-AzUpgradeModulePlan`** cmdlet to generate an upgrade plan for migrating your scripts and modules to the Az PowerShell module. Cmdlet ini tidak membuat perubahan apa pun pada skrip Anda yang sudah ada. Gunakan **`FilePath`** parameter untuk menargetkan skrip atau parameter tertentu **`DirectoryPath`** untuk menargetkan semua skrip dalam folder tertentu.

> [!NOTE]
> Cmdlet **`New-AzUpgradeModulePlan`** tidak menjalankan rencana, cmdlet hanya menghasilkan langkah-langkah pemutakhiran.

Contoh berikut menghasilkan rencana untuk semua skrip dalam _`C:\Scripts`_ folder. Parameter **`OutVariable`** ditentukan sehingga hasil dikembalikan dan disimpan secara bersamaan dalam variabel bernama **`Plan`** .

```powershell
# Generate an upgrade plan for all the scripts and module files in the specified folder and save it to a variable.
New-AzUpgradeModulePlan -FromAzureRmVersion 6.13.1 -ToAzVersion 5.2.0 -DirectoryPath 'C:\Scripts' -OutVariable Plan
```

Seperti yang diperlihatkan dalam output berikut, rencana pemutakhiran merinci titik file dan offset tertentu yang memerlukan perubahan saat berpindah dari AzureRM ke cmdlet Az PowerShell.

```Output
Order Location                                                   UpgradeType     PlanResult             Original
----- --------                                                   -----------     ----------             --------
1     compute-create-dockerhost.ps1:59:24                        CmdletParameter ReadyToUpgrade         ExtensionName
2     compute-create-dockerhost.ps1:59:1                         Cmdlet          ReadyToUpgrade         Set-AzureRmVM...
3     compute-create-dockerhost.ps1:54:1                         Cmdlet          ReadyToUpgrade         New-AzureRmVM
4     compute-create-dockerhost.ps1:51:1                         Cmdlet          ReadyToUpgrade         Add-AzureRmVM...
5     compute-create-dockerhost.ps1:47:1                         Cmdlet          ReadyToUpgrade         Add-AzureRmVM...
6     compute-create-dockerhost.ps1:46:1                         Cmdlet          ReadyToUpgrade         Set-AzureRmVM...
7     compute-create-dockerhost.ps1:45:1                         Cmdlet          ReadyToUpgrade         Set-AzureRmVM...
8     compute-create-dockerhost.ps1:44:13                        Cmdlet          ReadyToUpgrade         New-AzureRmVM...
9     compute-create-dockerhost.ps1:40:8                         Cmdlet          ReadyToUpgrade         New-AzureRmNe...
10    compute-create-dockerhost.ps1:36:8                         Cmdlet          ReadyToUpgrade         New-AzureRmNe...
11    compute-create-dockerhost.ps1:31:16                        Cmdlet          ReadyToUpgrade         New-AzureRmNe...
12    compute-create-dockerhost.ps1:26:15                        Cmdlet          ReadyToUpgrade         New-AzureRmNe...
13    compute-create-dockerhost.ps1:22:8                         Cmdlet          ReadyToUpgrade         New-AzureRmPu...
14    compute-create-dockerhost.ps1:18:9                         Cmdlet          ReadyToUpgrade         New-AzureRmVi...
15    compute-create-dockerhost.ps1:15:17                        Cmdlet          ReadyToUpgrade         New-AzureRmVi...
16    compute-create-dockerhost.ps1:12:1                         Cmdlet          ReadyToUpgrade         New-AzureRmRe...
17    compute-create-windowsvm-quick.ps1:18:3                    CmdletParameter ReadyToUpgrade         ImageName
18    compute-create-windowsvm-quick.ps1:14:1                    Cmdlet          ReadyToUpgrade         New-AzureRmVM
19    compute-create-windowsvm-quick.ps1:11:1                    Cmdlet          ReadyToUpgrade         New-AzureRmRe...
20    compute-create-wordpress-mysql.ps1:59:24                   CmdletParameter ReadyToUpgrade         ExtensionName
...
```

Sebelum melakukan pemutakhiran, Anda perlu melihat hasil rencana untuk masalah. Contoh berikut mengembalikan daftar skrip dan item dalam skrip tersebut yang akan mencegahnya di upgrade secara otomatis.

```powershell
# Filter plan results to only warnings and errors
$Plan | Where-Object PlanResult -ne ReadyToUpgrade | Format-List
```

Item yang diperlihatkan dalam output berikut ini tidak akan dimutakhirkan secara otomatis tanpa mengoreksi masalah secara manual terlebih dahulu.

```Output
Order                  : 42
UpgradeType            : CmdletParameter
PlanResult             : ErrorParameterNotFound
PlanSeverity           : Error
PlanResultReason       : Parameter was not found in Get-AzResource or it's aliases.
SourceCommand          : CommandReference
SourceCommandParameter : CommandReferenceParameter
Location               : devtestlab-add-marketplace-image-to-lab.ps1:14:74
FullPath               : C:\Scripts\devtestlab-add-marketplace-image-to-lab.ps1
StartOffset            : 556
Original               : ResourceNameEquals
Replacement            :
```

## <a name="step-2-perform-the-upgrade"></a>Langkah 2: Jalankan pemutakhiran

> [!CAUTION]
> Tidak ada operasi untuk membatalkan. Selalu pastikan bahwa Anda memiliki salinan cadangan skrip dan modul PowerShell yang sedang anda coba mutakhirkan.

Setelah puas dengan rencana tersebut, pemutakhiran dijalankan dengan **`Invoke-AzUpgradeModulePlan`** cmdlet. Tentukan **`SaveChangesToNewFiles`** nilai parameter untuk mencegah perubahan dibuat ke skrip asli **`FileEditMode`** Anda. Saat menggunakan mode ini, pemutakhiran dilakukan dengan membuat salinan setiap skrip yang ditargetkan _`_az_upgraded`_ dengan ditambahkan ke nama file.

> [!WARNING]
> Cmdlet **`Invoke-AzUpgradeModulePlan`** merusak saat **`-FileEditMode ModifyExistingFiles`** opsi ditentukan! Skrip akan memodifikasi skrip dan fungsi di tempat sesuai dengan rencana pemutakhiran modul yang dihasilkan oleh **`New-AzUpgradeModulePlan`** cmdlet. Untuk opsi non-perusak tentukan sebagai **`-FileEditMode SaveChangesToNewFiles`** gantinya.

```powershell
# Execute the automatic upgrade plan and save the results to a variable.
Invoke-AzUpgradeModulePlan -Plan $Plan -FileEditMode SaveChangesToNewFiles -OutVariable Results
```

```Output
Order Location                                                   UpgradeType     UpgradeResult    Original
----- --------                                                   -----------     -------------    --------
1     compute-create-dockerhost.ps1:59:24                        CmdletParameter UpgradeCompleted ExtensionName
2     compute-create-dockerhost.ps1:59:1                         Cmdlet          UpgradeCompleted Set-AzureRmVMExtens...
3     compute-create-dockerhost.ps1:54:1                         Cmdlet          UpgradeCompleted New-AzureRmVM
4     compute-create-dockerhost.ps1:51:1                         Cmdlet          UpgradeCompleted Add-AzureRmVMSshPub...
5     compute-create-dockerhost.ps1:47:1                         Cmdlet          UpgradeCompleted Add-AzureRmVMNetwor...
6     compute-create-dockerhost.ps1:46:1                         Cmdlet          UpgradeCompleted Set-AzureRmVMSource...
7     compute-create-dockerhost.ps1:45:1                         Cmdlet          UpgradeCompleted Set-AzureRmVMOperat...
8     compute-create-dockerhost.ps1:44:13                        Cmdlet          UpgradeCompleted New-AzureRmVMConfig
9     compute-create-dockerhost.ps1:40:8                         Cmdlet          UpgradeCompleted New-AzureRmNetworkI...
10    compute-create-dockerhost.ps1:36:8                         Cmdlet          UpgradeCompleted New-AzureRmNetworkS...
11    compute-create-dockerhost.ps1:31:16                        Cmdlet          UpgradeCompleted New-AzureRmNetworkS...
12    compute-create-dockerhost.ps1:26:15                        Cmdlet          UpgradeCompleted New-AzureRmNetworkS...
13    compute-create-dockerhost.ps1:22:8                         Cmdlet          UpgradeCompleted New-AzureRmPublicIp...
14    compute-create-dockerhost.ps1:18:9                         Cmdlet          UpgradeCompleted New-AzureRmVirtualN...
15    compute-create-dockerhost.ps1:15:17                        Cmdlet          UpgradeCompleted New-AzureRmVirtualN...
16    compute-create-dockerhost.ps1:12:1                         Cmdlet          UpgradeCompleted New-AzureRmResource...
17    compute-create-windowsvm-quick.ps1:18:3                    CmdletParameter UpgradeCompleted ImageName
18    compute-create-windowsvm-quick.ps1:14:1                    Cmdlet          UpgradeCompleted New-AzureRmVM
19    compute-create-windowsvm-quick.ps1:11:1                    Cmdlet          UpgradeCompleted New-AzureRmResource...
20    compute-create-wordpress-mysql.ps1:59:24                   CmdletParameter UpgradeCompleted ExtensionName
...
```

Jika kesalahan apa pun dikembalikan, Anda bisa melihat lebih dekat hasil kesalahan dengan perintah berikut ini:

```powershell
# Filter results to show only errors
$Results | Where-Object UpgradeResult -ne UpgradeCompleted | Format-List
```

```Output
Order                  : 42
UpgradeType            : CmdletParameter
UpgradeResult          : UnableToUpgrade
UpgradeSeverity        : Error
UpgradeResultReason    : Parameter was not found in Get-AzResource or it's aliases.
SourceCommand          : CommandReference
SourceCommandParameter : CommandReferenceParameter
Location               : devtestlab-add-marketplace-image-to-lab.ps1:14:74
FullPath               : C:\Scripts\devtestlab-add-marketplace-image-to-lab.ps1
StartOffset            : 556
Original               : ResourceNameEquals
Replacement            :
```

## <a name="limitations"></a>Batasan

* Operasi I/O File menggunakan pengodean default. Situasi pengodean file yang tidak biasa dapat menyebabkan masalah.
* Cmdlet AzureRM yang disampaikan sebagai argumen untuk pernyataan tes tes unit AzureRM tidak dideteksi.
* Saat ini, hanya modul Az PowerShell versi 5.2.0 yang didukung sebagai target.

## <a name="how-to-report-issues"></a>Cara melaporkan masalah

Laporkan umpan balik dan masalah tentang modul PowerShell Az.Tools.Migration [melalui GitHub di](https://github.com/Azure/azure-powershell-migration/issues) `azure-powershell-migration` repositori.

## <a name="next-steps"></a>Langkah berikutnya

Untuk mempelajari selengkapnya tentang modul PowerShell Az, lihat [Azure PowerShell teknis](/powershell/azure/)
