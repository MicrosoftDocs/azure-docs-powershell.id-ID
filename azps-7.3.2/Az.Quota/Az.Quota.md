---
Module Name: Az.Quota
Module Guid: bd26548c-ac2c-4447-9d5d-2e4d8c622495
Download Help Link: https://docs.microsoft.com/powershell/module/az.quota
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Az.Quota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Az.Quota.md
ms.openlocfilehash: bb434c565c90bfdec30615373f4e6e59edf8105e
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140196439"
---
# Az.Quota Module
## Deskripsi
Microsoft Azure PowerShell: Cmdlet kuota

## Cmdlet Az.Quota
### [Get-AzQuota](Get-AzQuota.md)
Dapatkan batas kuota sumber daya.
Respons dapat digunakan untuk menentukan sisa kuota untuk menghitung batas kuota baru yang bisa dikirimkan dengan permintaan PUT.

### [Get-AzQuotaOperation](Get-AzQuotaOperation.md)
Daftar semua operasi yang didukung oleh penyedia sumber daya Microsoft.Quota.

### [Get-AzQuotaRequestStatus](Get-AzQuotaRequestStatus.md)
Dapatkan detail permintaan kuota dan status dengan ID permintaan kuota untuk sumber daya penyedia sumber daya di lokasi tertentu.
Id permintaan **kuota** dikembalikan setelah operasi PUT.

### [Get-AzQuotaUsage](Get-AzQuotaUsage.md)
Dapatkan penggunaan sumber daya saat ini.

### [New-AzQuota](New-AzQuota.md)
Membuat atau memperbarui batas kuota untuk sumber daya tertentu dengan nilai yang diminta.
Untuk memperbarui kuota, ikuti langkah-langkah berikut:\n1.
Gunakan operasi GET untuk kuota dan penggunaan untuk menentukan berapa banyak sisa kuota untuk sumber daya tertentu dan untuk menghitung batas kuota baru.
Langkah-langkah ini dijelaskan secara [mendetail dalam contoh ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).\n2.
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status mendetail permintaan tersebut.

### [New-AzQuotaLimitObject](New-AzQuotaLimitObject.md)
Buat objek dalam memori untuk LimitObject.

### [Update-AzQuota](Update-AzQuota.md)
Perbarui batas kuota untuk sumber daya tertentu ke nilai tertentu:\n1.
Gunakan operasi Usages-GET dan Quota-GET untuk menentukan sisa kuota sumber daya tertentu dan untuk menghitung batas kuota baru.
Langkah-langkah ini dijelaskan secara [mendetail dalam contoh ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).\n2.
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status mendetail permintaan tersebut.

