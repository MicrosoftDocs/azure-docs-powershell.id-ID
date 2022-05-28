---
Module Name: Az.Quota
Module Guid: bd26548c-ac2c-4447-9d5d-2e4d8c622495
Download Help Link: https://docs.microsoft.com/powershell/module/az.quota
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Az.Quota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Az.Quota.md
ms.openlocfilehash: bb434c565c90bfdec30615373f4e6e59edf8105e
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145519426"
---
# Modul Az.Quota
## Deskripsi
Microsoft Azure PowerShell: Cmdlet kuota

## Cmdlet Az.Quota
### [Get-AzQuota](Get-AzQuota.md)
Dapatkan batas kuota sumber daya.
Respons dapat digunakan untuk menentukan sisa kuota untuk menghitung batas kuota baru yang dapat dikirimkan dengan permintaan PUT.

### [Get-AzQuotaOperation](Get-AzQuotaOperation.md)
Cantumkan semua operasi yang didukung oleh penyedia sumber daya Microsoft.Quota.

### [Get-AzQuotaRequestStatus](Get-AzQuotaRequestStatus.md)
Dapatkan detail permintaan kuota dan status berdasarkan ID permintaan kuota untuk sumber daya penyedia sumber daya di lokasi tertentu.
**ID** permintaan kuota dikembalikan sebagai respons operasi PUT.

### [Get-AzQuotaUsage](Get-AzQuotaUsage.md)
Dapatkan penggunaan sumber daya saat ini.

### [New-AzQuota](New-AzQuota.md)
Buat atau perbarui batas kuota untuk sumber daya yang ditentukan dengan nilai yang diminta.
Untuk memperbarui kuota, ikuti langkah-langkah berikut:\n1.
Gunakan operasi GET untuk kuota dan penggunaan untuk menentukan berapa banyak kuota yang tersisa untuk sumber daya tertentu dan untuk menghitung batas kuota baru.
Langkah-langkah ini dirinci dalam example.\n2 [ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status detail permintaan.

### [New-AzQuotaLimitObject](New-AzQuotaLimitObject.md)
Buat objek dalam memori untuk LimitObject.

### [Update-AzQuota](Update-AzQuota.md)
Perbarui batas kuota untuk sumber daya tertentu ke nilai yang ditentukan:\n1.
Gunakan operasi Usages-GET dan Quota-GET untuk menentukan kuota yang tersisa untuk sumber daya tertentu dan untuk menghitung batas kuota baru.
Langkah-langkah ini dirinci dalam example.\n2 [ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status detail permintaan.

