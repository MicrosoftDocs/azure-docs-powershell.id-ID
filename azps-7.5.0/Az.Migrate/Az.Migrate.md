---
Module Name: Az.Migrate
Module Guid: c638312b-9fd1-4611-a5cc-11a8caa5b698
Download Help Link: https://docs.microsoft.com/powershell/module/az.migrate
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Az.Migrate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Az.Migrate.md
ms.openlocfilehash: ebbed31853cd7f87e99a5380701ad838dc66fb8c
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144241381"
---
# Modul Az.Migrate
## Deskripsi
Microsoft Azure PowerShell: Memigrasikan cmdlet

## Cmdlet Az.Migrate
### [Get-AzMigrateDiscoveredServer](Get-AzMigrateDiscoveredServer.md)
Dapatkan commandlet server migrasi Azure mengambil semua server dalam proyek migrasi.

### [Get-AzMigrateJob](Get-AzMigrateJob.md)
Cmdlet Get-AzMigrateJob mengambil status pekerjaan Azure Migrate.

### [Get-AzMigrateProject](Get-AzMigrateProject.md)
Metode untuk mendapatkan proyek migrasi.

### [Get-AzMigrateReplicationEligibilityResult](Get-AzMigrateReplicationEligibilityResult.md)
Memvalidasi apakah VM tertentu dapat dilindungi atau tidak dalam hal ini mengembalikan daftar kesalahan.

### [Get-AzMigrateReplicationFabric](Get-AzMigrateReplicationFabric.md)
Mendapatkan detail azure Site Recovery fabric.

### [Get-AzMigrateReplicationPolicy](Get-AzMigrateReplicationPolicy.md)
Mendapatkan detail kebijakan replikasi.

### [Get-AzMigrateReplicationProtectionContainer](Get-AzMigrateReplicationProtectionContainer.md)
Mendapatkan detail kontainer perlindungan.

### [Get-AzMigrateReplicationProtectionContainerMapping](Get-AzMigrateReplicationProtectionContainerMapping.md)
Mendapatkan detail pemetaan kontainer perlindungan.

### [Get-AzMigrateReplicationProtectionIntent](Get-AzMigrateReplicationProtectionIntent.md)
Mendapatkan detail niat perlindungan replikasi ASR.

### [Get-AzMigrateReplicationRecoveryServicesProvider](Get-AzMigrateReplicationRecoveryServicesProvider.md)
Mendapatkan detail penyedia layanan pemulihan terdaftar.

### [Get-AzMigrateReplicationVaultSetting](Get-AzMigrateReplicationVaultSetting.md)
Mendapatkan pengaturan vault.
Ini termasuk pengaturan koneksi Migration Hub.

### [Get-AzMigrateRunAsAccount](Get-AzMigrateRunAsAccount.md)
Metode untuk dijalankan sebagai akun.

### [Get-AzMigrateServerReplication](Get-AzMigrateServerReplication.md)
Cmdlet Get-AzMigrateServerReplication mengambil objek untuk server replikasi.

### [Get-AzMigrateSite](Get-AzMigrateSite.md)
Metode untuk mendapatkan situs.

### [Get-AzMigrateSolution](Get-AzMigrateSolution.md)
Mendapatkan solusi dalam proyek migrasi.

### [Get-AzMigrateSupportedOperatingSystem](Get-AzMigrateSupportedOperatingSystem.md)
Mendapatkan data sistem operasi yang didukung oleh SRS.

### [Initialize-AzMigrateReplicationInfrastructure](Initialize-AzMigrateReplicationInfrastructure.md)
Cmdlet Initialize-AzMigrateReplicationInfrastructure menginisialisasi infrastruktur untuk proyek migrasi.

### [New-AzMigrateDiskMapping](New-AzMigrateDiskMapping.md)
Cmdlet New-AzMigrateDiskMapping membuat pemetaan disk sumber yang terpasang pada server yang akan dimigrasikan

### [New-AzMigrateNicMapping](New-AzMigrateNicMapping.md)
Cmdlet New-AzMigrateNicMapping membuat pemetaan NIC sumber yang dilampirkan ke server yang akan dimigrasikan.
Objek ini disediakan sebagai input ke cmdlet Set-AzMigrateServerReplication untuk memperbarui NIC dan propertinya untuk server replikasi.

### [New-AzMigrateProject](New-AzMigrateProject.md)
Membuat proyek Migrasi baru.

### [New-AzMigrateReplicationPolicy](New-AzMigrateReplicationPolicy.md)
Operasi untuk membuat kebijakan replikasi.

### [New-AzMigrateReplicationProtectionContainerMapping](New-AzMigrateReplicationProtectionContainerMapping.md)
Operasi untuk membuat pemetaan kontainer perlindungan.

### [New-AzMigrateReplicationProtectionIntent](New-AzMigrateReplicationProtectionIntent.md)
Operasi untuk membuat item niat perlindungan replikasi ASR.

### [New-AzMigrateReplicationVaultSetting](New-AzMigrateReplicationVaultSetting.md)
Operasi untuk mengonfigurasi pengaturan vault.

### [New-AzMigrateServerReplication](New-AzMigrateServerReplication.md)
Cmdlet New-AzMigrateServerReplication memulai replikasi untuk server tertentu yang ditemukan dalam proyek Azure Migrate.

### [Register-AzMigrateProjectTool](Register-AzMigrateProjectTool.md)
Mendaftarkan alat dengan proyek migrasi.

### [Remove-AzMigrateProject](Remove-AzMigrateProject.md)
Hapus proyek migrasi.
Menghapus proyek yang tidak ada adalah tanpa operasi.

### [Remove-AzMigrateServerReplication](Remove-AzMigrateServerReplication.md)
Cmdlet Remove-AzMigrateServerReplication menghentikan replikasi untuk server yang dimigrasikan.

### [Restart-AzMigrateServerReplication](Restart-AzMigrateServerReplication.md)
Cmdlet Restart-AzMigrateServerReplication memperbaiki replikasi untuk server yang ditentukan.

### [Set-AzMigrateDiskMapping](Set-AzMigrateDiskMapping.md)
Cmdlet Set-AzMigrateDiskMapping memperbarui pemetaan disk sumber yang dilampirkan ke server yang akan dimigrasikan

### [Set-AzMigrateServerReplication](Set-AzMigrateServerReplication.md)
Cmdlet Set-AzMigrateServerReplication memperbarui properti target untuk server replikasi.

### [Start-AzMigrateServerMigration](Start-AzMigrateServerMigration.md)
Memulai migrasi untuk server replikasi.

### [Start-AzMigrateTestMigration](Start-AzMigrateTestMigration.md)
Cmdlet Start-AzMigrateTestMigration memulai migrasi pengujian untuk server replikasi.

### [Start-AzMigrateTestMigrationCleanup](Start-AzMigrateTestMigrationCleanup.md)
Cmdlet Start-AzMigrateTestMigrationCleanup memulai pembersihan migrasi pengujian untuk server replikasi.

