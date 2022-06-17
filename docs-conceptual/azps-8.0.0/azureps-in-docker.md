---
description: Cara menggunakan Azure PowerShell yang diinstal sebelumnya di citra Docker.
ms.custom: devx-track-azurepowershell
ms.date: 05/24/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Menggunakan Azure PowerShell di Docker
ms.openlocfilehash: 071dfec2adcd0e997ef4113011ac244e393a3f1e
ms.sourcegitcommit: 16496dee798f33b983ffdc113dd248d57f3ece4d
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/17/2022
ms.locfileid: "146420900"
---
# <a name="using-azure-powershell-in-docker"></a>Menggunakan Azure PowerShell di Docker

Kami menerbitkan citra Docker dengan Azure PowerShell yang diinstal sebelumnya. Artikel ini menunjukkan kepada Anda cara memulai menggunakan Azure PowerShell di kontainer Docker.

## <a name="finding-available-images"></a>Menemukan citra yang tersedia

Citra yang dirilis memerlukan Docker 17.05 atau yang lebih baru. Diharapkan juga Anda mampu menjalankan Docker tanpa `sudo` atau hak administratif lokal. Silakan ikuti [instruksi][install] resmi Docker untuk menginstal `docker` dengan benar.

Citra kontainer terbaru berisi versi PowerShell terbaru dan modul Azure PowerShell terbaru yang didukung dengan modul Az.

Untuk setiap rilis baru modul Az, kami merilis citra untuk sistem operasi berikut:

- Ubuntu 20.04 (default)
- Debian 9
- CentOS 7+

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

Untuk host Windows Docker, Anda harus mengaktifkan berbagi file Docker untuk memungkinkan drive lokal pada Windows untuk dibagikan dengan kontainer Linux. Untuk informasi selengkapnya lihat [Memulai dengan Docker untuk Windows][file-sharing].

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
