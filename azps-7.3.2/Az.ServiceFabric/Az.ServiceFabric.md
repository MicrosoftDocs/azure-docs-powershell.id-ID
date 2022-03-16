---
Module Name: Az.ServiceFabric
Module Guid: 60f3ba88-443f-46ff-88a3-318cfd11c1da
Download Help Link: https://docs.microsoft.com/powershell/module/az.servicefabric
Help Version: 0.3.4.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Az.ServiceFabric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Az.ServiceFabric.md
ms.openlocfilehash: 9ff87e20b9ab12ffa060127a96adc946587a56c7
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140183759"
---
# Az.ServiceFabric Module
## Deskripsi
Azure Service Fabric Module yang dapat Anda gunakan untuk mengotomatisasi operasi end-2-end seperti membuat kluster yang aman, menggulung sertifikat kluster, menambahkan atau menghapus node dari kluster, dll. Daftar lengkap semua operasi dicantumkan di bawah ini.

## Cmdlet Az.ServiceFabric
### [Add-AzServiceFabricClientCertificate](Add-AzServiceFabricClientCertificate.md)
Tambahkan nama atau thumbprint umum ke kluster untuk tujuan autentikasi klien.

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
Dapatkan Service Fabric aplikasi selengkapnya. Hanya mendukung aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricApplicationType](Get-AzServiceFabricApplicationType.md)
Dapatkan Service Fabric jenis aplikasi. Hanya mendukung tipe aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricApplicationTypeVersion](Get-AzServiceFabricApplicationTypeVersion.md)
Dapatkan Service Fabric versi jenis aplikasi. Hanya mendukung versi tipe aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricCluster](Get-AzServiceFabricCluster.md)
Dapatkan detail sumber daya kluster.

### [Get-AzServiceFabricManagedCluster](Get-AzServiceFabricManagedCluster.md)
Dapatkan detail sumber daya kluster terkelola.

### [Get-AzServiceFabricManagedClusterApplication](Get-AzServiceFabricManagedClusterApplication.md)
Dapatkan Service Fabric aplikasi yang dikelola. Hanya mendukung aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricManagedClusterApplicationType](Get-AzServiceFabricManagedClusterApplicationType.md)
Dapatkan Service Fabric jenis aplikasi yang dikelola. Hanya mendukung tipe aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricManagedClusterApplicationTypeVersion](Get-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Dapatkan Service Fabric versi jenis aplikasi yang dikelola. Hanya mendukung versi tipe aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricManagedClusterService](Get-AzServiceFabricManagedClusterService.md)
Dapatkan Service Fabric layanan terkelola dalam aplikasi dan kluster yang ditentukan. Hanya mendukung layanan ARM yang disebarkan.

### [Get-AzServiceFabricManagedNodeType](Get-AzServiceFabricManagedNodeType.md)
Dapatkan detail sumber daya tipe node terkelola.

### [Get-AzServiceFabricService](Get-AzServiceFabricService.md)
Dapatkan Service Fabric layanan berdasarkan aplikasi dan kluster yang ditentukan. Hanya mendukung layanan ARM yang disebarkan.

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

### [New-AzServiceFabricManagedClusterApplication](New-AzServiceFabricManagedClusterApplication.md)
Create new service fabric managed application under the specified resource group and cluster.

### [New-AzServiceFabricManagedClusterApplicationType](New-AzServiceFabricManagedClusterApplicationType.md)
Create new service fabric managed application type under the specified resource group and cluster.

### [New-AzServiceFabricManagedClusterApplicationTypeVersion](New-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Buat versi tipe aplikasi terkelola baru di bawah grup dan kluster sumber daya yang ditentukan.

### [New-AzServiceFabricManagedClusterService](New-AzServiceFabricManagedClusterService.md)
Create new service fabric managed service under the specified application and cluster.

### [New-AzServiceFabricManagedNodeType](New-AzServiceFabricManagedNodeType.md)
Buat sumber daya tipe node baru.

### [New-AzServiceFabricService](New-AzServiceFabricService.md)
Create new service fabric service under the specified application and cluster.

### [Remove-AzServiceFabricApplication](Remove-AzServiceFabricApplication.md)
Menghapus aplikasi dari kluster. Ini akan menghapus semua layanan di bawah aplikasi tersebut. Hanya mendukung aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricApplicationType](Remove-AzServiceFabricApplicationType.md)
Remove Service fabric an application type from the cluster. Ini akan menghapus semua versi tipe di bawah sumber daya ini. Hanya mendukung tipe aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricApplicationTypeVersion](Remove-AzServiceFabricApplicationTypeVersion.md)
Remove Service fabric an application type version from the cluster. Hanya mendukung versi tipe aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricClientCertificate](Remove-AzServiceFabricClientCertificate.md)
Hapus nama subjek sertifikat atau sertifikat klien agar tidak digunakan untuk autentikasi klien ke kluster.

### [Remove-AzServiceFabricManagedCluster](Remove-AzServiceFabricManagedCluster.md)
Menghapus sumber daya kluster.

