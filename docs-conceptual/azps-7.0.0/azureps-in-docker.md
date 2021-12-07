---
title: Menggunakan Azure PowerShell di Docker
description: Cara menggunakan Azure PowerShell yang telah diinstal sebelumnya dalam gambar Docker.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/02/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: ef5f9c2007f6475b4c53a6e3c8510e6222102a6f
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "134026012"
---
# <a name="using-azure-powershell-in-docker"></a>Menggunakan Azure PowerShell di Docker

Kami menerbitkan gambar Docker dengan Azure PowerShell yang telah diinstal sebelumnya. Artikel ini memperlihatkan kepada Anda cara mulai menggunakan Azure PowerShell dalam wadah Docker.

## <a name="finding-available-images"></a>Menemukan gambar yang tersedia

Gambar yang dirilis memerlukan Docker 17.05 atau yang lebih baru. Diharapkan pula bahwa Anda bisa menjalankan Docker tanpa atau `sudo` hak administratif lokal. Ikuti instruksi resmi Docker [untuk menginstal][install] dengan `docker` benar.

Gambar wadah terbaru berisi versi terbaru PowerShell dan modul Azure PowerShell terbaru yang didukung dengan modul Az.

Untuk setiap rilis baru modul Az, kami akan merilis gambar untuk sistem operasi berikut ini:

- Ubuntu 18.04 (default)
- Debian 9
- CentOS 7

Daftar lengkap gambar yang tersedia dapat ditemukan di halaman [gambar Docker][az image] kami.

## <a name="using-azure-powershell-in-a-container"></a>Menggunakan Azure PowerShell dalam wadah

Langkah-langkah berikut ini memperlihatkan perintah Docker yang diperlukan untuk mengunduh gambar dan memulai sesi PowerShell interaktif.

1. Unduh gambar terbaru Azure-powershell.

   ```console
   docker pull mcr.microsoft.com/azure-powershell
   ```

1. Jalankan wadah azure-powershell dalam mode interaktif:

   ```console
   docker run -it mcr.microsoft.com/azure-powershell pwsh
   ```

Untuk Windows docker baru, Anda harus mengaktifkan berbagi file Docker agar drive lokal Windows dapat dibagikan dengan wadah Linux. Untuk informasi selengkapnya, [lihat Mulai menggunakan Docker untuk Windows][file-sharing].

### <a name="run-the-azure-powershell-container-interactively-using-host-authentication"></a>Jalankan wadah azure-powershell secara interaktif menggunakan autentikasi host

Jika telah Azure PowerShell di docker hosting sistem, Anda mungkin memiliki kredensial Azure singgahan. Kredensial ini dapat digunakan di sesi PowerShell yang berjalan dalam wadah Docker.

Secara default, kredensial singgahan berada dalam direktori `$HOME/.Azure` di host Anda. Layanan Docker harus memiliki akses ke lokasi ini untuk mengakses kredensial. Perintah berikut memulai wadah dengan cache kredensial yang terpasang dan memulai sesi PowerShell interaktif.

```console
docker run -it -v ~/.Azure/AzureRmContext.json:/root/.Azure/AzureRmContext.json -v ~/.Azure/TokenCache.dat:/root/.Azure/TokenCache.dat mcr.microsoft.com/azure-powershell pwsh
```

### <a name="remove-the-image-when-no-longer-needed"></a>Hapus gambar ketika tidak lagi diperlukan

Perintah berikut ini digunakan untuk menghapus wadah Docker ketika Anda tidak lagi memerlukannya.

```console
docker rmi mcr.microsoft.com/azure-powershell
```

## <a name="next-steps"></a>Langkah berikutnya

Untuk mempelajari selengkapnya tentang modul Azure PowerShell dan fiturnya, lihat [Mulai dengan Azure PowerShell](get-started-azureps.md).

<!-- link references -->
[install]: https://docs.docker.com/engine/installation/
[powershell image]: https://hub.docker.com/_/microsoft-powershell
[az image]: https://hub.docker.com/_/microsoft-azure-powershell
[file-sharing]: https://docs.docker.com/docker-for-windows/#file-sharing
