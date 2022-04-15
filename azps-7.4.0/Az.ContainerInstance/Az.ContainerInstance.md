---
Module Name: Az.ContainerInstance
Module Guid: ddf74844-4a25-4263-8a5c-f27979292e4e
Download Help Link: https://docs.microsoft.com/powershell/module/az.containerinstance
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Az.ContainerInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Az.ContainerInstance.md
ms.openlocfilehash: d52c63c72d810ee1a6679cdae7f25cf3b3cc951a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142434011"
---
# Modul Az.ContainerInstance
## Deskripsi
Microsoft Azure PowerShell: cmdlet ContainerInstance

## Cmdlet Az.ContainerInstance
### [Add-AzContainerInstanceOutput](Add-AzContainerInstanceOutput.md)
Lampirkan ke aliran output instans kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

### [Get-AzContainerGroup](Get-AzContainerGroup.md)
Mendapatkan properti grup kontainer yang ditentukan dalam grup sumber daya dan langganan tertentu.
Operasi mengembalikan properti dari setiap grup kontainer termasuk wadah, kredensial registri gambar, kebijakan mulai ulang, tipe alamat IP, tipe OS, status, dan volume.

### [Get-AzContainerInstanceCachedImage](Get-AzContainerInstanceCachedImage.md)
Dapatkan daftar gambar singgahan pada tipe OS tertentu untuk langganan di suatu kawasan.

### [Get-AzContainerInstanceCapability](Get-AzContainerInstanceCapability.md)
Dapatkan daftar kapabilitas CPU/memori/GPU suatu kawasan.

### [Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint](Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint.md)
Mendapatkan semua dependensi jaringan untuk grup kontainer ini untuk memungkinkan kontrol penuh pengaturan dan konfigurasi jaringan.
Untuk grup wadah, ini akan selalu menjadi daftar kosong.

### [Get-AzContainerInstanceLog](Get-AzContainerInstanceLog.md)
Dapatkan log untuk contoh kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

### [Get-AzContainerInstanceUsage](Get-AzContainerInstanceUsage.md)
Dapatkan penggunaan untuk langganan

### [Invoke-AzContainerInstanceCommand](Invoke-AzContainerInstanceCommand.md)
Menjalankan perintah untuk contoh kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

### [New-AzContainerGroup](New-AzContainerGroup.md)
Membuat atau memperbarui grup kontainer dengan konfigurasi tertentu.

### [New-AzContainerGroupImageRegistryCredentialObject](New-AzContainerGroupImageRegistryCredentialObject.md)
Membuat objek dalam memori untuk ImageRegistryCredential

### [New-AzContainerGroupPortObject](New-AzContainerGroupPortObject.md)
Membuat objek dalam memori untuk Port

### [New-AzContainerGroupVolumeObject](New-AzContainerGroupVolumeObject.md)
Membuat objek dalam memori untuk Volume

### [New-AzContainerInstanceEnvironmentVariableObject](New-AzContainerInstanceEnvironmentVariableObject.md)
Membuat objek dalam memori untuk EnvironmentVariable

### [New-AzContainerInstanceHttpHeaderObject](New-AzContainerInstanceHttpHeaderObject.md)
Membuat objek dalam memori untuk HttpHeader

### [New-AzContainerInstanceInitDefinitionObject](New-AzContainerInstanceInitDefinitionObject.md)
Membuat objek dalam memori untuk InitContainerDefinition

### [New-AzContainerInstanceObject](New-AzContainerInstanceObject.md)
Membuat objek dalam memori untuk Kontainer

### [New-AzContainerInstancePortObject](New-AzContainerInstancePortObject.md)
Membuat objek dalam memori untuk ContainerPort

### [New-AzContainerInstanceVolumeMountObject](New-AzContainerInstanceVolumeMountObject.md)
Membuat objek dalam memori untuk VolumeMount

### [Hapus-AzContainerGroup](Remove-AzContainerGroup.md)
Hapus grup kontainer tertentu dalam grup sumber daya dan langganan tertentu.
Operasi ini tidak menghapus sumber daya lain yang disediakan oleh pengguna, seperti volume.

### [Mulai ulang-AzContainerGroup](Restart-AzContainerGroup.md)
Mulai ulang semua wadah dalam grup wadah di tempatnya.
Jika gambar kontainer memiliki pembaruan, gambar baru akan diunduh.

### [Start-AzContainerGroup](Start-AzContainerGroup.md)
Memulai semua wadah dalam grup wadah.
Sumber daya komputasi akan dialokasikan dan tagihan akan dimulai.

### [Stop-AzContainerGroup](Stop-AzContainerGroup.md)
Menghentikan semua wadah dalam grup wadah.
Sumber daya komputasi akan ditangani dan penagihan akan berhenti.

### [Update-AzContainerGroup](Update-AzContainerGroup.md)
Memperbarui tag grup penampung dengan nilai yang ditentukan.