### [Remove-AzServiceFabricManagedClusterApplication](Remove-AzServiceFabricManagedClusterApplication.md)
Menghapus aplikasi yang dikelola dari kluster. This will remove all the managed services under the application. Hanya mendukung aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricManagedClusterApplicationType](Remove-AzServiceFabricManagedClusterApplicationType.md)
Menghapus tipe aplikasi terkelola dari kluster. Ini akan menghapus semua versi tipe di bawah sumber daya ini. Hanya mendukung tipe aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricManagedClusterApplicationTypeVersion](Remove-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Menghapus versi tipe aplikasi terkelola dari kluster. Hanya mendukung versi tipe aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricManagedClusterClientCertificate](Remove-AzServiceFabricManagedClusterClientCertificate.md)
Sertifikat klien remvoe berdasarkan thumbprint atau nama umum.

### [Remove-AzServiceFabricManagedClusterService](Remove-AzServiceFabricManagedClusterService.md)
Menghapus layanan terkelola dari kluster. Hanya mendukung layanan ARM yang disebarkan.

### [Remove-AzServiceFabricManagedNodeType](Remove-AzServiceFabricManagedNodeType.md)
Hapus tipe node atau node tertentu di dalam tipe node.

### [Remove-AzServiceFabricManagedNodeTypeVMExtension](Remove-AzServiceFabricManagedNodeTypeVMExtension.md)
Hapus ekstensi vm dari tipe node.

### [Remove-AzServiceFabricNode](Remove-AzServiceFabricNode.md)
Hapus node dari tipe node tertentu dari kluster.

### [Remove-AzServiceFabricNodeType](Remove-AzServiceFabricNodeType.md)
Menghapus tipe node lengkap dari kluster.

### [Remove-AzServiceFabricService](Remove-AzServiceFabricService.md)
Menghapus layanan dari kluster. Hanya mendukung layanan ARM yang disebarkan.

### [Remove-AzServiceFabricSetting](Remove-AzServiceFabricSetting.md)
Menghapus satu atau Service Fabric kluster dari kluster.

### [Restart-AzServiceFabricManagedNodeType](Restart-AzServiceFabricManagedNodeType.md)
Mulai ulang node tertentu dari tipe node.

### [Set-AzServiceFabricManagedCluster](Set-AzServiceFabricManagedCluster.md)
Mengatur properti sumber daya kluster.

### [Set-AzServiceFabricManagedClusterApplication](Set-AzServiceFabricManagedClusterApplication.md)
Update a service fabric managed application. Hal ini memungkinkan untuk memperbarui parameter aplikasi dan/atau memutakhirkan versi tipe aplikasi yang akan memicu pemutakhiran aplikasi atau pembaruan konfigurasi lainnya saja. Hanya mendukung aplikasi yang disebarkan ARM.

### [Set-AzServiceFabricManagedClusterApplicationType](Set-AzServiceFabricManagedClusterApplicationType.md)
Update a service fabric managed application type. Ini memungkinkan Anda memperbarui tag. Hanya mendukung tipe aplikasi yang disebarkan ARM.

### [Set-AzServiceFabricManagedClusterApplicationTypeVersion](Set-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Update a service fabric managed application type version. Ini memungkinkan Anda untuk memperbarui url tag dan paket. Hanya mendukung versi tipe aplikasi yang disebarkan ARM.

### [Set-AzServiceFabricManagedClusterService](Set-AzServiceFabricManagedClusterService.md)
Memperbarui layanan yang dikelola dari kluster. Hanya mendukung layanan ARM yang disebarkan.

### [Set-AzServiceFabricManagedNodeType](Set-AzServiceFabricManagedNodeType.md)
Mengatur properti sumber daya tipe node atau menjalankan tindakanimasi ulang pada ndes tipe node tertentu dengan parameter -Reimage.

### [Set-AzServiceFabricSetting](Set-AzServiceFabricSetting.md)
Tambahkan atau perbarui satu atau Service Fabric yang sama ke kluster.

### [Set-AzServiceFabricUpgradeType](Set-AzServiceFabricUpgradeType.md)
Ubah Service Fabric pemutakhiran kluster.

### [Update-AzServiceFabricApplication](Update-AzServiceFabricApplication.md)
Update a service fabric application. Ini memungkinkan untuk memperbarui parameter aplikasi dan/atau memutakhirkan versi tipe aplikasi yang akan memicu pemutakhiran aplikasi. Hanya mendukung aplikasi yang disebarkan ARM.

### [Update-azServiceFabricDurability](Update-AzServiceFabricDurability.md)
Perbarui tier durability atau VmSku tipe node dalam kluster.

### [Update-azServiceFabricNodeType](Update-AzServiceFabricNodeType.md)
Memperbarui tipe node dalam kluster.

### [Update-AzServiceFabricReliability](Update-AzServiceFabricReliability.md)
Perbarui tingkat keandalan tipe node utama dalam kluster.

### [Update-AzServiceFabricVmImage](Update-AzServiceFabricVmImage.md)
Perbarui pengaturan vmImage sumber daya kluster yang memetakan paket runtime yang sesuai untuk dikirimkan berdasarkan sistem operasi target.

