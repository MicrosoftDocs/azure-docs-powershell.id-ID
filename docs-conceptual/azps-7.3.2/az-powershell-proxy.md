---
description: Cara menggunakan modul Azure Az PowerShell di belakang server proksi
ms.custom: devx-track-azurepowershell
ms.date: 03/12/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Menggunakan modul Az PowerShell di belakang proksi
ms.openlocfilehash: 6abe45a126c9d91d8948d5d7c7b4e2d2379b73ad
ms.sourcegitcommit: b346b2fbd8b25f54759984e75ddbee3304921c43
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/16/2022
ms.locfileid: "140664291"
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
