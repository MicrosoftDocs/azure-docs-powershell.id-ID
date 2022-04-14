---
Module Name: Az.ServiceFabric
Module Guid: 60f3ba88-443f-46ff-88a3-318cfd11c1da
Download Help Link: https://docs.microsoft.com/powershell/module/az.servicefabric
Help Version: 0.3.4.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Az.ServiceFabric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Az.ServiceFabric.md
ms.openlocfilehash: 9ff87e20b9ab12ffa060127a96adc946587a56c7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141990203"
---
# Modul Az.ServiceFabric
## Deskripsi
Azure Service Fabric Module yang dapat Anda gunakan untuk mengotomatisasi operasi akhir 2-end seperti membuat kluster yang aman, menggulung sertifikat kluster, menambahkan atau menghapus node dari kluster, dll. Daftar lengkap semua operasi tercantum di bawah ini.

## Cmdlet Az.ServiceFabric
### [Add-AzServiceFabricClientCertificate](Add-AzServiceFabricClientCertificate.md)
Tambahkan nama umum atau sidik jari ke kluster untuk tujuan autentikasi klien.

### [Add-AzServiceFabricManagedClusterClientCertificate](Add-AzServiceFabricManagedClusterClientCertificate.md)
Tambahkan nama umum sertifikat atau sidik jari ke kluster. Ini akan mendaftarkan sertifikat lagi kluster untuk tujuan autentikasi klien.

### [Add-AzServiceFabricManagedNodeTypeVMExtension](Add-AzServiceFabricManagedNodeTypeVMExtension.md)
Tambahkan ekstensi vm ke tipe simpul.

### [Add-AzServiceFabricManagedNodeTypeVMSecret](Add-AzServiceFabricManagedNodeTypeVMSecret.md)
Tambahkan rahasia sertifikat ke tipe simpul.

### [Add-AzServiceFabricNode](Add-AzServiceFabricNode.md)
Tambahkan node ke tipe simpul tertentu dalam kluster.

### [Add-AzServiceFabricNodeType](Add-AzServiceFabricNodeType.md)
Tambahkan tipe node baru ke kluster yang sudah ada.

### [Get-AzServiceFabricApplication](Get-AzServiceFabricApplication.md)
Dapatkan detail aplikasi Service Fabric. Hanya mendukung aplikasi arm yang digunakan.

### [Get-AzServiceFabricApplicationType](Get-AzServiceFabricApplicationType.md)
Dapatkan detail tipe aplikasi Service Fabric. Hanya mendukung ARM tipe aplikasi yang digunakan.

### [Get-AzServiceFabricApplicationTypeVersion](Get-AzServiceFabricApplicationTypeVersion.md)
Dapatkan detail versi tipe aplikasi Service Fabric. Hanya mendukung ARM versi tipe aplikasi yang digunakan.

### [Get-AzServiceFabricCluster](Get-AzServiceFabricCluster.md)
Dapatkan detail sumber daya kluster.

### [Get-AzServiceFabricManagedCluster](Get-AzServiceFabricManagedCluster.md)
Dapatkan detail sumber daya kluster terkelola.

### [Get-AzServiceFabricManagedClusterApplication](Get-AzServiceFabricManagedClusterApplication.md)
Dapatkan detail aplikasi terkelola Service Fabric. Hanya mendukung aplikasi arm yang digunakan.

### [Get-AzServiceFabricManagedClusterApplicationType](Get-AzServiceFabricManagedClusterApplicationType.md)
Dapatkan detail tipe aplikasi terkelola Service Fabric. Hanya mendukung ARM tipe aplikasi yang digunakan.

### [Get-AzServiceFabricManagedClusterApplicationTypeVersion](Get-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Dapatkan detail versi tipe aplikasi terkelola Service Fabric. Hanya mendukung ARM versi tipe aplikasi yang digunakan.

### [Get-AzServiceFabricManagedClusterService](Get-AzServiceFabricManagedClusterService.md)
Dapatkan detail layanan terkelola Service Fabric di bawah aplikasi dan kluster yang ditentukan. Hanya mendukung layanan arm yang disebarkan.

### [Get-AzServiceFabricManagedNodeType](Get-AzServiceFabricManagedNodeType.md)
Dapatkan detail sumber daya tipe simpul terkelola.

### [Get-AzServiceFabricService](Get-AzServiceFabricService.md)
Dapatkan detail layanan Service Fabric di bawah aplikasi dan kluster yang ditentukan. Hanya mendukung layanan arm yang disebarkan.

### [New-AzServiceFabricApplication](New-AzServiceFabricApplication.md)
Buat aplikasi kain layanan baru di bawah kelompok dan kluster sumber daya yang ditentukan.

