---
Module Name: Az.Support
Module Guid: 22d73af7-38c2-4bf6-b56f-4dc9db05d97a
Download Help Link: https://docs.microsoft.com/powershell/module/az.support
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Az.Support.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Support/Support/help/Az.Support.md
ms.openlocfilehash: 42ab910b01e81911f94945ecf6244a744542b311
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138288267"
---
# Az.Support Module
## Deskripsi
Topik dalam bagian ini mendokumentasikan Azure PowerShell cmdlet untuk membuat dan mengelola tiket dukungan Azure dalam kerangka kerja Azure Resource Manager (ARM). Cmdlet ada dalam ruang nama Microsoft.Azure.Commands.Support

## Cmdlet Az.Support
### [Get-AzSupportService](Get-AzSupportService.md)
Mendapatkan daftar layanan Azure saat ini yang menyediakan dukungan. Setiap layanan Azure memiliki kumpulan kategorinya sendiri yang disebut klasifikasi masalah. Dapatkan daftar klasifikasi masalah saat ini untuk layanan menggunakan Get-AzSupportProblemClassification. Anda dapat menggunakan GUID klasifikasi masalah dan layanan untuk membuat tiket dukungan baru menggunakan New-AzSupportTicket.

### [Get-AzSupportProblemClassification](Get-AzSupportProblemClassification.md)
Dapatkan daftar klasifikasi masalah saat ini untuk layanan Azure. Anda dapat menggunakan GUID klasifikasi masalah dan layanan untuk membuat tiket dukungan baru menggunakan New-AzSupportTicket. 

### [New-AzSupportContactProfileObject](New-AzSupportContactProfileObject.md)
Cmdlet Helper untuk membuat objek profil kontak dukungan. Anda dapat menggunakan objek ini New-AzSupportTicket cmdlet.

### [New-AzSupportTicket](New-AzSupportTicket.md)
Buat tiket dukungan Azure baru. Operasi ini dimodelkan pada perilaku halaman [permintaan dukungan Azure New](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview).

### [Get-AzSupportTicket](Get-AzSupportTicket.md)
Mendapatkan daftar tiket dukungan. Anda bisa mendapatkan detail tiket dukungan lengkap menurut nama tiket atau memfilter tiket dukungan menurut *Status* atau *CreatedDate*.

### [Update-AzSupportTicket](Update-AzSupportTicket.md)
Perbarui detail jelas, status, status, atau kontak pelanggan Anda.

### [Get-AzSupportTicketCommunication](Get-AzSupportTicketCommunication.md)
Mendapatkan komunikasi untuk tiket dukungan. Anda juga dapat memfilter komunikasi tiket dukungan oleh *CreatedDate* atau *CommunicationType*. 

### [New-AzSupportTicketCommunication](New-AzSupportTicketCommunication.md)
Menambahkan komunikasi pelanggan baru ke tiket dukungan Azure. 



