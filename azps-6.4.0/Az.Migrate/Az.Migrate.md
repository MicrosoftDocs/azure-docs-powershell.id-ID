---
Module Name: Az.Migrate
Module Guid: c638312b-9fd1-4611-a5cc-11a8caa5b698
Download Help Link: https://docs.microsoft.com/powershell/module/az.migrate
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Az.Migrate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Az.Migrate.md
ms.openlocfilehash: ebbed31853cd7f87e99a5380701ad838dc66fb8c
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136201620"
---
# Az.Migrate Module
## Deskripsi
Microsoft Azure PowerShell: Migrasikan cmdlet

## Az.Migrate Cmdlets
### [Get-AzMigrateDiscoveredServer](Get-AzMigrateDiscoveredServer.md)
Dapatkan commandlet server migrasi Azure mengambil semua server dalam proyek migrasi.

### [Get-AzMigrateJob](Get-AzMigrateJob.md)
Cmdlet Get-AzMigrateJob cmdlet tersebut masih menggunakan status pekerjaan Azure Migrate.

### [Get-AzMigrateProject](Get-AzMigrateProject.md)
Metode untuk mendapatkan migrasi proyek.

### [Get-AzMigrateReplicationEligibilityResult](Get-AzMigrateReplicationEligibilityResult.md)
Memvalidasi apakah VM yang diberikan dapat dilindungi atau tidak, dalam hal ini, daftar kesalahan akan dikembalikan.

### [Get-AzMigrateReplicationFabric](Get-AzMigrateReplicationFabric.md)
Gets the details of an Azure Site Recovery fabric.

### [Get-AzMigrateReplicationPolicy](Get-AzMigrateReplicationPolicy.md)
Mendapatkan detail kebijakan replikasi.

### [Get-AzMigrateReplicationProtectionContainer](Get-AzMigrateReplicationProtectionContainer.md)
Mendapatkan detail wadah proteksi.

### [Get-AzMigrateReplicationProtectionContainerMapping](Get-AzMigrateReplicationProtectionContainerMapping.md)
Mendapatkan detail pemetaan wadah proteksi.

### [Get-AzMigrateReplicationProtectionIntent](Get-AzMigrateReplicationProtectionIntent.md)
Mendapatkan detail tujuan perlindungan replikasi ASR.

### [Get-AzMigrateReplicationRecoveryServicesProvider](Get-AzMigrateReplicationRecoveryServicesProvider.md)
Dapatkan detail dari penyedia layanan pemulihan yang terdaftar.

### [Get-AzMigrateReplicationVaultSetting](Get-AzMigrateReplicationVaultSetting.md)
Dapatkan pengaturan vault.
Ini termasuk pengaturan koneksi Hub Migrasi.

### [Get-azMigrateRunAsAccount](Get-AzMigrateRunAsAccount.md)
Metode untuk menjalankan sebagai akun.

### [Get-AzMigrateServerReplication](Get-AzMigrateServerReplication.md)
Cmdlet Get-AzMigrateServerReplication mengambil objek untuk server yang replikasi.

### [Get-AzMigrateSite](Get-AzMigrateSite.md)
Metode untuk mendapatkan situs.

### [Get-AzMigrateSolution](Get-AzMigrateSolution.md)
Mendapatkan solusi dalam proyek migrasi.

### [Get-AzMigrateSupportedOperatingSystem](Get-AzMigrateSupportedOperatingSystem.md)
Mendapatkan data sistem operasi yang didukung oleh SRS.

### [Initialize-AzMigrateReplicationInfrastructure](Initialize-AzMigrateReplicationInfrastructure.md)
Inisial Initialize-AzMigrateReplicationInfrastructure cmdlet adalah infrastruktur untuk proyek migrasi.

### [New-AzMigrateDiskMapping](New-AzMigrateDiskMapping.md)
Cmdlet New-AzMigrateDiskMapping membuat pemetaan disk sumber yang terhubung ke server untuk dimigrasi

### [New-AzMigrateNicMapping](New-AzMigrateNicMapping.md)
Cmdlet New-AzMigrateNicMapping membuat pemetaan NIC sumber yang terhubung ke server untuk dimigrasi.
Objek ini disediakan sebagai input ke cmdlet Set-AzMigrateServerReplication untuk memperbarui NIC dan propertinya untuk server yang replikasi.

### [New-AzMigrateProject](New-AzMigrateProject.md)
Membuat proyek Migrasi baru.

### [New-AzMigrateReplicationPolicy](New-AzMigrateReplicationPolicy.md)
Operasi untuk membuat kebijakan replikasi.

### [New-AzMigrateReplicationProtectionContainerMapping](New-AzMigrateReplicationProtectionContainerMapping.md)
Operasi ini untuk membuat pemetaan wadah proteksi.

### [New-AzMigrateReplicationProtectionIntent](New-AzMigrateReplicationProtectionIntent.md)
Operasi untuk membuat item tujuan proteksi replikasi ASR.

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
Cmdlet Set-AzMigrateDiskMapping memperbarui pemetaan disk sumber yang terhubung ke server untuk dimigrasi

### [Set-AzMigrateServerReplication](Set-AzMigrateServerReplication.md)
Cmdlet Set-AzMigrateServerReplication memperbarui properti target untuk server yang replikasi.

### [Start-AzMigrateServerMigration](Start-AzMigrateServerMigration.md)
Memulai migrasi untuk server yang replikasi.

### [Start-azMigrateTestMigration](Start-AzMigrateTestMigration.md)
Cmdlet Start-AzMigrateTestMigration memulai migrasi pengujian untuk server replika.

### [Start-AzMigrateTestMigrationCleanup](Start-AzMigrateTestMigrationCleanup.md)
Cmdlet Start-AzMigrateTestMigrationCleanup memulai pembersihan migrasi percobaan untuk replikasi server.

