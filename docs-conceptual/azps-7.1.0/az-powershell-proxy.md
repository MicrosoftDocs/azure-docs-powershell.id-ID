---
title: Menggunakan modul Az PowerShell di belakang proksi
description: Cara menggunakan modul PowerShell Azure Az di belakang server proksi
ms.date: 01/04/2022
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 60428ed9014ad301f3608222e66b3f8cffb619f7
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "135958397"
---
# <a name="use-the-az-powershell-module-behind-a-proxy"></a>Menggunakan modul Az PowerShell di belakang proksi

Jika proksi diperlukan untuk permintaan HTTP, tim Azure PowerShell merekomendasikan konfigurasi proksi berikut ini untuk platform yang berbeda:

|      **Platform**       |                          **Proksi yang Pengaturan**                           |                                               **Komentar**                                                |
| ----------------------- | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Windows PowerShell 5.1  | Pengaturan proksi sistem                                                             | Jangan sarankan pengaturan HTTP_PROXY/HTTPS_PROXY variabel lingkungan.                                     |
| PowerShell 7 Windows | Pengaturan proksi sistem                                                             | Proksi dapat dikonfigurasi dengan mengatur HTTP_PROXY maupun HTTPS_PROXY variabel lingkungan.              |
| PowerShell 7 di macOS   | Pengaturan proksi sistem                                                             | Proksi dapat dikonfigurasi dengan mengatur HTTP_PROXY maupun HTTPS_PROXY variabel lingkungan.              |
| PowerShell 7 di Linux   | Atur baik HTTP_PROXY maupun HTTPS_PROXY lingkungan lingkungan, ditambah opsi NO_PROXY | Variabel lingkungan harus diatur sebelum memulai PowerShell, jika tidak, variabel mungkin tidak dihargai. |

Variabel lingkungan yang digunakan adalah:

- HTTP_PROXY: server proksi digunakan pada permintaan HTTP.
- HTTPS_PROXY: server proksi yang digunakan pada permintaan HTTPS.
- NO_PROXY: daftar nama host yang dipisahkan koma yang harus dikecualikan dari proksi.

Pada sistem di mana variabel lingkungan peka huruf besar/kecil, nama variabel mungkin semuanya huruf kecil atau semua huruf besar. Nama huruf kecil dicentang terlebih dahulu.
