---
title: Menggunakan modul Az PowerShell di belakang proksi
description: Cara menggunakan modul PowerShell Azure Az di belakang server proksi
ms.date: 09/27/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 7f4eb2101b5af592ee9ebbeca49c85165bc8aff5
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429337"
---
# <a name="use-the-az-powershell-module-behind-a-proxy"></a>Menggunakan modul Az PowerShell di belakang proksi

Jika proksi diperlukan untuk permintaan HTTP, tim Azure PowerShell merekomendasikan konfigurasi proksi berikut ini untuk platform yang berbeda:

|      **Platform**       |                          **Proksi yang Pengaturan**                           |                                               **Komentar**                                                |
| ----------------------- | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Windows PowerShell 5.1  | Pengaturan proksi sistem                                                             | Jangan sarankan pengaturan HTTP_PROXY/HTTPS_PROXY variabel lingkungan.                                     |
| PowerShell 7 di Windows | Pengaturan proksi sistem                                                             | Proksi dapat dikonfigurasi dengan menyetel HTTP_PROXY maupun HTTPS_PROXY variabel lingkungan.              |
| PowerShell 7 di macOS   | Pengaturan proksi sistem                                                             | Proksi dapat dikonfigurasi dengan menyetel HTTP_PROXY maupun HTTPS_PROXY variabel lingkungan.              |
| PowerShell 7 di Linux   | Menyetel baik HTTP_PROXY maupun HTTPS_PROXY variabel lingkungan, plus nilai NO_PROXY | Variabel lingkungan harus diatur sebelum memulai PowerShell, jika tidak, variabel mungkin tidak dihargai. |

Variabel lingkungan yang digunakan adalah:

- HTTP_PROXY: server proksi digunakan pada permintaan HTTP.
- HTTPS_PROXY: server proksi yang digunakan pada permintaan HTTPS.
- NO_PROXY: daftar nama host yang dipisahkan koma yang harus dikecualikan dari proksi.

Pada sistem di mana variabel lingkungan peka huruf besar/kecil, nama variabel mungkin semuanya huruf kecil atau semua huruf besar. Nama huruf kecil dicentang terlebih dahulu.
