---
title: Output cmdlet format Azure PowerShell
description: Cara memformat output cmdlet untuk Azure PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/07/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 6333546ec0d57b6dedab6e26721dfab459a0fe44
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425052"
---
# <a name="format-azurepowershell-cmdlet-output"></a>Output cmdlet Format AzurePowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Secara default, Azure PowerShell cmdlet telah memformat output yang sudah ditentukan sebelumnya sehingga mudah dibaca.  PowerShell juga menyediakan fleksibilitas untuk menyesuaikan output atau mengonversi output cmdlet ke format lain dengan cmdlet berikut:

| Pemformatan      | Konversi       |
|-----------------|------------------|
| [Format-Kustom](/powershell/module/microsoft.powershell.utility/format-custom) | [ConvertTo-csv](/powershell/module/microsoft.powershell.utility/convertto-csv)  |
| [Format-List](/powershell/module/microsoft.powershell.utility/format-list)   | [ConvertTo-Html](/powershell/module/microsoft.powershell.utility/convertto-html) |
| [Format-Tabel](/powershell/module/microsoft.powershell.utility/format-table)  | [ConvertTo-Json](/powershell/module/microsoft.powershell.utility/convertto-json) |
| [Format-Wide](/powershell/module/microsoft.powershell.utility/format-wide)   | [ConvertTo-Xml](/powershell/module/microsoft.powershell.utility/convertto-xml)  |

## <a name="format-examples"></a>Contoh format

Dalam contoh ini, kami mendapatkan daftar VM Azure dalam langganan default.  Perintah `Get-AzureRmVM` default output ke dalam format tabel.

```azurepowershell-interactive
Get-AzureRmVM
```

```output
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

Jika ingin membatasi kolom yang dikembalikan, Anda dapat menggunakan `Format-Table` cmdlet. Dalam contoh berikut, kami mendapatkan daftar mesin virtual yang sama tetapi membatasi output hanya dengan nama VM, grup sumber daya, dan lokasi VM.  Parameter `-Autosize` akan mengubah ukuran kolom sesuai dengan ukuran data.

```azurepowershell-interactive
Get-AzureRmVM | Format-Table Name,ResourceGroupName,Location -AutoSize
```

```output
Name          ResourceGroupName Location
----          ----------------- --------
MyUnbuntu1610 MYWESTEURG        westeurope
MyWin2016VM   MYWESTEURG        westeurope
```

Output juga bisa diformat ke dalam daftar. Contoh berikut memperlihatkan hal ini menggunakan `Format-List` cmdlet.

```azurepowershell-interactive
Get-AzureRmVM | Format-List Name,VmId,Location,ResourceGroupName
```

```output
Name              : MyUnbuntu1610
VmId              : 33422f9b-e339-4704-bad8-dbe094585496
Location          : westeurope
ResourceGroupName : MYWESTEURG

Name              : MyWin2016VM
VmId              : 4650c755-fc2b-4fc7-a5bc-298d5c00808f
Location          : westeurope
ResourceGroupName : MYWESTEURG
```

## <a name="convert-to-other-data-types"></a>Mengonversi ke tipe data lainnya

PowerShell juga memungkinkan mengambil output perintah dan mengonversinya menjadi beberapa format data. Dalam contoh berikut, cmdlet digunakan untuk mendapatkan atribut mesin virtual di langganan kami dan mengonversi output ke format CSV untuk mengimpor ke database atau lembar `Select-Object` bentang dengan mudah.

```azurepowershell-interactive
Get-AzureRmVM | Select-Object ResourceGroupName,Id,VmId,Name,Location,ProvisioningState | ConvertTo-Csv -NoTypeInformation
```

```output
"ResourceGroupName","Id","VmId","Name","Location","ProvisioningState"
"MYWESTUERG","/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTUERG/providers/Microsoft.Compute/virtualMachines/MyUnbuntu1610","33422f9b-e339-4704-bad8-dbe094585496","MyUnbuntu1610","westeurope","Succeeded"
"MYWESTUERG","/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTUERG/providers/Microsoft.Compute/virtualMachines/MyWin2016VM","4650c755-fc2b-4fc7-a5bc-298d5c00808f","MyWin2016VM","westeurope","Succeeded"
```

Output juga bisa dikonversi menjadi format JSON.  Contoh berikut membuat daftar VM yang sama namun mengubah format output menjadi JSON.

```azurepowershell-interactive
Get-AzureRmVM | Select-Object ResourceGroupName,Id,VmId,Name,Location,ProvisioningState | ConvertTo-Json
```

```output
[
    {
        "ResourceGroupName":  "MYWESTEURG",
        "Id":  "/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTEURG/providers/Microsoft.Compute/virtualMachines/MyUnbuntu1610",
        "VmId":  "33422f9b-e339-4704-bad8-dbe094585496",
        "Name":  "MyUnbuntu1610",
        "Location":  "westeurope",
        "ProvisioningState":  "Succeeded"
    },
    {
        "ResourceGroupName":  "MYWESTEURG",
        "Id":  "/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTEURG/providers/Microsoft.Compute/virtualMachines/MyWin2016VM",
        "VmId":  "4650c755-fc2b-4fc7-a5bc-298d5c00808f",
        "Name":  "MyWin2016VM",
        "Location":  "westeurope",
        "ProvisioningState":  "Succeeded"
    }
]
```