### [New-AzServiceFabricApplicationType](New-AzServiceFabricApplicationType.md)
Buat jenis aplikasi kain layanan baru di bawah kelompok dan kluster sumber daya yang ditentukan.

### [New-AzServiceFabricApplicationTypeVersion](New-AzServiceFabricApplicationTypeVersion.md)
Buat versi tipe aplikasi baru di bawah grup sumber daya dan kluster yang ditentukan.

### [New-AzServiceFabricCluster](New-AzServiceFabricCluster.md)
Perintah ini menggunakan sertifikat yang Anda berikan atau sistem yang dibuat sertifikat yang ditandatangani sendiri untuk menyiapkan kluster kain layanan baru. Templat dapat menggunakan templat default atau templat kustom yang Anda sediakan. Anda memiliki opsi untuk menentukan folder untuk mengekspor sertifikat yang ditandatangani sendiri atau mengambilnya nanti dari kubah kunci.

### [New-AzServiceFabricManagedCluster](New-AzServiceFabricManagedCluster.md)
Buat kluster terkelola baru.

### [New-AzServiceFabricManagedClusterApplication](New-AzServiceFabricManagedClusterApplication.md)
Buat aplikasi terkelola kain layanan baru di bawah kelompok dan kluster sumber daya yang ditentukan.

### [New-AzServiceFabricManagedClusterApplicationType](New-AzServiceFabricManagedClusterApplicationType.md)
Buat jenis aplikasi terkelola kain layanan baru di bawah grup sumber daya dan kluster yang ditentukan.

### [New-AzServiceFabricManagedClusterApplicationTypeVersion](New-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Buat versi tipe aplikasi terkelola baru di bawah grup sumber daya dan kluster yang ditentukan.

### [New-AzServiceFabricManagedClusterService](New-AzServiceFabricManagedClusterService.md)
Buat servis servis baru yang dikelola kain di bawah aplikasi dan kluster yang ditentukan.

### [New-AzServiceFabricManagedNodeType](New-AzServiceFabricManagedNodeType.md)
Buat sumber daya tipe simpul baru.

### [New-AzServiceFabricService](New-AzServiceFabricService.md)
Buat layanan baru layanan fabric service di bawah aplikasi dan kluster yang ditentukan.

### [Remove-AzServiceFabricApplication](Remove-AzServiceFabricApplication.md)
Hapus aplikasi dari kluster. Tindakan ini akan menghapus semua layanan di bawah aplikasi. Hanya mendukung aplikasi arm yang digunakan.

### [Remove-AzServiceFabricApplicationType](Remove-AzServiceFabricApplicationType.md)
Hapus Service fabric tipe aplikasi dari kluster. Tindakan ini akan menghapus semua versi tipe di bawah sumber daya ini. Hanya mendukung ARM tipe aplikasi yang digunakan.

### [Remove-AzServiceFabricApplicationTypeVersion](Remove-AzServiceFabricApplicationTypeVersion.md)
Hapus Service fabric versi tipe aplikasi dari kluster. Hanya mendukung ARM versi tipe aplikasi yang digunakan.

### [Remove-AzServiceFabricClientCertificate](Remove-AzServiceFabricClientCertificate.md)
Hapus sertifikat klien atau nama subjek sertifikat agar tidak digunakan untuk autentikasi klien ke kluster.

### [Remove-AzServiceFabricManagedCluster](Remove-AzServiceFabricManagedCluster.md)
Hapus sumber daya kluster.

### [Remove-AzServiceFabricManagedClusterApplication](Remove-AzServiceFabricManagedClusterApplication.md)
Hapus aplikasi yang dikelola dari kluster. Tindakan ini akan menghapus semua layanan terkelola di bawah aplikasi. Hanya mendukung aplikasi arm yang digunakan.

### [Remove-AzServiceFabricManagedClusterApplicationType](Remove-AzServiceFabricManagedClusterApplicationType.md)
Menghapus tipe aplikasi yang dikelola dari kluster. Tindakan ini akan menghapus semua versi tipe di bawah sumber daya ini. Hanya mendukung ARM tipe aplikasi yang digunakan.

### [Remove-AzServiceFabricManagedClusterApplicationTypeVersion](Remove-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Menghapus versi tipe aplikasi terkelola dari kluster. Hanya mendukung ARM versi tipe aplikasi yang digunakan.

### [Remove-AzServiceFabricManagedClusterClientCertificate](Remove-AzServiceFabricManagedClusterClientCertificate.md)
Cabut sertifikat klien dengan sidik jari atau nama umum.

