---
title: Memformat hasil kueri | Microsoft Docs
description: Cara mengkueri sumber daya di Azure dan memformat hasilnya.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/30/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 54895da77a0073f34c1fae9565eb93092de9cfd1
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428304"
---
# <a name="formatting-query-results"></a>Memformat hasil kueri

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Secara default setiap cmdlet PowerShell memiliki pemformatan output yang telah ditentukan yang memudahkannya untuk dibaca.  PowerShell juga memberikan fleksibilitas untuk menyesuaikan output atau mengonversi output cmdlet ke format yang berbeda dengan cmdlet berikut:

| Pemformatan      | Konversi       |
|-----------------|------------------|
| `Format-Custom` | `ConvertTo-Csv`  |
| `Format-List`   | `ConvertTo-Html` |
| `Format-Table`  | `ConvertTo-Json` |
| `Format-Wide`   | `ConvertTo-Xml`  |

## <a name="formatting-examples"></a>Contoh pemformatan

Dalam contoh ini kami mendapatkan daftar Azure VM di langganan default kami.  Default perintah Get-AzureRmVM menghasilkan ke dalam format tabel.

```powershell-interactive
Get-AzureRmVM
```

```output
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

Jika Anda ingin membatasi kolom yang dikembalikan, Anda dapat menggunakan cmdlet `Format-Table`. Dalam contoh berikut kami mendapatkan daftar mesin virtual yang sama tetapi membatasi output ke hanya nama VM, grup sumber daya, dan lokasi VM.  Parameter `-Autosize` mengukur kolom sesuai dengan ukuran data.

```powershell-interactive
Get-AzureRmVM | Format-Table Name,ResourceGroupName,Location -AutoSize
```

```output
Name          ResourceGroupName Location
----          ----------------- --------
MyUnbuntu1610 MYWESTEURG        westeurope
MyWin2016VM   MYWESTEURG        westeurope
```

Jika diinginkan, Anda dapat menampilkan informasi dalam format dapat. Contoh berikut menunjukkan hal ini menggunakan cmdlet `Format-List`.

```powershell-interactive
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

## <a name="converting-to-other-data-types"></a>Mengonversi ke jenis data lain

PowerShell juga menawarkan beberapa format output yang dapat Anda gunakan untuk memenuhi kebutuhan Anda.  Dalam contoh berikut kami menggunakan cmdlet `Select-Object` untuk mendapatkan atribut mesin virtual di langganan kami dan mengonversi output ke format CSV untuk kemudahan impor ke database atau spreadsheet.

```powershell-interactive
Get-AzureRmVM | Select-Object ResourceGroupName,Id,VmId,Name,Location,ProvisioningState | ConvertTo-Csv -NoTypeInformation
```

```output
"ResourceGroupName","Id","VmId","Name","Location","ProvisioningState"
"MYWESTUERG","/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTUERG/providers/Microsoft.Compute/virtualMachines/MyUnbuntu1610","33422f9b-e339-4704-bad8-dbe094585496","MyUnbuntu1610","westeurope","Succeeded"
"MYWESTUERG","/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTUERG/providers/Microsoft.Compute/virtualMachines/MyWin2016VM","4650c755-fc2b-4fc7-a5bc-298d5c00808f","MyWin2016VM","westeurope","Succeeded"
```

Anda juga dapat mengonversi output menjadi format JSON.  Contoh berikut membuat daftar VM yang sama tetapi mengubah format output menjadi JSON.

```powershell-interactive
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
