---
title: Menggunakan modul Az PowerShell di belakang proksi
description: Cara menggunakan modul PowerShell Azure Az di belakang server proksi
ms.date: 11/02/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 2847bcac5c60725e7a9eab18f6cca3827d945c01
ms.sourcegitcommit: b7ef209e489945ce397bbbba2c5f34fa6b2ca22e
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429569"
---
# <a name="use-the-az-powershell-module-behind-a-proxy"></a>Menggunakan modul Az PowerShell di belakang proksi

Jika proksi diperlukan untuk permintaan HTTP, tim Azure PowerShell merekomendasikan konfigurasi proksi berikut ini untuk platform yang berbeda:

|      **Platform**       |                          **Proksi yang Pengaturan**                           |                                               **Komentar**                                                |
| ----------------------- | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Windows PowerShell 5.1  | Pengaturan proksi sistem                                                             | Jangan sarankan pengaturan HTTP_PROXY/HTTPS_PROXY variabel lingkungan.                                     |
| PowerShell 7 Windows | Pengaturan proksi sistem                                                             | Proksi dapat dikonfigurasi dengan menyetel HTTP_PROXY maupun HTTPS_PROXY variabel lingkungan.              |
| PowerShell 7 di macOS   | Pengaturan proksi sistem                                                             | Proksi dapat dikonfigurasi dengan menyetel HTTP_PROXY maupun HTTPS_PROXY variabel lingkungan.              |
| PowerShell 7 di Linux   | Atur baik HTTP_PROXY maupun HTTPS_PROXY lingkungan mereka, ditambah opsi NO_PROXY | Variabel lingkungan harus diatur sebelum memulai PowerShell, jika tidak, variabel mungkin tidak dihargai. |

Variabel lingkungan yang digunakan adalah:

- HTTP_PROXY: server proksi digunakan pada permintaan HTTP.
- HTTPS_PROXY: server proksi yang digunakan pada permintaan HTTPS.
- NO_PROXY: daftar nama host yang dipisahkan koma yang harus dikecualikan dari proksi.

Pada sistem di mana variabel lingkungan peka huruf besar/kecil, nama variabel mungkin semuanya huruf kecil atau semua huruf besar. Nama huruf kecil dicentang terlebih dahulu.
