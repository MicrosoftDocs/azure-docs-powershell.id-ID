---
Module Name: Az.Support
Module Guid: 22d73af7-38c2-4bf6-b56f-4dc9db05d97a
Download Help Link: https://docs.microsoft.com/powershell/module/az.support
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Az.Support.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Az.Support.md
ms.openlocfilehash: 42ab910b01e81911f94945ecf6244a744542b311
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142000774"
---
# Modul Dukungan Az.
## Deskripsi
Topik di bagian ini mendokumentasikan cmdlet Azure PowerShell untuk membuat dan mengelola tiket dukungan Azure dalam kerangka kerja Azure Resource Manager (ARM). Cmdlet ada di ruang nama Microsoft.Azure.Commands.Support

## Cmdlet Az.Support
### [Get-AzSupportService](Get-AzSupportService.md)
Mendapatkan daftar layanan Azure saat ini yang dukungannya tersedia. Setiap layanan Azure memiliki kumpulan kategorinya sendiri yang disebut klasifikasi masalah. Dapatkan daftar klasifikasi masalah saat ini untuk layanan menggunakan Get-AzSupportProblemClassification. Anda dapat menggunakan GUID klasifikasi layanan dan masalah untuk membuat tiket dukungan baru menggunakan New-AzSupportTicket.

### [Get-AzSupportProblemClassification](Get-AzSupportProblemClassification.md)
Mendapatkan daftar klasifikasi masalah saat ini untuk layanan Azure. Anda dapat menggunakan GUID klasifikasi layanan dan masalah untuk membuat tiket dukungan baru menggunakan New-AzSupportTicket. 

### [New-AzSupportContactProfileObject](New-AzSupportContactProfileObject.md)
Cmdlet helper untuk membuat objek profil kontak dukungan. Anda dapat menggunakan objek ini untuk cmdlet New-AzSupportTicket.

### [New-AzSupportTicket](New-AzSupportTicket.md)
Membuat tiket dukungan Azure baru. Operasi ini dimodelkan pada perilaku [halaman permintaan dukungan Azure New](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview).

### [Get-AzSupportTicket](Get-AzSupportTicket.md)
Mendapatkan daftar tiket dukungan. Anda dapat memperoleh detail tiket dukungan penuh berdasarkan nama tiket atau memfilter tiket dukungan menurut *Status* atau *TanggalDijadikan*.

### [Update-AzSupportTicket](Update-AzSupportTicket.md)
Perbarui tingkat keparahan, status, atau detail kontak pelanggan tiket dukungan.

### [Get-AzSupportTicketCommunication](Get-AzSupportTicketCommunication.md)
Mendapatkan komunikasi untuk tiket dukungan. Anda juga bisa memfilter komunikasi tiket dukungan oleh *CreatedDate* atau *CommunicationType*. 

### [New-AzSupportTicketCommunication](New-AzSupportTicketCommunication.md)
Menambahkan komunikasi pelanggan baru ke tiket dukungan Azure. 



