---
title: Mengelola sumber daya Azure Invoke-AzRestMethod
description: Cara menggunakan Azure PowerShell mengelola sumber daya dengan cmdlet Invoke-AzRestMethod cmdlet.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/27/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 70e1765576966390b5e403d6f8e42830e329d220
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429472"
---
# <a name="manage-azure-resources-with-invoke-azrestmethod"></a>Mengelola sumber daya Azure Invoke-AzRestMethod

[Invoke-AzConfigMethod](/powershell/module/az.accounts/invoke-azrestmethod) adalah cmdlet Azure PowerShell cmdlet yang diperkenalkan di Az PowerShell versi modul 4.4.0. Ini memungkinkan Anda untuk membuat permintaan HTTP kustom ke titik akhir Manajemen Sumber Daya Azure (ARM, Azure Resource Management) menggunakan konteks Az.

Cmdlet ini berguna saat Anda ingin mengelola layanan Azure untuk fitur yang belum tersedia dalam modul Az PowerShell.

## <a name="how-to-use-invoke-azrestmethod"></a>Cara menggunakan Invoke-AzRestMethod

Sebagai contoh, Anda dapat mengizinkan akses ke Azure Container Registry (ACR) hanya untuk jaringan tertentu atau menolak akses publik. Saat modul Az PowerShell versi 4.5.0, fitur tersebut belum tersedia dalam modul [PowerShell Az.ContainerRegistry](/powershell/module/Az.ContainerRegistry/). Namun, file ini dapat dikelola secara sementara dengan `Invoke-AzRestMethod` .

## <a name="using-invoke-azrestmethod-with-get-operations"></a>Menggunakan Invoke-AzRestMethod dengan operasi GET

Contoh berikut ini menunjukkan cara menggunakan `Invoke-AzRestMethod` cmdlet dengan operasi GET:

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

Untuk memungkinkan fleksibilitas maksimum, sebagian besar parameter untuk `Invoke-AzRestMethod` adalah opsional.
Namun, saat Anda mengelola sumber daya di dalam grup sumber daya, Anda kemungkinan besar harus menyediakan ID lengkap untuk sumber daya atau parameter seperti grup sumber daya, penyedia sumber daya, dan tipe sumber daya.

Parameter `ResourceType` dapat mengambil beberapa nilai saat menargetkan sumber daya yang memerlukan lebih dari satu `Name` nama. Misalnya, untuk memanipulasi pencarian yang disimpan dalam ruang kerja Analitik Log, parameter terlihat seperti contoh berikut: `-ResourceType @('workspaces', 'savedsearches') -Name @('my-la', 'my-search')` .

Dengan menggunakan pemetaan berdasarkan posisi dalam array, cmdlet menyusun sumber daya berikut: `Id:'/workspaces/my-la/savedsearches/my-search'` .

Parameter `APIVersion` ini memungkinkan Anda menggunakan versi API tertentu, termasuk melihat pratinjaunya. Versi API yang didukung untuk penyedia Sumber Daya Azure dapat ditemukan di spesifikasi [azure rest-api](https://github.com/Azure/azure-rest-api-specs) GitHub penyimpanan.

Anda dapat menemukan definisi ACR versi 2019-12-01-preview di lokasi berikut: [azure-rest-api-specification/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview/](https://github.com/Azure/azure-rest-api-specs/tree/master/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview).

## <a name="using-invoke-azrestmethod-with-patch-operations"></a>Menggunakan Invoke-AzRestMethod dengan operasi PATCH

Anda bisa menonaktifkan akses publik ke ACR yang sudah ada yang `myacr` dinamai di grup sumber daya menggunakan `myresourcegroup` `Invoke-AzRestMethod` cmdlet.

Untuk menonaktifkan akses jaringan publik, Anda perlu melakukan panggilan **PATCH** ke API yang mengubah nilai parameter seperti yang `publicNetwokAccess` diperlihatkan dalam contoh berikut ini:

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

`Payload`Properti tersebut merupakan string JSON yang memperlihatkan jalur properti yang akan dimodifikasi.

Semua parameter untuk API ini dijelaskan dalam file **spesifikasi api rest yang** terkait dengan API ini.
Definisi tertentu untuk parameter publicNetworkAccess dapat ditemukan dalam file JSON registri [wadah untuk versi pratinjau](https://github.com/Azure/azure-rest-api-specs/blob/2a9da9a79d0a7b74089567ec4f0289f3e0f31bec/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview/2019-12-01-preview/containerregistry.json) API 2019-12-01.

Untuk mengizinkan akses ke registri dari alamat IP tertentu saja, payload perlu dimodifikasi seperti yang diperlihatkan dalam contoh berikut:

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

## <a name="comparison-to-get-azresource-new-azresource-and-remove-azresource"></a>Perbandingan ke Get-AzResource, New-AzResource, dan Remove-AzResource

Cmdlets `*-AzResource` allow you to customize the REST API call to Azure by specifying the resource type, the API version, and the properties to be updated. Namun, properti perlu dibuat terlebih dahulu sebagai `PSObject` . Proses ini menambahkan tingkat kerumitan tambahan dan bisa dengan mudah menjadi rumit.

`Invoke-AzRestMethod` menawarkan cara sederhana untuk mengelola sumber daya Azure. Seperti yang diperlihatkan dalam contoh sebelumnya, Anda dapat membuat string JSON dan menggunakannya untuk mengustomisasi panggilan REST API tanpa harus membuat string JSON terlebih `PSObjects` lanjut.

Jika Anda sudah tidak asing dengan `*-AzResource` cmdlet, Anda bisa terus menggunakannya. Kami tidak memiliki rencana untuk berhenti mendukung mereka. Dengan `Invoke-AzRestMethod` , kami telah menambahkan cmdlet baru ke toolkit Anda.

## <a name="see-also"></a>Lihat Juga

* [Get-AzResource](/powershell/module/az.resources/get-azresource)
* [New-AzResource](/powershell/module/az.resources/new-azresource)
* [Remove-AzResource](/powershell/module/az.resources/remove-azresource)
