---
Module Name: Az.ResourceMover
Module Guid: 97d87543-8eef-4574-a70d-7317ec4abe54
Download Help Link: https://docs.microsoft.com/powershell/module/az.resourcemover
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Az.ResourceMover.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Az.ResourceMover.md
ms.openlocfilehash: 105b55c63901254d46e813a296c4a0bdc1b8ddfb
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144237867"
---
# Modul Az.ResourceMover
## Deskripsi
Microsoft Azure PowerShell: Cmdlet ResourceMover

## Cmdlet Az.ResourceMover
### [Add-AzResourceMoverMoveResource](Add-AzResourceMoverMoveResource.md)
Membuat atau memperbarui Pindahkan Sumber Daya dalam kumpulan pemindahan.

### [Get-AzResourceMoverMoveCollection](Get-AzResourceMoverMoveCollection.md)
Mendapatkan koleksi pemindahan.

### [Get-AzResourceMoverMoveResource](Get-AzResourceMoverMoveResource.md)
Mendapatkan Sumber Daya Pemindahan.

### [Get-AzResourceMoverRequiredForResources](Get-AzResourceMoverRequiredForResources.md)
Daftar sumber daya pemindahan tempat sumber daya arm diperlukan.

### [Get-AzResourceMoverUnresolvedDependency](Get-AzResourceMoverUnresolvedDependency.md)
Mendapatkan daftar dependensi yang belum terselesaikan.

### [Invoke-AzResourceMoverBulkRemove](Invoke-AzResourceMoverBulkRemove.md)
Menghapus kumpulan sumber daya pemindahan yang disertakan dalam isi permintaan dari kumpulan pemindahan.
Orkestrasi dilakukan oleh layanan.
Untuk membantu pengguna untuk prasyarat operasi, klien dapat memanggil operasi dengan properti validateOnly diatur ke true.

### [Invoke-AzResourceMoverCommit](Invoke-AzResourceMoverCommit.md)
Menerapkan set sumber daya yang disertakan dalam isi permintaan.
Operasi penerapan dipicu pada moveResources di moveState 'CommitPending' atau 'CommitFailed', pada penyelesaian yang berhasil, moveResource moveState melakukan transisi ke Penerapan.
Untuk membantu pengguna untuk prasyarat operasi, klien dapat memanggil operasi dengan properti validateOnly diatur ke true.

### [Invoke-AzResourceMoverDiscard](Invoke-AzResourceMoverDiscard.md)
Membuang set sumber daya yang disertakan dalam isi permintaan.
Operasi buang dipicu pada moveResources di moveState 'CommitPending' atau 'DiscardFailed', pada penyelesaian yang berhasil, moveResource moveState melakukan transisi ke MovePending.
Untuk membantu pengguna untuk prasyarat operasi, klien dapat memanggil operasi dengan properti validateOnly diatur ke true.

### [Invoke-AzResourceMoverInitiateMove](Invoke-AzResourceMoverInitiateMove.md)
Memindahkan set sumber daya yang disertakan dalam isi permintaan.
Operasi pemindahan dipicu setelah moveResources berada di moveState 'MovePending' atau 'MoveFailed', pada penyelesaian yang berhasil, moveResource moveState melakukan transisi ke CommitPending.
Untuk membantu pengguna untuk prasyarat operasi, klien dapat memanggil operasi dengan properti validateOnly diatur ke true.

### [Invoke-AzResourceMoverPrepare](Invoke-AzResourceMoverPrepare.md)
Memulai persiapan untuk set sumber daya yang disertakan dalam isi permintaan.
Operasi persiapan ada di moveResources yang berada di moveState 'PreparePending' atau 'PrepareFailed', pada penyelesaian yang berhasil, moveResource moveState melakukan transisi ke MovePending.
Untuk membantu pengguna untuk prasyarat operasi, klien dapat memanggil operasi dengan properti validateOnly diatur ke true.

### [New-AzResourceMoverMoveCollection](New-AzResourceMoverMoveCollection.md)
Membuat atau memperbarui koleksi pemindahan.

### [Remove-AzResourceMoverMoveCollection](Remove-AzResourceMoverMoveCollection.md)
Menghapus kumpulan pemindahan.

### [Remove-AzResourceMoverMoveResource](Remove-AzResourceMoverMoveResource.md)
Menghapus Pindahkan Sumber Daya dari kumpulan pemindahan.

### [Resolve-AzResourceMoverMoveCollectionDependency](Resolve-AzResourceMoverMoveCollectionDependency.md)
Menghitung, menyelesaikan, dan memvalidasi dependensi moveResources dalam kumpulan pemindahan.

