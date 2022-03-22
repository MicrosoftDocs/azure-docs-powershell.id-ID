---
title: Menggunakan Azure PowerShell di Docker
description: Cara menggunakan Azure PowerShell yang diinstal sebelumnya di citra Docker.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/20/2020
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 48935f15241ec965adf4c34d2c17aa670110585a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428011"
---
# <a name="using-azure-powershell-in-docker"></a>Menggunakan Azure PowerShell di Docker

Kami menerbitkan citra Docker dengan Azure PowerShell yang diinstal sebelumnya. Artikel ini menunjukkan kepada Anda cara memulai menggunakan Azure PowerShell di kontainer Docker.

## <a name="finding-available-images"></a>Menemukan citra yang tersedia

Citra yang dirilis memerlukan Docker 17.05 atau yang lebih baru. Diharapkan juga Anda mampu menjalankan Docker tanpa `sudo` atau hak administratif lokal. Silakan ikuti [instruksi][install] resmi Docker untuk menginstal `docker` dengan benar.

Citra kontainer terbaru berisi versi PowerShell terbaru dan modul Azure PowerShell terbaru yang didukung dengan modul Az.

Untuk setiap rilis baru modul Az, kami merilis citra untuk sistem operasi berikut:

- Ubuntu 18.04 (default)
- Debian 9
- CentOs 7

Daftar lengkap citra yang tersedia dapat ditemukan di halaman [citra Docker][az image].

## <a name="using-azure-powershell-in-a-container"></a>Menggunakan Azure PowerShell dalam kontainer

Langkah berikut menunjukkan perintah Docker yang diperlukan untuk mengunduh citra dan memulai sesi PowerShell interaktif.

1. Unduh citra azure-powershell terbaru.

   ```console
   docker pull mcr.microsoft.com/azure-powershell
   ```

1. Jalankan kontainer azure-powershell dalam mode interaktif:

   ```console
   docker run -it mcr.microsoft.com/azure-powershell pwsh
   ```

Untuk host Windows Docker, Anda harus mengaktifkan Berbagi File Docker untuk memungkinkan drive lokal pada Windows untuk dibagikan dengan kontainer Linux. Untuk informasi selengkapnya lihat [Memulai dengan Docker untuk Windows][file-sharing].

### <a name="run-the-azure-powershell-container-interactively-using-host-authentication"></a>Menjalankan kontainer azure-powershell secara interaktif menggunakan autentikasi host

Jika Anda telah menginstal Azure PowerShell di Docker hosting sistem, Anda mungkin memiliki informasi masuk Azure yang di-cache. Informasi masuk ini dapat digunakan di sesi PowerShell yang berjalan di kontainer Docker.

Secara default, informasi masuk yang di-cache ada di direktori `$HOME/.Azure` di host Anda. Layanan Docker harus memiliki akses ke lokasi ini untuk mengakses informasi masuk. Perintah berikut memulai kontainer dengan cache informasi masuk yang dipasang dan memulai sesi PowerShell interaktif.

```console
docker run -it -v ~/.Azure/AzureRmContext.json:/root/.Azure/AzureRmContext.json -v ~/.Azure/TokenCache.dat:/root/.Azure/TokenCache.dat mcr.microsoft.com/azure-powershell pwsh
```

### <a name="remove-the-image-when-no-longer-needed"></a>Menghapus citra saat tidak lagi diperlukan

Perintah berikut digunakan untuk menghapus kontainer Docker saat Anda tidak lagi membutuhkannya.

```console
docker rmi mcr.microsoft.com/azure-powershell
```

## <a name="next-steps"></a>Langkah berikutnya

Untuk mempelajari selengkapnya tentang modul Azure PowerShell dan fiturnya, lihat [Memulai dengan Azure PowerShell](get-started-azureps.md).

<!-- link references -->
[install]: https://docs.docker.com/engine/installation/
[powershell image]: https://hub.docker.com/_/microsoft-powershell
[az image]: https://hub.docker.com/_/microsoft-azure-powershell
[file-sharing]: https://docs.docker.com/docker-for-windows/#file-sharing
