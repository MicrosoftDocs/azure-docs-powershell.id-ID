---
Module Name: Az.ResourceMover
Module Guid: 97d87543-8eef-4574-a70d-7317ec4abe54
Download Help Link: https://docs.microsoft.com/powershell/module/az.resourcemover
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Az.ResourceMover.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Az.ResourceMover.md
ms.openlocfilehash: 105b55c63901254d46e813a296c4a0bdc1b8ddfb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141990594"
---
# Modul Az.ResourceMover
## Deskripsi
Microsoft Azure PowerShell: cmdlet ResourceMover

## Cmdlet Az.ResourceMover
### [Add-AzResourceMoverMoveResource](Add-AzResourceMoverMoveResource.md)
Membuat atau memperbarui Pindahkan Sumber Daya dalam kumpulan pemindahan.

### [Get-AzResourceMoverMoveCollection](Get-AzResourceMoverMoveCollection.md)
Mendapatkan koleksi perpindahan.

### [Get-AzResourceMoverMoveResource](Get-AzResourceMoverMoveResource.md)
Mendapatkan Pindahkan Sumber Daya.

### [Get-AzResourceMoverRequiredForResources](Get-AzResourceMoverRequiredForResources.md)
Daftar sumber daya pemindahan tempat sumber daya lengan diperlukan.

### [Get-AzResourceMoverUnresolvedDependency](Get-AzResourceMoverUnresolvedDependency.md)
Mendapatkan daftar dependensi yang belum diatasi.

### [Invoke-AzResourceMoverBulkRemove](Invoke-AzResourceMoverBulkRemove.md)
Menghapus kumpulan sumber daya pemindahan yang disertakan dalam isi permintaan dari pemindahan koleksi.
Orkestrasi dilakukan melalui layanan.
Untuk membantu pengguna prasyarat operasi klien dapat menghubungi operasi dengan properti validateOnly diatur ke true.

### [Invoke-AzResourceMoverCommit](Invoke-AzResourceMoverCommit.md)
Melakukan kumpulan sumber daya yang disertakan dalam isi permintaan.
Operasi komit dipicu pada moveResources dalam perpindahanState 'CommitPending' atau 'CommitFailed', pada penyelesaian yang berhasil, moveResource moveState melakukan transisi ke Komitmen.
Untuk membantu pengguna prasyarat operasi klien dapat menghubungi operasi dengan properti validateOnly diatur ke true.

### [Invoke-AzResourceMoverDiscard](Invoke-AzResourceMoverDiscard.md)
Membuang kumpulan sumber daya yang disertakan dalam isi permintaan.
Operasi buang dipicu pada moveResources dalam moveState 'CommitPending' atau 'DiscardFailed', pada penyelesaian yang berhasil, moveResource moveState melakukan transisi ke MovePending.
Untuk membantu pengguna prasyarat operasi klien dapat menghubungi operasi dengan properti validateOnly diatur ke true.

### [Invoke-AzResourceMoverInitiateMove](Invoke-AzResourceMoverInitiateMove.md)
Memindahkan kumpulan sumber daya yang disertakan dalam isi permintaan.
Operasi pemindahan dipicu setelah moveResources berada dalam perpindahanState 'MovePending' atau 'MoveFailed', pada penyelesaian yang berhasil, moveResource moveState melakukan transisi ke CommitPending.
Untuk membantu pengguna prasyarat operasi klien dapat menghubungi operasi dengan properti validateOnly diatur ke true.

### [Invoke-AzResourceMoverPrepare](Invoke-AzResourceMoverPrepare.md)
Memulai persiapan untuk kumpulan sumber daya yang disertakan dalam isi permintaan.
Operasi persiapan berada pada moveResources yang berada dalam perpindahanState 'PreparePending' atau 'PrepareFailed', pada penyelesaian yang berhasil, moveResource moveState melakukan transisi ke MovePending.
Untuk membantu pengguna prasyarat operasi klien dapat menghubungi operasi dengan properti validateOnly diatur ke true.

### [New-AzResourceMoverMoveCollection](New-AzResourceMoverMoveCollection.md)
Membuat atau memperbarui koleksi perpindahan.

### [Remove-AzResourceMoverMoveCollection](Remove-AzResourceMoverMoveCollection.md)
Menghapus koleksi pemindahan.

### [Hapus-AzResourceMoverMoveResource](Remove-AzResourceMoverMoveResource.md)
Menghapus Pindahkan Sumber Daya dari kumpulan pemindahan.

### [Resolve-AzResourceMoverMoveCollectionDependency](Resolve-AzResourceMoverMoveCollectionDependency.md)
Menghitung, menyelesaikan, dan memvalidasi dependensi dari moveResources dalam koleksi pemindahan.

