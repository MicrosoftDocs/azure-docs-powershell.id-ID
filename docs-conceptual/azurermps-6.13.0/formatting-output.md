---
title: Output cmdlet format Azure PowerShell
description: Cara memformat output cmdlet untuk Azure PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 4ba2cf544385c205990278bd075d479710d9ce92
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429362"
---
# <a name="format-azurepowershell-cmdlet-output"></a>Output cmdlet Format AzurePowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Secara default, Azure PowerShell cmdlet telah memformat output yang sudah ditentukan sebelumnya sehingga mudah dibaca.
PowerShell juga menyediakan fleksibilitas untuk menyesuaikan output atau mengonversi output cmdlet ke format lain dengan cmdlet berikut:

|                                   Pemformatan                                   |                                    Konversi                                    |
| ------------------------------------------------------------------------------ | -------------------------------------------------------------------------------- |
| [Format-Kustom](/powershell/module/microsoft.powershell.utility/format-custom) | [ConvertTo-csv](/powershell/module/microsoft.powershell.utility/convertto-csv)   |
| [Format-List](/powershell/module/microsoft.powershell.utility/format-list)     | [ConvertTo-Html](/powershell/module/microsoft.powershell.utility/convertto-html) |
| [Format-Tabel](/powershell/module/microsoft.powershell.utility/format-table)   | [ConvertTo-Json](/powershell/module/microsoft.powershell.utility/convertto-json) |
| [Format-Wide](/powershell/module/microsoft.powershell.utility/format-wide)     | [ConvertTo-Xml](/powershell/module/microsoft.powershell.utility/convertto-xml)   |

## <a name="format-examples"></a>Contoh format

Dalam contoh ini, kami mendapatkan daftar VM Azure dalam langganan default. Perintah `Get-AzureRmVM` default output ke dalam format tabel.

```azurepowershell
Get-AzureRmVM
```

```output
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

Jika ingin membatasi kolom yang dikembalikan, Anda dapat menggunakan `Format-Table` cmdlet. Dalam contoh berikut, kami mendapatkan daftar mesin virtual yang sama tetapi membatasi output hanya dengan nama VM, grup sumber daya, dan lokasi VM. Parameter `-Autosize` akan mengubah ukuran kolom sesuai dengan ukuran data.

```azurepowershell
Get-AzureRmVM |
  Format-Table -Property Name, ResourceGroupName, Location -AutoSize
```

```Output
Name          ResourceGroupName Location
----          ----------------- --------
MyUnbuntu1610 MYWESTEURG        westeurope
MyWin2016VM   MYWESTEURG        westeurope
```

Output juga bisa diformat ke dalam daftar. Contoh berikut memperlihatkan hal ini menggunakan `Format-List` cmdlet.

```azurepowershell
Get-AzureRmVM |
  Format-List -Property Name, VmId, Location, ResourceGroupName
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

PowerShell juga memungkinkan mengambil output perintah dan mengonversinya menjadi beberapa format data. Dalam contoh berikut, cmdlet digunakan untuk mendapatkan atribut mesin virtual di langganan kami dan mengonversi output ke format CSV untuk memudahkan impor ke `Select-Object` database atau lembar bentang.

```azurepowershell
Get-AzureRmVM |
  Select-Object -Property ResourceGroupName, Id, VmId, Name, Location, ProvisioningState |
  ConvertTo-Csv -NoTypeInformation
```

```Output
"ResourceGroupName","Id","VmId","Name","Location","ProvisioningState"
"MYWESTUERG","/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MYWESTUERG/providers/Microsoft.Compute/virtualMachines/MyUnbuntu1610","33422f9b-e339-4704-bad8-dbe094585496","MyUnbuntu1610","westeurope","Succeeded"
"MYWESTUERG","/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MYWESTUERG/providers/Microsoft.Compute/virtualMachines/MyWin2016VM","4650c755-fc2b-4fc7-a5bc-298d5c00808f","MyWin2016VM","westeurope","Succeeded"
```

Output juga bisa dikonversi menjadi format JSON. Contoh berikut membuat daftar VM yang sama namun mengubah format output menjadi JSON.

```azurepowershell
Get-AzureRmVM |
  Select-Object -Property ResourceGroupName, Id, VmId, Name, Location, ProvisioningState |
  ConvertTo-Json
```

```Output
[
    {
        "ResourceGroupName":  "MYWESTEURG",
        "Id":  "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MYWESTEURG/providers/Microsoft.Compute/virtualMachines/MyUnbuntu1610",
        "VmId":  "33422f9b-e339-4704-bad8-dbe094585496",
        "Name":  "MyUnbuntu1610",
        "Location":  "westeurope",
        "ProvisioningState":  "Succeeded"
    },
    {
        "ResourceGroupName":  "MYWESTEURG",
        "Id":  "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MYWESTEURG/providers/Microsoft.Compute/virtualMachines/MyWin2016VM",
        "VmId":  "4650c755-fc2b-4fc7-a5bc-298d5c00808f",
        "Name":  "MyWin2016VM",
        "Location":  "westeurope",
        "ProvisioningState":  "Succeeded"
    }
]
```
