---
title: Menggunakan modul Az PowerShell di belakang proksi
description: Cara menggunakan modul Azure Az PowerShell di belakang server proksi
ms.date: 11/02/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 2847bcac5c60725e7a9eab18f6cca3827d945c01
ms.sourcegitcommit: b7ef209e489945ce397bbbba2c5f34fa6b2ca22e
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429569"
---
# <a name="use-the-az-powershell-module-behind-a-proxy"></a>Menggunakan modul Az PowerShell di belakang proksi

Jika proksi diperlukan untuk permintaan HTTP, tim Azure PowerShell merekomendasikan konfigurasi proksi berikut untuk platform yang berbeda:

|      **Platform**       |                          **Pengaturan Proksi yang Direkomendasikan**                           |                                               **Komentar**                                                |
| ----------------------- | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Windows PowerShell 5.1  | Pengaturan proksi sistem                                                             | Jangan menyarankan pengaturan variabel lingkungan HTTP_PROXY/HTTPS_PROXY.                                     |
| PowerShell 7 di Windows | Pengaturan proksi sistem                                                             | Proksi dapat dikonfigurasi dengan mengatur variabel lingkungan HTTP_PROXY dan HTTPS_PROXY.              |
| PowerShell 7 di macOS   | Pengaturan proksi sistem                                                             | Proksi dapat dikonfigurasi dengan mengatur variabel lingkungan HTTP_PROXY dan HTTPS_PROXY.              |
| PowerShell 7 di Linux   | Mengatur variabel lingkungan HTTP_PROXY dan HTTPS_PROXY, ditambah NO_PROXY opsional | Variabel lingkungan harus diatur sebelum memulai PowerShell, jika tidak, variabel mungkin tidak dianggap. |

Variabel lingkungan digunakan:

- HTTP_PROXY: server proksi yang digunakan pada permintaan HTTP.
- HTTPS_PROXY: server proksi yang digunakan pada permintaan HTTPS.
- NO_PROXY: daftar nama host yang dipisahkan koma yang harus dikecualikan dari proksi.

Pada sistem di mana variabel lingkungan peka huruf besar/kecil, nama variabel bisa semua huruf kecil atau huruf besar. Nama-nama huruf kecil diperiksa terlebih dahulu.
