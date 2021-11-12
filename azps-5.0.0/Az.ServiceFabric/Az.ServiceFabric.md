---
Module Name: Az.ServiceFabric
Module Guid: 60f3ba88-443f-46ff-88a3-318cfd11c1da
Download Help Link: https://docs.microsoft.com/en-us/powershell/module/az.servicefabric
Help Version: 0.3.4.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/ServiceFabric/ServiceFabric/help/Az.ServiceFabric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/ServiceFabric/ServiceFabric/help/Az.ServiceFabric.md
ms.openlocfilehash: 6c58f25209a0acd227e2f04e7ca808916f283d46
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132407577"
---
# Az.ServiceFabric Module
## Deskripsi
Azure Service Fabric Module yang dapat Anda gunakan untuk mengotomatisasi operasi end-2-end seperti membuat kluster yang aman, menggulung sertifikat kluster, menambahkan atau menghapus node dari kluster, dll. Daftar lengkap semua operasi dicantumkan di bawah ini.

## Cmdlet Az.ServiceFabric
### [Add-AzServiceFabricClientCertificate](Add-AzServiceFabricClientCertificate.md)
Tambahkan nama atau thumbprint umum ke kluster untuk tujuan autentikasi klien.

### [Add-AzServiceFabricClusterCertificate](Add-AzServiceFabricClusterCertificate.md)
Menambahkan sertifikat kluster sekunder ke kluster.

### [Add-AzServiceFabricManagedClusterClientCertificate](Add-AzServiceFabricManagedClusterClientCertificate.md)
Tambahkan sertifikat nama umum atau thumbprint ke kluster. Langkah ini akan mendaftarkan kembali sertifikat kluster untuk tujuan autentikasi klien.

### [Add-AzServiceFabricManagedNodeTypeVMExtension](Add-AzServiceFabricManagedNodeTypeVMExtension.md)
Tambahkan ekstensi vm ke tipe node.

### [Add-AzServiceFabricManagedNodeTypeVMSecret](Add-AzServiceFabricManagedNodeTypeVMSecret.md)
Tambahkan sertifikat rahasia ke tipe node.

### [Add-AzServiceFabricNode](Add-AzServiceFabricNode.md)
Tambahkan node ke tipe node tertentu dalam kluster.

### [Add-AzServiceFabricNodeType](Add-AzServiceFabricNodeType.md)
Tambahkan tipe node baru ke kluster yang sudah ada.

### [Get-AzServiceFabricApplication](Get-AzServiceFabricApplication.md)
Dapatkan Service Fabric detail aplikasi.

### [Get-AzServiceFabricApplicationType](Get-AzServiceFabricApplicationType.md)
Dapatkan Service Fabric jenis aplikasi.

### [Get-AzServiceFabricApplicationTypeVersion](Get-AzServiceFabricApplicationTypeVersion.md)
Dapatkan Service Fabric versi jenis aplikasi.

### [Get-AzServiceFabricCluster](Get-AzServiceFabricCluster.md)
Dapatkan detail sumber daya kluster.

### [Get-AzServiceFabricManagedCluster](Get-AzServiceFabricManagedCluster.md)
Dapatkan detail sumber daya kluster terkelola.

### [Get-AzServiceFabricManagedNodeType](Get-AzServiceFabricManagedNodeType.md)
Dapatkan detail sumber daya tipe node terkelola.

### [Get-AzServiceFabricService](Get-AzServiceFabricService.md)
Dapatkan Service Fabric layanan berdasarkan aplikasi dan kluster yang ditentukan.

### [New-AzServiceFabricApplication](New-AzServiceFabricApplication.md)
Create new service fabric application under the specified resource group and cluster.

### [New-AzServiceFabricApplicationType](New-AzServiceFabricApplicationType.md)
Create new service fabric application type under the specified resource group and cluster.

### [New-AzServiceFabricApplicationTypeVersion](New-AzServiceFabricApplicationTypeVersion.md)
Buat versi tipe aplikasi baru di bawah grup dan kluster sumber daya yang ditentukan.

### [New-AzServiceFabricCluster](New-AzServiceFabricCluster.md)
This command uses certificates that you provide or system generated self-signed certificates to set up a new service fabric cluster. Templat ini dapat menggunakan templat default atau templat kustom yang telah diberikan. Anda memiliki opsi menentukan folder untuk mengekspor sertifikat yang ditandatangani sendiri untuk atau mengambilnya nanti dari kunci vault.