### [Remove-AzServiceFabricManagedClusterService](Remove-AzServiceFabricManagedClusterService.md)
Hapus layanan terkelola dari kluster. Hanya mendukung layanan arm yang disebarkan.

### [Remove-AzServiceFabricManagedNodeType](Remove-AzServiceFabricManagedNodeType.md)
Hapus tipe node atau node tertentu dalam tipe simpul.

### [Remove-AzServiceFabricManagedNodeTypeVMExtension](Remove-AzServiceFabricManagedNodeTypeVMExtension.md)
Hapus ekstensi vm dari tipe simpul.

### [Hapus-AzServiceFabricNode](Remove-AzServiceFabricNode.md)
Hapus node dari tipe simpul tertentu dari kluster.

### [Remove-AzServiceFabricNodeType](Remove-AzServiceFabricNodeType.md)
Hapus tipe node lengkap dari kluster.

### [Hapus-AzServiceFabricService](Remove-AzServiceFabricService.md)
Hapus layanan dari kluster. Hanya mendukung layanan arm yang disebarkan.

### [Remove-AzServiceFabricSetting](Remove-AzServiceFabricSetting.md)
Hapus satu atau beberapa pengaturan Service Fabric dari kluster.

### [Mulai Ulang-AzServiceFabricManagedNodeType](Restart-AzServiceFabricManagedNodeType.md)
Mulai ulang node tertentu dari tipe simpul.

### [Set-AzServiceFabricManagedCluster](Set-AzServiceFabricManagedCluster.md)
Atur properti sumber daya kluster.

### [Set-AzServiceFabricManagedClusterApplication](Set-AzServiceFabricManagedClusterApplication.md)
Perbarui aplikasi yang dikelola kain layanan. Hal ini memungkinkan untuk memperbarui parameter aplikasi dan/atau memutakhirkan versi tipe aplikasi yang akan memicu pemutakhiran aplikasi atau hanya pembaruan konfigurasi lainnya. Hanya mendukung aplikasi arm yang digunakan.

### [Set-AzServiceFabricManagedClusterApplicationType](Set-AzServiceFabricManagedClusterApplicationType.md)
Perbarui jenis aplikasi yang dikelola kain layanan. Ini memungkinkan Anda memperbarui tag. Hanya mendukung ARM tipe aplikasi yang digunakan.

### [Set-AzServiceFabricManagedClusterApplicationTypeVersion](Set-AzServiceFabricManagedClusterApplicationTypeVersion.md)
Perbarui versi tipe aplikasi yang dikelola kain layanan. Ini memungkinkan Anda memperbarui tag dan Url paket. Hanya mendukung ARM versi tipe aplikasi yang digunakan.

### [Set-AzServiceFabricManagedClusterService](Set-AzServiceFabricManagedClusterService.md)
Memperbarui layanan terkelola dari kluster. Hanya mendukung layanan arm yang disebarkan.

### [Set-AzServiceFabricManagedNodeType](Set-AzServiceFabricManagedNodeType.md)
Mengatur properti sumber daya tipe node atau menjalankan tindakan reimage pada ndes tertentu dari tipe node dengan parameter -Reimage.

### [Set-AzServiceFabricSetting](Set-AzServiceFabricSetting.md)
Tambahkan atau perbarui satu atau beberapa pengaturan Service Fabric ke kluster.

### [Set-AzServiceFabricUpgradeType](Set-AzServiceFabricUpgradeType.md)
Ubah tipe pemutakhiran Service Fabric kluster.

### [Pembaruan-AzServiceFabricAplikasi](Update-AzServiceFabricApplication.md)
Perbarui aplikasi kain layanan. Hal ini memungkinkan untuk memperbarui parameter aplikasi dan/atau memutakhirkan versi tipe aplikasi yang akan memicu pemutakhiran aplikasi. Hanya mendukung aplikasi arm yang digunakan.

### [Pembaruan-AzServiceFabricDurability](Update-AzServiceFabricDurability.md)
Memperbarui tingkat ketahanan atau VmSku dari tipe node dalam kluster.

### [Update-AzServiceFabricNodeType](Update-AzServiceFabricNodeType.md)
Memperbarui tipe simpul dalam kluster.

### [Pembaruan-AzServiceFabricReliabilitas](Update-AzServiceFabricReliability.md)
Perbarui tingkat keandalan tipe node utama dalam kluster.

### [Update-AzServiceFabricVmImage](Update-AzServiceFabricVmImage.md)
Perbarui pengaturan vmImage sumber daya kluster yang memetakan paket runtime yang sesuai untuk dikirim berdasarkan sistem operasi target.

