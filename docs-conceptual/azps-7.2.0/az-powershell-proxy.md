---
title: Menggunakan modul Az PowerShell di belakang proxy
description: Cara menggunakan modul Azure Az PowerShell di belakang server proxy
ms.date: 01/04/2022
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 60428ed9014ad301f3608222e66b3f8cffb619f7
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138335130"
---
# <a name="use-the-az-powershell-module-behind-a-proxy"></a>Menggunakan modul Az PowerShell di belakang proxy

Jika proxy diperlukan untuk permintaan HTTP, tim Azure PowerShell merekomendasikan konfigurasi proxy berikut untuk platform yang berbeda:

|      **Platform**       |                          **Pengaturan Proxy yang Direkomendasikan**                           |                                               **Komentar**                                                |
| ----------------------- | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Windows PowerShell 5,1  | Pengaturan proxy sistem                                                             | Jangan menyarankan pengaturan variabel lingkungan HTTP_PROXY/HTTPS_PROXY.                                     |
| PowerShell 7 pada Windows | Pengaturan proxy sistem                                                             | Proxy dapat dikonfigurasi dengan mengatur variabel lingkungan HTTP_PROXY dan HTTPS_PROXY.              |
| PowerShell 7 di macOS   | Pengaturan proxy sistem                                                             | Proxy dapat dikonfigurasi dengan mengatur variabel lingkungan HTTP_PROXY dan HTTPS_PROXY.              |
| PowerShell 7 di Linux   | Atur variabel lingkungan HTTP_PROXY dan HTTPS_PROXY, ditambah NO_PROXY opsional | Variabel lingkungan harus diatur sebelum memulai PowerShell, jika tidak, variabel tersebut mungkin tidak dihormati. |

Variabel lingkungan yang digunakan adalah:

- HTTP_PROXY: server proxy yang digunakan pada permintaan HTTP.
- HTTPS_PROXY: server proxy yang digunakan pada permintaan HTTPS.
- NO_PROXY: daftar nama host yang dipisahkan koma yang harus dikecualikan dari proxying.

Pada sistem di mana variabel lingkungan peka huruf besar/kecil, nama variabel mungkin semuanya huruf kecil atau huruf besar. Nama-nama huruf kecil diperiksa terlebih dahulu.
