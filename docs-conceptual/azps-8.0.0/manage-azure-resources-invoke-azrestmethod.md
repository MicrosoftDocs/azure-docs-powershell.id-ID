---
description: Cara menggunakan Azure PowerShell untuk mengelola sumber daya dengan cmdlet Invoke-AzRestMethod.
ms.custom: devx-track-azurepowershell
ms.date: 05/24/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Mengelola sumber daya Azure dengan Invoke-AzRestMethod
ms.openlocfilehash: 9d37159cc8a4fc08aefe5b0576edd31bd818e06a
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145819271"
---
# <a name="manage-azure-resources-with-invoke-azrestmethod"></a>Mengelola sumber daya Azure dengan Invoke-AzRestMethod

[Invoke-AzRestMethod](/powershell/module/az.accounts/invoke-azrestmethod) adalah cmdlet Azure PowerShell yang diperkenalkan di modul Az PowerShell versi 4.4.0. Ini memungkinkan Anda untuk membuat permintaan HTTP kustom ke titik akhir Azure Resource Management (ARM) menggunakan konteks Az.

Cmdlet ini berguna saat Anda ingin mengelola layanan Azure untuk fitur yang belum tersedia di modul Az PowerShell.

## <a name="how-to-use-invoke-azrestmethod"></a>Cara menggunakan Invoke-AzRestMethod

Misalnya, Anda dapat mengizinkan akses ke Azure Container Registry (ACR) hanya untuk jaringan tertentu atau menolak akses publik. Pada modul Az PowerShell versi 4.5.0, fitur itu belum tersedia di [modul Az.ContainerRegistry Powershell](/powershell/module/Az.ContainerRegistry/). Namun, ini dapat dikelola untuk sementara dengan `Invoke-AzRestMethod`.

## <a name="using-invoke-azrestmethod-with-get-operations"></a>Menggunakan Invoke-AzRestMethod dengan operasi GET

Contoh berikut menunjukkan cara menggunakan cmdlet `Invoke-AzRestMethod` dengan operasi GET:

```azurepowershell-interactive
$getParams = @{
  ResourceGroupName = 'myresourcegroup'
  ResourceProviderName = 'Microsoft.ContainerRegistry'
  ResourceType = 'registries'
  Name = 'myacr'
  ApiVersion = '2019-12-01-preview'
  Method = 'GET'
}
Invoke-AzRestMethod @getParams
```

Untuk memungkinkan fleksibilitas maksimum, sebagian besar parameter `Invoke-AzRestMethod` bersifat opsional.
Namun, saat Anda mengelola sumber daya dalam grup sumber daya, kemungkinan besar Anda perlu memberikan ID lengkap ke sumber daya atau parameter seperti grup sumber daya, penyedia sumber daya, dan jenis sumber daya.

Parameter `ResourceType` dan `Name` dapat mengambil beberapa nilai saat menargetkan sumber daya yang memerlukan lebih dari satu nama. Misalnya, untuk memanipulasi pencarian yang tersimpan di ruang kerja Analitik Log, parameternya terlihat seperti contoh berikut: `-ResourceType @('workspaces', 'savedsearches') -Name @('my-la', 'my-search')`.

Menggunakan pemetaan berdasarkan posisi dalam array, cmdlet membangun sumber daya berikut: `Id:'/workspaces/my-la/savedsearches/my-search'`.

Parameter `APIVersion` memungkinkan Anda untuk menggunakan versi API tertentu, termasuk yang pratinjau. Versi API yang didukung untuk penyedia Sumber Daya Azure dapat ditemukan di repositori GitHub [azure-rest-api-specs](https://github.com/Azure/azure-rest-api-specs).

Anda dapat menemukan definisi untuk ACR versi 2019-12-01-preview di lokasi berikut: [azure-rest-api-specs/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview/](https://github.com/Azure/azure-rest-api-specs/tree/master/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview).

## <a name="using-invoke-azrestmethod-with-patch-operations"></a>Menggunakan Invoke-AzRestMethod dengan operasi PATCH

Anda dapat menonaktifkan akses publik ke ACR yang ada yang bernama `myacr` dalam grup sumber daya `myresourcegroup` menggunakan cmdlet `Invoke-AzRestMethod`.

Untuk menonaktifkan akses jaringan publik, Anda perlu melakukan panggilan **PATCH** ke API yang mengubah nilai parameter `publicNetwokAccess` seperti yang ditunjukkan pada contoh berikut:

```azurepowershell-interactive
$patchParams = @{
  ResourceGroupName = 'myresourcegroup'
  Name = 'myacr'
  ResourceProviderName = 'Microsoft.ContainerRegistry'
  ResourceType = 'registries'
  ApiVersion = '2019-12-01-preview'
  Payload = '{ "properties": {
     "publicNetworkAccess": "Disabled"
     } }'
  Method = 'PATCH'
}
Invoke-AzRestMethod @patchParams
```

Properti `Payload` adalah string JSON yang menunjukkan jalur properti yang akan dimodifikasi.

Semua parameter untuk API ini dijelaskan dalam file **rest-api-spec** yang terkait dengan API ini.
Definisi spesifik untuk parameter publicNetworkAccess dapat ditemukan di [file JSON registri kontainer](https://github.com/Azure/azure-rest-api-specs/blob/2a9da9a79d0a7b74089567ec4f0289f3e0f31bec/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview/2019-12-01-preview/containerregistry.json) untuk versi pratinjau API 2019-12-01.

Untuk mengizinkan akses ke registri dari alamat IP tertentu saja, payload perlu dimodifikasi seperti yang ditunjukkan dalam contoh berikut:

```azurepowershell-interactive
$specificIpParams = @{
  ResourceGroupName = 'myresourcegroup'
  Name = 'myacr'
  ResourceProviderName = 'Microsoft.ContainerRegistry'
  ResourceType = 'registries'
  ApiVersion = '2019-12-01-preview'
  Payload = '{ "properties": {
      "networkRuleSet": {
      "defaultAction": "Deny",
      "ipRules": [ {
         "action": "Allow",
         "value": "24.22.123.123"
         } ]
      }
  } }'
  -Method = 'PATCH'
}
Invoke-AzRestMethod @specificIpParams
```

## <a name="comparison-to-get-azresource-new-azresource-and-remove-azresource"></a>Perbandingan dengan Get-AzResource, New-AzResource, dan Remove-AzResource

Cmdlet `*-AzResource` memungkinkan Anda untuk menyesuaikan panggilan REST API ke Azure dengan menentukan jenis sumber daya, versi API, dan properti yang akan diperbarui. Namun, properti harus dibuat terlebih dahulu sebagai `PSObject`. Proses ini menambahkan tingkat kompleksitas tambahan dan dapat dengan mudah menjadi rumit.

`Invoke-AzRestMethod` menawarkan cara sederhana untuk mengelola sumber daya Azure. Seperti yang ditunjukkan pada contoh sebelumnya, Anda dapat membuat string JSON dan menggunakannya untuk menyesuaikan panggilan REST API tanpa harus membuat ulang `PSObjects`.

Jika Anda sudah terbiasa dengan cmdlet `*-AzResource`, Anda dapat terus menggunakannya. Kami tidak berencana untuk berhenti mendukungnya. Dengan `Invoke-AzRestMethod`, kami telah menambahkan cmdlet baru ke toolkit Anda.

## <a name="see-also"></a>Lihat juga

- [Mendapatkan-AzResource](/powershell/module/az.resources/get-azresource)
- [Baru-AzResource](/powershell/module/az.resources/new-azresource)
- [Remove-AzResource](/powershell/module/az.resources/remove-azresource)
