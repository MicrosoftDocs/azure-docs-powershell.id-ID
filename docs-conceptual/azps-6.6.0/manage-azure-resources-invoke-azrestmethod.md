---
title: Mengelola sumber daya Azure dengan Invoke-AzRestMethod
description: Cara menggunakan Azure PowerShell untuk mengelola sumber daya dengan cmdlet Invoke-AzRestMethod.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/02/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 4ba6940e0fc5ac49b3f11860cd1ba24adb6995f2
ms.sourcegitcommit: b7ef209e489945ce397bbbba2c5f34fa6b2ca22e
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429517"
---
# <a name="manage-azure-resources-with-invoke-azrestmethod"></a>Mengelola sumber daya Azure dengan Invoke-AzRestMethod

[Invoke-AzRestMethod](/powershell/module/az.accounts/invoke-azrestmethod) adalah cmdlet Azure PowerShell yang diperkenalkan di modul Az PowerShell versi 4.4.0. Cmdlet ini memungkinkan Anda membuat permintaan HTTP kustom ke titik akhir Azure Resource Management (ARM) dengan konteks Az.

Cmdlet ini berguna saat Anda ingin mengelola layanan Azure untuk fitur yang belum tersedia di modul Az PowerShell.

## <a name="how-to-use-invoke-azrestmethod"></a>Cara menggunakan Invoke-AzRestMethod

Misalnya, Anda dapat mengizinkan akses ke Azure Container Registry (ACR) hanya untuk jaringan tertentu atau menolak akses publik. Sejak modul Az PowerShell versi 4.5.0, fitur tersebut belum tersedia di [modul Az.ContainerRegistry Powershell](/powershell/module/Az.ContainerRegistry/). Namun, fitur tersebut dapat dikelola untuk sementara dengan `Invoke-AzRestMethod`.

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

Untuk fleksibilitas maksimum, sebagian besar parameter `Invoke-AzRestMethod` bersifat opsional.
Namun, saat Anda mengelola sumber daya dalam grup sumber daya, kemungkinan besar Anda perlu memberikan ID lengkap ke sumber daya atau parameter seperti grup sumber daya, penyedia sumber daya, dan jenis sumber daya.

Parameter `ResourceType` dan `Name` dapat mengambil beberapa nilai saat menargetkan sumber daya yang memerlukan lebih dari satu nama. Misalnya, untuk memanipulasi pencarian yang tersimpan di ruang kerja Log Analytics, parameternya terlihat seperti contoh berikut: `-ResourceType @('workspaces', 'savedsearches') -Name @('my-la', 'my-search')`.

Menggunakan pemetaan berdasarkan posisi dalam array, cmdlet membangun sumber daya berikut: `Id:'/workspaces/my-la/savedsearches/my-search'`.

Parameter `APIVersion` memungkinkan Anda untuk menggunakan versi API tertentu, termasuk versi pratinjau. Versi API yang didukung untuk penyedia Azure Resource dapat ditemukan di repositori GitHub [azure-rest-api-specs](https://github.com/Azure/azure-rest-api-specs).

Anda dapat menemukan definisi ACR versi 2019-12-01-preview di lokasi berikut: [azure-rest-api-specs/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview/](https://github.com/Azure/azure-rest-api-specs/tree/master/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview).

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
Definisi spesifik untuk parameter publicNetworkAccess dapat ditemukan di [file JSON registri kontainer](https://github.com/Azure/azure-rest-api-specs/blob/2a9da9a79d0a7b74089567ec4f0289f3e0f31bec/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview/2019-12-01-preview/containerregistry.json) untuk versi API pratinjau 2019-12-01.

Untuk mengizinkan akses ke registri dari alamat IP tertentu saja, payload perlu dimodifikasi seperti dalam contoh berikut:

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

## <a name="comparison-to-get-azresource-new-azresource-and-remove-azresource"></a>Perbandingan antara Get-AzResource, New-AzResource, dan Remove-AzResource

Cmdlet `*-AzResource` memungkinkan Anda untuk menyesuaikan panggilan REST API ke Azure dengan menentukan jenis sumber daya, versi API, dan properti yang akan diperbarui. Namun, properti harus dibuat terlebih dahulu sebagai `PSObject`. Proses ini menambahkan tingkat kompleksitas dan mungkin menjadi lebih rumit.

`Invoke-AzRestMethod` menghadirkan cara mudah untuk mengelola sumber daya Azure. Seperti yang ditunjukkan pada contoh sebelumnya, Anda dapat membuat string JSON dan menggunakannya untuk menyesuaikan panggilan REST API tanpa harus membuat `PSObjects` terlebih dahulu.

Jika Anda sudah memahami cmdlet `*-AzResource`, Anda dapat terus menggunakannya. Kami tidak berencana untuk berhenti mendukungnya. Dengan `Invoke-AzRestMethod`, kami telah menambahkan cmdlet baru ke toolkit Anda.

## <a name="see-also"></a>Lihat juga

* [Mendapatkan-AzResource](/powershell/module/az.resources/get-azresource)
* [Baru-AzResource](/powershell/module/az.resources/new-azresource)
* [Remove-AzResource](/powershell/module/az.resources/remove-azresource)