### [New-AzServiceFabricManagedCluster](New-AzServiceFabricManagedCluster.md)
Membuat kluster terkelola baru.

### [New-AzServiceFabricManagedNodeType](New-AzServiceFabricManagedNodeType.md)
Buat sumber daya tipe node baru.

### [New-AzServiceFabricService](New-AzServiceFabricService.md)
Create new service fabric service under the specified application and cluster.

### [Remove-AzServiceFabricApplication](Remove-AzServiceFabricApplication.md)
Menghapus aplikasi dari kluster. Ini akan menghapus semua layanan di bawah aplikasi tersebut.

### [Remove-AzServiceFabricApplicationType](Remove-AzServiceFabricApplicationType.md)
Remove Service fabric an application type from the cluster. Ini akan menghapus semua versi tipe di bawah sumber daya ini.

### [Remove-AzServiceFabricApplicationTypeVersion](Remove-AzServiceFabricApplicationTypeVersion.md)
Remove Service fabric an application type version from the cluster.

### [Remove-AzServiceFabricClientCertificate](Remove-AzServiceFabricClientCertificate.md)
Hapus nama subjek sertifikat atau sertifikat klien agar tidak digunakan untuk autentikasi klien ke kluster.

### [Remove-AzServiceFabricClusterCertificate](Remove-AzServiceFabricClusterCertificate.md)
Hapus sertifikat kluster agar tidak digunakan untuk keamanan kluster.

### [Remove-AzServiceFabricManagedCluster](Remove-AzServiceFabricManagedCluster.md)
Menghapus sumber daya kluster.

### [Remove-AzServiceFabricManagedClusterClientCertificate](Remove-AzServiceFabricManagedClusterClientCertificate.md)
Sertifikat klien remvoe berdasarkan thumbprint atau nama umum.

### [Remove-AzServiceFabricManagedNodeType](Remove-AzServiceFabricManagedNodeType.md)
Hapus tipe node atau node tertentu di dalam tipe node.

### [Remove-AzServiceFabricManagedNodeTypeVMExtension](Remove-AzServiceFabricManagedNodeTypeVMExtension.md)
Hapus ekstensi vm dari tipe node.

### [Remove-AzServiceFabricNode](Remove-AzServiceFabricNode.md)
Hapus node dari tipe node tertentu dari kluster.

### [Remove-AzServiceFabricNodeType](Remove-AzServiceFabricNodeType.md)
Menghapus tipe node lengkap dari kluster.

### [Remove-AzServiceFabricService](Remove-AzServiceFabricService.md)
Menghapus layanan dari kluster.

### [Remove-AzServiceFabricSetting](Remove-AzServiceFabricSetting.md)
Hapus satu atau beberapa Service Fabric kluster dari kluster.

### [Restart-AzServiceFabricManagedNodeType](Restart-AzServiceFabricManagedNodeType.md)
Mulai ulang node tertentu dari tipe node.

### [Set-AzServiceFabricManagedCluster](Set-AzServiceFabricManagedCluster.md)
Mengatur properti sumber daya kluster.

### [Set-AzServiceFabricManagedNodeType](Set-AzServiceFabricManagedNodeType.md)
Mengatur properti sumber daya tipe node atau menjalankan tindakanimasi ulang pada ndes tipe node tertentu dengan parameter -Reimage.

### [Set-AzServiceFabricSetting](Set-AzServiceFabricSetting.md)
Menambahkan atau memperbarui satu atau beberapa Service Fabric ke kluster.

### [Set-AzServiceFabricUpgradeType](Set-AzServiceFabricUpgradeType.md)
Ubah Service Fabric pemutakhiran kluster.

### [Update-AzServiceFabricApplication](Update-AzServiceFabricApplication.md)
Update a service fabric application. Ini memungkinkan untuk memperbarui parameter aplikasi dan/atau memutakhirkan versi tipe aplikasi yang akan memicu pemutakhiran aplikasi.

### [Update-azServiceFabricDurability](Update-AzServiceFabricDurability.md)
Perbarui tier durability atau VmSku tipe node dalam kluster.

### [Update-AzServiceFabricReliability](Update-AzServiceFabricReliability.md)
Perbarui tingkat keandalan tipe node utama dalam kluster.

