---
title: Menggunakan Azure PowerShell di Docker
description: Cara menggunakan Azure PowerShell yang sudah diinstal sebelumnya dalam gambar Docker.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/04/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: a6422099018fd917f44ace3e4b454ce64ab941a9
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138335097"
---
# <a name="using-azure-powershell-in-docker"></a>Menggunakan Azure PowerShell di Docker

Kami menerbitkan gambar Docker dengan Azure PowerShell yang sudah diinstal sebelumnya. Artikel ini menunjukkan kepada Anda cara memulai menggunakan Azure PowerShell dalam wadah Docker.

## <a name="finding-available-images"></a>Menemukan gambar yang tersedia

Gambar yang dirilis membutuhkan Docker 17.05 atau yang lebih baru. Diharapkan juga bahwa Anda dapat menjalankan Docker tanpa `sudo` atau hak administratif lokal. Silakan ikuti [instruksi][install] resmi Docker untuk menginstal `docker` dengan benar.

Gambar kontainer terbaru berisi versi terbaru PowerShell dan modul Azure PowerShell terbaru yang didukung dengan modul Az.

Untuk setiap rilis baru modul Az kami merilis gambar untuk sistem operasi berikut:

- Ubuntu 18.04 (default)
- Debian 9
- CentOS 7

Daftar lengkap gambar yang tersedia dapat ditemukan di halaman [gambar Docker][az image] kami.

## <a name="using-azure-powershell-in-a-container"></a>Menggunakan Azure PowerShell dalam wadah

Langkah-langkah berikut menunjukkan perintah Docker yang diperlukan untuk mengunduh gambar dan memulai sesi PowerShell interaktif.

1. Unduh gambar azure-powershell terbaru.

   ```console
   docker pull mcr.microsoft.com/azure-powershell
   ```

1. Jalankan kontainer azure-powershell dalam mode interaktif:

   ```console
   docker run -it mcr.microsoft.com/azure-powershell pwsh
   ```

Untuk host Docker Windows, Anda harus mengaktifkan berbagi file Docker untuk memungkinkan drive lokal di Windows dibagikan dengan kontainer Linux. Untuk informasi [selengkapnya lihat Mulai dengan Docker untuk Windows][file-sharing].

### <a name="run-the-azure-powershell-container-interactively-using-host-authentication"></a>Jalankan kontainer azure-powershell secara interaktif menggunakan autentikasi host

Jika Anda telah Azure PowerShell diinstal pada sistem hosting Docker, Anda mungkin telah menyimpan kredensial Azure yang di-cache. Kredensial ini dapat digunakan dalam sesi PowerShell yang berjalan di kontainer Docker.

Secara default, kredensial yang di-cache ada di `$HOME/.Azure` direktori di host Anda. Layanan Docker harus memiliki akses ke lokasi ini untuk mengakses kredensial. Perintah berikut memulai kontainer dengan cache kredensial yang dipasang dan memulai sesi PowerShell interaktif.

```console
docker run -it -v ~/.Azure/AzureRmContext.json:/root/.Azure/AzureRmContext.json -v ~/.Azure/TokenCache.dat:/root/.Azure/TokenCache.dat mcr.microsoft.com/azure-powershell pwsh
```

### <a name="remove-the-image-when-no-longer-needed"></a>Menghapus gambar saat tidak lagi diperlukan

Perintah berikut digunakan untuk menghapus kontainer Docker saat Anda tidak lagi membutuhkannya.

```console
docker rmi mcr.microsoft.com/azure-powershell
```

## <a name="next-steps"></a>Langkah berikutnya

Untuk mempelajari lebih lanjut tentang modul Azure PowerShell dan fitur-fiturnya, lihat [Mulai dengan Azure PowerShell](get-started-azureps.md).

<!-- link references -->
[install]: https://docs.docker.com/engine/installation/
[powershell image]: https://hub.docker.com/_/microsoft-powershell
[az image]: https://hub.docker.com/_/microsoft-azure-powershell
[file-sharing]: https://docs.docker.com/docker-for-windows/#file-sharing
