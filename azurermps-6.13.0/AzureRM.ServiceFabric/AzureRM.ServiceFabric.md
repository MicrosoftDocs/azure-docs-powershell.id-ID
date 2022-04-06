---
Module Name: AzureRM.ServiceFabric
Module Guid: 60f3ba88-443f-46ff-88a3-318cfd11c1da
Download Help Link: https://docs.microsoft.com/en-us/powershell/module/azurerm.servicefabric
Help Version: 0.3.4.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/AzureRM.ServiceFabric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/AzureRM.ServiceFabric.md
ms.openlocfilehash: 6d93775a028e7a590a8da9cc008640fb8484bdf2
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/25/2022
ms.locfileid: "132414945"
---
# AzureRM.ServiceFabric Module
## Deskripsi
Azure Service Fabric Module yang dapat Anda gunakan untuk mengotomatisasi operasi end-2-end seperti membuat kluster yang aman, menggulung sertifikat kluster, menambahkan atau menghapus node dari kluster, dll. Daftar lengkap semua operasi dicantumkan di bawah ini.

## Cmdlet AzureRM.ServiceFabric
### [Add-AzureRmServiceFabricApplicationCertificate](Add-AzureRmServiceFabricApplicationCertificate.md)
Tambahkan sertifikat baru ke Kumpulan Skala Mesin Virtual yang menjadi kluster. Sertifikat tersebut dimaksudkan untuk digunakan sebagai sertifikat aplikasi.

### [Add-AzureRmServiceFabricClientCertificate](Add-AzureRmServiceFabricClientCertificate.md)
Tambahkan nama atau thumbprint umum ke kluster untuk tujuan autentikasi klien.

### [Add-AzureRmServiceFabricClusterCertificate](Add-AzureRmServiceFabricClusterCertificate.md)
Menambahkan sertifikat kluster sekunder ke kluster.

### [Add-AzureRmServiceFabricNode](Add-AzureRmServiceFabricNode.md)
Tambahkan node ke tipe node tertentu dalam kluster.

### [Add-AzureRmServiceFabricNodeType](Add-AzureRmServiceFabricNodeType.md)
Tambahkan tipe node baru ke kluster yang sudah ada.

### [Get-AzureRmServiceFabricCluster](Get-AzureRmServiceFabricCluster.md)
Dapatkan detail sumber daya kluster.

### [New-AzureRmServiceFabricCluster](New-AzureRmServiceFabricCluster.md)
This command uses certificates that you provide or system generated self-signed certificates to set up a new service fabric cluster. Templat ini dapat menggunakan templat default atau templat kustom yang telah diberikan. Anda memiliki opsi menentukan folder untuk mengekspor sertifikat yang ditandatangani sendiri untuk atau mengambilnya nanti dari kunci vault. 

### [Remove-AzureRmServiceFabricClientCertificate](Remove-AzureRmServiceFabricClientCertificate.md)
Hapus nama subjek sertifikat atau sertifikat klien agar tidak digunakan untuk autentikasi klien ke kluster.

### [Remove-AzureRmServiceFabricClusterCertificate](Remove-AzureRmServiceFabricClusterCertificate.md)
Hapus sertifikat kluster agar tidak digunakan untuk keamanan kluster.

### [Remove-AzureRmServiceFabricNode](Remove-AzureRmServiceFabricNode.md)
Hapus node dari tipe node tertentu dari kluster.

### [Remove-AzureRmServiceFabricNodeType](Remove-AzureRmServiceFabricNodeType.md)
Menghapus tipe node lengkap dari kluster.

### [Remove-AzureRmServiceFabricSetting](Remove-AzureRmServiceFabricSetting.md)
Menghapus satu atau Service Fabric kluster dari kluster.

### [Set-AzureRmServiceFabricSetting](Set-AzureRmServiceFabricSetting.md)
Tambahkan atau perbarui satu atau Service Fabric yang sama ke kluster.

### [Set-AzureRmServiceFabricUpgradeType](Set-AzureRmServiceFabricUpgradeType.md)
Ubah Service Fabric pemutakhiran kluster.

### [Update-AzureRmServiceFabricDurability](Update-AzureRmServiceFabricDurability.md)
Perbarui tier durability atau VmSku tipe node dalam kluster.

### [Update-AzureRmServiceFabricReliability](Update-AzureRmServiceFabricReliability.md)
Perbarui tingkat keandalan tipe node utama dalam kluster.

