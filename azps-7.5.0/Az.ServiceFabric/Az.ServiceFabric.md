---
Module Name: Az.ServiceFabric
Module Guid: 60f3ba88-443f-46ff-88a3-318cfd11c1da
Download Help Link: https://docs.microsoft.com/powershell/module/az.servicefabric
Help Version: 0.3.4.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Az.ServiceFabric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Az.ServiceFabric.md
ms.openlocfilehash: 9ff87e20b9ab12ffa060127a96adc946587a56c7
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144199984"
---
# Modul Az.ServiceFabric
## Deskripsi
Modul Azure Service Fabric yang dapat Anda gunakan untuk mengotomatiskan operasi akhir 2-end seperti membuat kluster aman, menggulirkan sertifikat kluster, menambahkan atau menghapus simpul dari kluster, dll. Daftar lengkap semua operasi tercantum di bawah ini.

## Cmdlet Az.ServiceFabric
### [Add-AzServiceFabricClientCertificate](Add-AzServiceFabricClientCertificate.md)
Tambahkan nama umum atau thumbprint ke kluster untuk tujuan autentikasi klien.

### [Add-AzServiceFabricManagedClusterClientCertificate](Add-AzServiceFabricManagedClusterClientCertificate.md)
Tambahkan nama umum sertifikat atau thumbprint ke kluster. Ini akan mendaftarkan sertifikat lagi kluster untuk tujuan autentikasi klien.

### [Add-AzServiceFabricManagedNodeTypeVMExtension](Add-AzServiceFabricManagedNodeTypeVMExtension.md)
Tambahkan ekstensi vm ke jenis node.

### [Add-AzServiceFabricManagedNodeTypeVMSecret](Add-AzServiceFabricManagedNodeTypeVMSecret.md)
Tambahkan rahasia sertifikat ke jenis node.

### [Add-AzServiceFabricNode](Add-AzServiceFabricNode.md)
Tambahkan node ke jenis node tertentu di kluster.

### [Add-AzServiceFabricNodeType](Add-AzServiceFabricNodeType.md)
Tambahkan jenis node baru ke kluster yang ada.

### [Get-AzServiceFabricApplication](Get-AzServiceFabricApplication.md)
Dapatkan detail aplikasi Service Fabric. Hanya mendukung aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricApplicationType](Get-AzServiceFabricApplicationType.md)
Dapatkan detail jenis aplikasi Service Fabric. Hanya mendukung jenis aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricApplicationTypeVersion](Get-AzServiceFabricApplicationTypeVersion.md)
Dapatkan detail versi jenis aplikasi Service Fabric. Hanya mendukung versi jenis aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricCluster](Get-AzServiceFabricCluster.md)
Dapatkan detail sumber daya kluster.

### [Get-AzServiceFabricManagedCluster](Get-AzServiceFabricManagedCluster.md)
Dapatkan detail sumber daya kluster terkelola.

