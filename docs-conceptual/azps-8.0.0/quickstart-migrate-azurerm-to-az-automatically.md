---
author: mikefrobbins
description: Pelajari cara memigrasikan skrip PowerShell secara otomatis dari AzureRM ke modul Az PowerShell.
ms.author: mirobb
ms.custom: devx-track-azurepowershell, mode-api
ms.date: 06/09/2022
ms.service: azure-powershell
ms.topic: quickstart
title: Secara otomatis memigrasikan skrip PowerShell dari AzureRM ke modul Az PowerShell
ms.openlocfilehash: d5a6bff8ec8304ccefe3d5332fad60a26284f374
ms.sourcegitcommit: 37440f9593703a5e400f8052b026691982899953
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/11/2022
ms.locfileid: "146259659"
---
# <a name="quickstart-automatically-migrate-powershell-scripts-from-azurerm-to-the-az-powershell-module"></a>Mulai cepat: Secara otomatis memigrasikan skrip PowerShell dari AzureRM ke modul Az PowerShell

Pada artikel ini, Anda akan mempelajari cara menggunakan modul Az.Tools.Migration PowerShell untuk secara otomatis meningkatkan skrip PowerShell dan modul skrip Anda dari AzureRM ke modul Az PowerShell. Untuk opsi migrasi tambahan, lihat [Memigrasikan Azure PowerShell dari AzureRM ke Az](/powershell/azure/migrate-from-azurerm-to-az).

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## <a name="requirements"></a>Persyaratan

- Perbarui skrip PowerShell Anda yang ada ke versi terbaru [modul AzureRM PowerShell (6.13.1)](https://www.powershellgallery.com/packages/AzureRM/).
- Instal modul Az.Tools.Migration PowerShell.

  ```powershell
  Install-Module -Name Az.Tools.Migration
  ```

## <a name="step-1-generate-an-upgrade-plan"></a>Langkah 1: Buat rencana peningkatan

Anda menggunakan cmdlet **`New-AzUpgradeModulePlan`** untuk membuat rencana peningkatan untuk memigrasikan skrip dan modul Anda ke modul Az PowerShell. Cmdlet ini tidak membuat perubahan apa pun pada skrip yang ada. Gunakan parameter **`FilePath`** untuk menargetkan skrip tertentu atau parameter **`DirectoryPath`** untuk menargetkan semua skrip dalam folder tertentu.

> [!NOTE]
> Cmdlet **`New-AzUpgradeModulePlan`** tidak menjalankan rencana, hanya menghasilkan langkah-langkah peningkatan.

Contoh berikut menghasilkan rencana untuk semua skrip di folder _`C:\Scripts`_ . Parameter **`OutVariable`** ditentukan sehingga hasilnya dikembalikan dan disimpan secara bersamaan dalam variabel bernama **`Plan`** .

```powershell
# Generate an upgrade plan for all the scripts and module files in the specified folder and save it to a variable.
New-AzUpgradeModulePlan -FromAzureRmVersion 6.13.1 -ToAzVersion 5.2.0 -DirectoryPath 'C:\Scripts' -OutVariable Plan
```

Seperti yang ditunjukkan dalam output berikut, rencana peningkatan merinci file tertentu dan titik offset yang memerlukan perubahan saat berpindah dari AzureRM ke cmdlet Az PowerShell.

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

Sebelum melakukan peningkatan, Anda perlu melihat masalah pada hasil rencana. Contoh berikut mengembalikan daftar skrip dan item dalam skrip tersebut yang akan mencegahnya ditingkatkan secara otomatis.

```powershell
# Filter plan results to only warnings and errors
$Plan | Where-Object PlanResult -ne ReadyToUpgrade | Format-List
```

Item yang ditampilkan dalam output berikut tidak akan ditingkatkan secara otomatis tanpa mengoreksi masalah secara manual terlebih dahulu.

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

## <a name="step-2-perform-the-upgrade"></a>Langkah 2: Lakukan peningkatan

> [!CAUTION]
> Tidak ada operasi undo (pembatalan). Selalu pastikan bahwa Anda memiliki salinan cadangan skrip dan modul PowerShell yang ingin Anda tingkatkan.

Setelah Anda puas dengan rencananya, peningkatan dilakukan dengan cmdlet **`Invoke-AzUpgradeModulePlan`** . Tentukan **`SaveChangesToNewFiles`** untuk nilai parameter **`FileEditMode`** untuk mencegah perubahan dilakukan pada skrip asli Anda. Saat menggunakan mode ini, peningkatan dilakukan dengan membuat salinan setiap skrip yang ditargetkan dengan _`_az_upgraded`_ yang disertakan pada nama file.

> [!WARNING]
> Cmdlet **`Invoke-AzUpgradeModulePlan`** bersifat destruktif ketika opsi **`-FileEditMode ModifyExistingFiles`** ditentukan! Ini memodifikasi skrip dan fungsi Anda di tempatnya sesuai dengan rencana peningkatan modul yang dihasilkan oleh cmdlet **`New-AzUpgradeModulePlan`** . Untuk opsi non-destruktif tentukan **`-FileEditMode SaveChangesToNewFiles`** sebagai gantinya.

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

Jika ada kesalahan yang dikembalikan, Anda dapat melihat lebih dekat hasil kesalahan dengan perintah berikut:

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

- Operasi I/O file menggunakan pengkodean default. Situasi pengkodean file yang tidak biasa dapat menyebabkan masalah.
- Cmdlet AzureRM yang diteruskan sebagai argumen ke pernyataan tiruan uji unit Pester tidak terdeteksi.
- Saat ini, hanya modul Az PowerShell versi 5.2.0 yang didukung sebagai target.

## <a name="how-to-report-issues"></a>Cara melaporkan masalah

Laporkan umpan balik dan masalah tentang modul Az.Tools.Migration PowerShell melalui [masalah GitHub](https://github.com/Azure/azure-powershell-migration/issues) di repositori `azure-powershell-migration`.

## <a name="next-steps"></a>Langkah berikutnya

Untuk informasi selengkapnya tentang modul Azure PowerShell, lihat [dokumentasi Azure PowerShell](/powershell/azure/)
