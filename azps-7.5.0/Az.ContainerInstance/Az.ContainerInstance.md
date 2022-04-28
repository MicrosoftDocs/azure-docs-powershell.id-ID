---
Module Name: Az.ContainerInstance
Module Guid: ddf74844-4a25-4263-8a5c-f27979292e4e
Download Help Link: https://docs.microsoft.com/powershell/module/az.containerinstance
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Az.ContainerInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Az.ContainerInstance.md
ms.openlocfilehash: b115771726c758d8c6300f110b7ae8634c466e54
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144219551"
---
# Modul Az.ContainerInstance
## Deskripsi
Microsoft Azure PowerShell: Cmdlet ContainerInstance

## Cmdlet Az.ContainerInstance
### [Add-AzContainerInstanceOutput](Add-AzContainerInstanceOutput.md)
Lampirkan ke aliran output instans kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

### [Get-AzContainerGroup](Get-AzContainerGroup.md)
Mendapatkan properti grup kontainer yang ditentukan dalam langganan dan grup sumber daya yang ditentukan.
Operasi mengembalikan properti setiap grup kontainer termasuk kontainer, kredensial registri gambar, kebijakan hidupkan ulang, jenis alamat IP, jenis OS, status, dan volume.

### [Get-AzContainerInstanceCachedImage](Get-AzContainerInstanceCachedImage.md)
Dapatkan daftar gambar yang di-cache pada jenis OS tertentu untuk langganan di suatu wilayah.

### [Get-AzContainerInstanceCapability](Get-AzContainerInstanceCapability.md)
Dapatkan daftar kemampuan CPU/memori/GPU suatu wilayah.

### [Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint](Get-AzContainerInstanceContainerGroupOutboundNetworkDependencyEndpoint.md)
Mendapatkan semua dependensi jaringan untuk grup kontainer ini untuk memungkinkan kontrol penuh pengaturan dan konfigurasi jaringan.
Untuk grup kontainer, ini akan selalu menjadi daftar kosong.

### [Get-AzContainerInstanceLog](Get-AzContainerInstanceLog.md)
Dapatkan log untuk instans kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

### [Get-AzContainerInstanceUsage](Get-AzContainerInstanceUsage.md)
Mendapatkan penggunaan untuk langganan

### [Invoke-AzContainerInstanceCommand](Invoke-AzContainerInstanceCommand.md)
Menjalankan perintah untuk instans kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

### [New-AzContainerGroup](New-AzContainerGroup.md)
Membuat atau memperbarui grup kontainer dengan konfigurasi tertentu.

### [New-AzContainerGroupImageRegistryCredentialObject](New-AzContainerGroupImageRegistryCredentialObject.md)
Membuat objek dalam memori untuk ImageRegistryCredential

### [New-AzContainerGroupPortObject](New-AzContainerGroupPortObject.md)
Membuat objek dalam memori untuk Port

### [New-AzContainerGroupVolumeObject](New-AzContainerGroupVolumeObject.md)
Buat objek dalam memori untuk Volume.

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

### [Remove-AzContainerGroup](Remove-AzContainerGroup.md)
Hapus grup kontainer yang ditentukan dalam langganan dan grup sumber daya yang ditentukan.
Operasi ini tidak menghapus sumber daya lain yang disediakan oleh pengguna, seperti volume.

### [Mulai ulang-AzContainerGroup](Restart-AzContainerGroup.md)
Memulai ulang semua kontainer dalam grup kontainer di tempatnya.
Jika gambar kontainer memiliki pembaruan, gambar baru akan diunduh.

### [Start-AzContainerGroup](Start-AzContainerGroup.md)
Memulai semua kontainer dalam grup kontainer.
Sumber daya komputasi akan dialokasikan dan penagihan akan dimulai.

### [Stop-AzContainerGroup](Stop-AzContainerGroup.md)
Menghentikan semua kontainer dalam grup kontainer.
Sumber daya komputasi akan dibatalkan alokasinya dan penagihan akan dihentikan.

### [Update-AzContainerGroup](Update-AzContainerGroup.md)
Memperbarui tag grup kontainer dengan nilai yang ditentukan.

