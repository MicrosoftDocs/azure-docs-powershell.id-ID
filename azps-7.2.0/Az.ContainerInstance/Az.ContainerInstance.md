---
Module Name: Az.ContainerInstance
Module Guid: ddf74844-4a25-4263-8a5c-f27979292e4e
Download Help Link: https://docs.microsoft.com/powershell/module/az.containerinstance
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Az.ContainerInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Az.ContainerInstance.md
ms.openlocfilehash: d52c63c72d810ee1a6679cdae7f25cf3b3cc951a
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138258892"
---
# Az.ContainerInstance Module
## Deskripsi
Microsoft Azure PowerShell: Cmdlet ContainerInstance

## Cmdlet Az.ContainerInstance
### [Add-AzContainerInstanceOutput](Add-AzContainerInstanceOutput.md)
Lampirkan ke aliran output contoh wadah tertentu dalam grup sumber daya dan grup wadah yang ditentukan.

### [Get-AzContainerGroup](Get-AzContainerGroup.md)
Mendapatkan properti grup wadah yang ditentukan dalam langganan dan grup sumber daya yang ditentukan.
Operasi mengembalikan properti setiap grup wadah termasuk wadah, kredensial registri gambar, kebijakan mulai ulang, tipe alamat IP, tipe OS, status, dan volume.

### [Get-AzContainerInstanceCachedImage](Get-AzContainerInstanceCachedImage.md)
Dapatkan daftar gambar singgahan di tipe OS tertentu untuk langganan di suatu kawasan.

### [Get-AzContainerInstanceCapability](Get-AzContainerInstanceCapability.md)
Dapatkan daftar kapabilitas CPU/memori/GPU di suatu wilayah.

### [Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint](Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint.md)
Mendapatkan semua dependensi jaringan untuk grup wadah ini untuk memungkinkan kontrol penuh atas pengaturan dan konfigurasi jaringan.
Untuk grup wadah, ini akan selalu menjadi daftar kosong.

### [Get-AzContainerInstanceLog](Get-AzContainerInstanceLog.md)
Dapatkan log untuk contoh wadah yang ditentukan dalam grup sumber daya dan grup wadah yang ditentukan.

### [Get-AzContainerInstanceUsage](Get-AzContainerInstanceUsage.md)
Dapatkan penggunaan untuk langganan

### [Invoke-AzContainerInstanceCommand](Invoke-AzContainerInstanceCommand.md)
Menjalankan perintah untuk contoh wadah tertentu dalam grup sumber daya dan grup wadah yang ditentukan.

### [New-AzContainerGroup](New-AzContainerGroup.md)
Membuat atau memperbarui grup wadah dengan konfigurasi tertentu.

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
Membuat objek dalam memori untuk Wadah

### [New-AzContainerInstancePortObject](New-AzContainerInstancePortObject.md)
Membuat objek dalam memori untuk ContainerPort

### [New-AzContainerInstanceVolumeMountObject](New-AzContainerInstanceVolumeMountObject.md)
Membuat objek dalam memori untuk Jumlah Volume

### [Remove-AzContainerGroup](Remove-AzContainerGroup.md)
Hapus grup wadah tertentu dalam langganan dan grup sumber daya yang ditentukan.
Operasi tidak menghapus sumber daya lain yang disediakan oleh pengguna, seperti volume.

### [Restart-AzContainerGroup](Restart-AzContainerGroup.md)
Memulai ulang semua wadah dalam grup wadah di tempat.
Jika gambar kontainer memiliki pembaruan, gambar baru akan diunduh.

### [Start-AzContainerGroup](Start-AzContainerGroup.md)
Memulai semua wadah dalam grup wadah.
Hitung sumber daya akan dialokasikan dan tagihan akan dimulai.

### [Stop-AzContainerGroup](Stop-AzContainerGroup.md)
Menghentikan semua wadah dalam grup wadah.
Hitung sumber daya yang akan ditangani, lalu tagihan akan berhenti.

### [Update-AzContainerGroup](Update-AzContainerGroup.md)
Memperbarui tag grup wadah dengan nilai tertentu.