### [Get-AzServiceFabricManagedClusterApplication](Get-AzServiceFabricManagedClusterApplication.md)
Dapatkan detail aplikasi terkelola Service Fabric. Hanya mendukung aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricManagedClusterApplicationType](Get-AzServiceFabricManagedClusterApplicationType.md)
Dapatkan detail jenis aplikasi terkelola Service Fabric. Hanya mendukung jenis aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricManagedClusterApplicationTypeVersion](Get-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Dapatkan detail versi jenis aplikasi terkelola Service Fabric. Hanya mendukung versi jenis aplikasi yang disebarkan ARM.

### [Get-AzServiceFabricManagedClusterService](Get-AzServiceFabricManagedClusterService.md)
Dapatkan detail layanan terkelola Service Fabric di bawah aplikasi dan kluster yang ditentukan. Hanya mendukung layanan yang disebarkan ARM.

### [Get-AzServiceFabricManagedNodeType](Get-AzServiceFabricManagedNodeType.md)
Dapatkan detail sumber daya jenis node terkelola.

### [Get-AzServiceFabricService](Get-AzServiceFabricService.md)
Dapatkan detail layanan Service Fabric di bawah aplikasi dan kluster yang ditentukan. Hanya mendukung layanan yang disebarkan ARM.

### [New-AzServiceFabricApplication](New-AzServiceFabricApplication.md)
Buat aplikasi service fabric baru di bawah grup sumber daya dan kluster yang ditentukan.

### [New-AzServiceFabricApplicationType](New-AzServiceFabricApplicationType.md)
Buat jenis aplikasi service fabric baru di bawah grup sumber daya dan kluster yang ditentukan.

### [New-AzServiceFabricApplicationTypeVersion](New-AzServiceFabricApplicationTypeVersion.md)
Buat versi jenis aplikasi baru di bawah grup sumber daya dan kluster yang ditentukan.

### [Baru-AzServiceFabricCluster](New-AzServiceFabricCluster.md)
Perintah ini menggunakan sertifikat yang Anda berikan atau sertifikat yang ditandatangani sendiri yang dihasilkan sistem untuk menyiapkan kluster service fabric baru. Ini dapat menggunakan templat default atau templat kustom yang Anda sediakan. Anda memiliki opsi untuk menentukan folder untuk mengekspor sertifikat yang ditandatangani sendiri ke atau mengambilnya nanti dari brankas kunci.

### [New-AzServiceFabricManagedCluster](New-AzServiceFabricManagedCluster.md)
Buat kluster terkelola baru.

### [New-AzServiceFabricManagedClusterApplication](New-AzServiceFabricManagedClusterApplication.md)
Buat aplikasi terkelola service fabric baru di bawah grup sumber daya dan kluster yang ditentukan.

### [New-AzServiceFabricManagedClusterApplicationType](New-AzServiceFabricManagedClusterApplicationType.md)
Buat jenis aplikasi terkelola service fabric baru di bawah grup sumber daya dan kluster yang ditentukan.

### [New-AzServiceFabricManagedClusterApplicationTypeVersion](New-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Buat versi jenis aplikasi terkelola baru di bawah grup sumber daya dan kluster yang ditentukan.

### [New-AzServiceFabricManagedClusterService](New-AzServiceFabricManagedClusterService.md)
Buat layanan terkelola service fabric baru di bawah aplikasi dan kluster yang ditentukan.

### [New-AzServiceFabricManagedNodeType](New-AzServiceFabricManagedNodeType.md)
Buat sumber daya jenis node baru.

### [New-AzServiceFabricService](New-AzServiceFabricService.md)
Buat layanan service fabric baru di bawah aplikasi dan kluster yang ditentukan.

### [Remove-AzServiceFabricApplication](Remove-AzServiceFabricApplication.md)
Menghapus aplikasi dari kluster. Ini akan menghapus semua layanan di bawah aplikasi. Hanya mendukung aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricApplicationType](Remove-AzServiceFabricApplicationType.md)
Hapus Service fabric jenis aplikasi dari kluster. Ini akan menghapus semua versi jenis di bawah sumber daya ini. Hanya mendukung jenis aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricApplicationTypeVersion](Remove-AzServiceFabricApplicationTypeVersion.md)
Hapus Service fabric versi jenis aplikasi dari kluster. Hanya mendukung versi jenis aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricClientCertificate](Remove-AzServiceFabricClientCertificate.md)
Hapus sertifikat klien atau nama subjek sertifikat agar tidak digunakan untuk autentikasi klien ke kluster.

### [Remove-AzServiceFabricManagedCluster](Remove-AzServiceFabricManagedCluster.md)
Hapus sumber daya kluster.

