---
title: Menggunakan modul Az PowerShell di belakang proksi
description: Cara menggunakan modul PowerShell Azure Az di belakang server proksi
ms.date: 12/07/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: a8bfcdbf57ca238d61bb937d8160c9dc08d947fe
ms.sourcegitcommit: 2a404a7aac28f6568e0e17912814e4403ea5d0d9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/08/2021
ms.locfileid: "134110613"
---
# <a name="use-the-az-powershell-module-behind-a-proxy"></a>Menggunakan modul Az PowerShell di belakang proksi

Jika proksi diperlukan untuk permintaan HTTP, tim Azure PowerShell merekomendasikan konfigurasi proksi berikut ini untuk platform yang berbeda:

|      **Platform**       |                          **Proksi yang Pengaturan**                           |                                               **Komentar**                                                |
| ----------------------- | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Windows PowerShell 5.1  | Pengaturan proksi sistem                                                             | Jangan sarankan pengaturan HTTP_PROXY/HTTPS_PROXY variabel lingkungan.                                     |
| PowerShell 7 pada Windows | Pengaturan proksi sistem                                                             | Proksi dapat dikonfigurasi dengan menyetel HTTP_PROXY maupun HTTPS_PROXY variabel lingkungan.              |
| PowerShell 7 di macOS   | Pengaturan proksi sistem                                                             | Proksi dapat dikonfigurasi dengan menyetel HTTP_PROXY maupun HTTPS_PROXY variabel lingkungan.              |
| PowerShell 7 di Linux   | Atur baik HTTP_PROXY lingkungan HTTPS_PROXY maupun variabel lingkungan, ditambah NO_PROXY | Variabel lingkungan harus diatur sebelum memulai PowerShell, jika tidak, variabel mungkin tidak dihargai. |

Variabel lingkungan yang digunakan adalah:

- HTTP_PROXY: server proksi digunakan pada permintaan HTTP.
- HTTPS_PROXY: server proksi digunakan pada permintaan HTTPS.
- NO_PROXY: daftar nama host yang dipisahkan koma yang harus dikecualikan dari proksi.

Pada sistem di mana variabel lingkungan peka huruf besar/kecil, nama variabel mungkin semuanya huruf kecil atau semua huruf besar. Nama huruf kecil dicentang terlebih dahulu.
