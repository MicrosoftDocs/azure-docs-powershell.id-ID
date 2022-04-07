---
Module Name: Az.ResourceMover
Module Guid: 97d87543-8eef-4574-a70d-7317ec4abe54
Download Help Link: https://docs.microsoft.com/powershell/module/az.resourcemover
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Az.ResourceMover.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Az.ResourceMover.md
ms.openlocfilehash: 105b55c63901254d46e813a296c4a0bdc1b8ddfb
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140178662"
---
# Az.ResourceMover Module
## Deskripsi
Microsoft Azure PowerShell: Cmdlet ResourceMover

## Cmdlet Az.ResourceMover
### [Add-AzResourceMoverMoveResource](Add-AzResourceMoverMoveResource.md)
Membuat atau memperbarui Sumber Daya Pemindahan dalam kumpulan pemindahan.

### [Get-AzResourceMoverMoveCollection](Get-AzResourceMoverMoveCollection.md)
Dapatkan koleksi untuk dipindahkan.

### [Get-AzResourceMoverMoveResource](Get-AzResourceMoverMoveResource.md)
Mendapatkan Pindahkan Sumber Daya.

### [Get-AzResourceMoverRequiredForResources](Get-AzResourceMoverRequiredForResources.md)
Daftar sumber daya pemindahan yang diperlukan oleh sebuah sumber daya.

### [Get-AzResourceMoverUnresolvedDependency](Get-AzResourceMoverUnresolvedDependency.md)
Mendapatkan daftar dependensi yang belum diatasi.

### [Invoke-AzResourceMoverBulkRemove](Invoke-AzResourceMoverBulkRemove.md)
Menghapus kumpulan sumber daya pemindahan yang disertakan dalam badan permintaan dari kumpulan pemindahan.
The orchestration is done by service.
Untuk membantu pengguna agar prasyarat operasi klien bisa memanggil operasi dengan properti validateOnly yang diatur ke true.

### [Invoke-AzResourceMoverCommit](Invoke-AzResourceMoverCommit.md)
Melakukan kumpulan sumber daya yang disertakan dalam badan permintaan.
Operasi melakukan dipicu pada moveResources di moveState 'CommitPending' atau 'CommitFailed', pada penyelesaian moveResource moveState yang berhasil melakukan transisi ke Committed.
Untuk membantu pengguna agar prasyarat operasi klien bisa memanggil operasi dengan properti validateOnly yang diatur ke true.

### [Invoke-AzResourceMoverDiscard](Invoke-AzResourceMoverDiscard.md)
Membuang kumpulan sumber daya yang disertakan dalam badan permintaan.
Operasi buang dipicu pada moveResources di moveState 'CommitPending' atau 'DiscardFailed', setelah berhasil menyelesaikan moveResource moveState melakukan transisi ke MovePending.
Untuk membantu pengguna agar prasyarat operasi klien bisa memanggil operasi dengan properti validateOnly yang diatur ke true.

### [Invoke-AzResourceMoverInitiateMove](Invoke-AzResourceMoverInitiateMove.md)
Memindahkan kumpulan sumber daya yang disertakan dalam badan permintaan.
Operasi perpindahan dipicu setelah moveResources berada di 'MovePending' atau 'MoveFailed', setelah moveResource moveState melakukan transisi ke CommitPending.
Untuk membantu pengguna agar prasyarat operasi klien bisa memanggil operasi dengan properti validateOnly yang diatur ke true.

### [Invoke-AzResourceMoverPrepare](Invoke-AzResourceMoverPrepare.md)
Memulai persiapan untuk kumpulan sumber daya yang disertakan dalam badan permintaan.
Operasi persiapan berada pada moveResources yang berada di moveState 'PreparePending' atau 'PrepareFailed', setelah selesai, moveResource moveState melakukan transisi ke MovePending.
Untuk membantu pengguna agar prasyarat operasi klien bisa memanggil operasi dengan properti validateOnly yang diatur ke true.

### [New-AzResourceMoverMoveCollection](New-AzResourceMoverMoveCollection.md)
Membuat atau memperbarui kumpulan pindahkan.

### [Remove-AzResourceMoverMoveCollection](Remove-AzResourceMoverMoveCollection.md)
Menghapus kumpulan pindahkan.

### [Remove-AzResourceMoverMoveResource](Remove-AzResourceMoverMoveResource.md)
Menghapus Sumber Daya Pemindahan dari kumpulan pemindahan.

### [Resolve-AzResourceMoverMoveCollectionDependency](Resolve-AzResourceMoverMoveCollectionDependency.md)
Menghitung, menyelesaikan, dan memvalidasi dependensi moveResources di kumpulan pemindahan.