### [Remove-AzServiceFabricManagedClusterApplication](Remove-AzServiceFabricManagedClusterApplication.md)
Menghapus aplikasi terkelola dari kluster. Ini akan menghapus semua layanan terkelola di bawah aplikasi. Hanya mendukung aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricManagedClusterApplicationType](Remove-AzServiceFabricManagedClusterApplicationType.md)
Menghapus jenis aplikasi terkelola dari kluster. Ini akan menghapus semua versi jenis di bawah sumber daya ini. Hanya mendukung jenis aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricManagedClusterApplicationTypeVersion](Remove-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Menghapus versi jenis aplikasi terkelola dari kluster. Hanya mendukung versi jenis aplikasi yang disebarkan ARM.

### [Remove-AzServiceFabricManagedClusterClientCertificate](Remove-AzServiceFabricManagedClusterClientCertificate.md)
Remvoe sertifikat klien dengan thumbprint atau nama umum.

### [Remove-AzServiceFabricManagedClusterService](Remove-AzServiceFabricManagedClusterService.md)
Menghapus layanan terkelola dari kluster. Hanya mendukung layanan yang disebarkan ARM.

### [Remove-AzServiceFabricManagedNodeType](Remove-AzServiceFabricManagedNodeType.md)
Hapus jenis node atau node tertentu dalam jenis node.

### [Remove-AzServiceFabricManagedNodeTypeVMExtension](Remove-AzServiceFabricManagedNodeTypeVMExtension.md)
Hapus ekstensi vm dari jenis node.

### [Remove-AzServiceFabricNode](Remove-AzServiceFabricNode.md)
Hapus node dari jenis node tertentu dari kluster.

### [Remove-AzServiceFabricNodeType](Remove-AzServiceFabricNodeType.md)
Menghapus jenis node lengkap dari kluster.

### [Remove-AzServiceFabricService](Remove-AzServiceFabricService.md)
Menghapus layanan dari kluster. Hanya mendukung layanan yang disebarkan ARM.

### [Remove-AzServiceFabricSetting](Remove-AzServiceFabricSetting.md)
Hapus satu atau beberapa pengaturan Service Fabric dari kluster.

### [Restart-AzServiceFabricManagedNodeType](Restart-AzServiceFabricManagedNodeType.md)
Hidupkan ulang simpul tertentu dari jenis node.

### [Set-AzServiceFabricManagedCluster](Set-AzServiceFabricManagedCluster.md)
Atur properti sumber daya kluster.

### [Set-AzServiceFabricManagedClusterApplication](Set-AzServiceFabricManagedClusterApplication.md)
Memperbarui aplikasi yang dikelola service fabric. Ini memungkinkan untuk memperbarui parameter aplikasi dan/atau meningkatkan versi jenis aplikasi yang akan memicu peningkatan aplikasi atau pembaruan konfigurasi lainnya saja. Hanya mendukung aplikasi yang disebarkan ARM.

### [Set-AzServiceFabricManagedClusterApplicationType](Set-AzServiceFabricManagedClusterApplicationType.md)
Memperbarui jenis aplikasi yang dikelola service fabric. Ini memungkinkan Anda memperbarui tag. Hanya mendukung jenis aplikasi yang disebarkan ARM.

### [Set-AzServiceFabricManagedClusterApplicationTypeVersion](Set-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Memperbarui versi jenis aplikasi terkelola service fabric. Ini memungkinkan Anda memperbarui tag dan Url paket. Hanya mendukung versi jenis aplikasi yang disebarkan ARM.

### [Set-AzServiceFabricManagedClusterService](Set-AzServiceFabricManagedClusterService.md)
Memperbarui layanan terkelola dari kluster. Hanya mendukung layanan yang disebarkan ARM.

### [Set-AzServiceFabricManagedNodeType](Set-AzServiceFabricManagedNodeType.md)
Mengatur properti sumber daya jenis node atau menjalankan tindakan reimage pada ndes tertentu dari jenis node dengan parameter -Reimage.

### [Set-AzServiceFabricSetting](Set-AzServiceFabricSetting.md)
Tambahkan atau perbarui satu atau beberapa pengaturan Service Fabric ke kluster.

### [Set-AzServiceFabricUpgradeType](Set-AzServiceFabricUpgradeType.md)
Ubah jenis peningkatan Service Fabric kluster.

### [Update-AzServiceFabricApplication](Update-AzServiceFabricApplication.md)
Memperbarui aplikasi service fabric. Ini memungkinkan untuk memperbarui parameter aplikasi dan/atau meningkatkan versi jenis aplikasi yang akan memicu peningkatan aplikasi. Hanya mendukung aplikasi yang disebarkan ARM.

### [Update-AzServiceFabricDurability](Update-AzServiceFabricDurability.md)
Perbarui tingkat durabilitas atau VmSku dari jenis node di kluster.

### [Update-AzServiceFabricNodeType](Update-AzServiceFabricNodeType.md)
Perbarui jenis node dalam kluster.

### [Update-AzServiceFabricReliability](Update-AzServiceFabricReliability.md)
Perbarui tingkat keandalan jenis node utama dalam kluster.

### [Update-AzServiceFabricVmImage](Update-AzServiceFabricVmImage.md)
Perbarui pengaturan vmImage sumber daya kluster yang memetakan paket runtime yang sesuai untuk dikirimkan berdasarkan sistem operasi target.

