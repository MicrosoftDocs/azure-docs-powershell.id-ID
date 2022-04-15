---
Module Name: Az.Migrate
Module Guid: c638312b-9fd1-4611-a5cc-11a8caa5b698
Download Help Link: https://docs.microsoft.com/powershell/module/az.migrate
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Az.Migrate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Az.Migrate.md
ms.openlocfilehash: ebbed31853cd7f87e99a5380701ad838dc66fb8c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142001714"
---
# Az.Migrasi Modul
## Deskripsi
Microsoft Azure PowerShell: Melakukan migrasi cmdlet

## Az.Migrasi cmdlet
### [Get-AzMigrateDiscoveredServer](Get-AzMigrateDiscoveredServer.md)
Dapatkan commandlet server migrasi Azure mengambil semua server dalam proyek migrasi.

### [Get-AzMigrateJob](Get-AzMigrateJob.md)
Cmdlet Get-AzMigrateJob mengupahkan status pekerjaan Migrasi Azure.

### [Get-AzMigrateProject](Get-AzMigrateProject.md)
Metode untuk mendapatkan proyek migrasi.

### [Get-AzMigrateReplicationEligibilityResult](Get-AzMigrateReplicationEligibilityResult.md)
Memvalidasi apakah VM tertentu dapat dilindungi atau tidak dalam hal ini mengembalikan daftar kesalahan.

### [Get-AzMigrateReplicationFabric](Get-AzMigrateReplicationFabric.md)
Mendapatkan detail kain Site Recovery Azure.

### [Get-AzMigrateReplicationPolicy](Get-AzMigrateReplicationPolicy.md)
Mendapatkan detail kebijakan replikasi.

### [Get-AzMigrateReplicationProtectionContainer](Get-AzMigrateReplicationProtectionContainer.md)
Mendapatkan detail wadah perlindungan.

### [Get-AzMigrateReplicationProtectionContainerMapping](Get-AzMigrateReplicationProtectionContainerMapping.md)
Mendapatkan detail pemetaan wadah perlindungan.

### [Get-AzMigrateReplicationProtectionIntent](Get-AzMigrateReplicationProtectionIntent.md)
Mendapatkan detail tujuan perlindungan replikasi ASR.

### [Get-AzMigrateReplicationRecoveryServicesProvider](Get-AzMigrateReplicationRecoveryServicesProvider.md)
Mendapatkan detail penyedia layanan pemulihan terdaftar.

### [Get-AzMigrateReplicationVaultSetting](Get-AzMigrateReplicationVaultSetting.md)
Mendapatkan pengaturan kubah.
Ini termasuk pengaturan koneksi Hub Migrasi.

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
Cmdlet Initialize-AzMigrateReplicationInfrastructure menginisiasi infrastruktur untuk migrasi proyek.

### [New-AzMigrateDiskMapping](New-AzMigrateDiskMapping.md)
Cmdlet New-AzMigrateDiskMapping membuat pemetaan disk sumber yang terhubung ke server yang akan dimigrasikan

### [New-AzMigrateNicMapping](New-AzMigrateNicMapping.md)
Cmdlet New-AzMigrateNicMapping membuat pemetaan sumber NIC yang dilampirkan ke server yang akan dimigrasikan.
Objek ini disediakan sebagai input ke cmdlet Set-AzMigrateServerReplication untuk memperbarui NIC dan propertinya untuk server replikasi.

### [New-AzMigrateProject](New-AzMigrateProject.md)
Membuat proyek migrasi baru.

### [New-AzMigrateReplicationPolicy](New-AzMigrateReplicationPolicy.md)
Operasi untuk membuat kebijakan replikasi.

### [New-AzMigrateReplicationProtectionContainerMapping](New-AzMigrateReplicationProtectionContainerMapping.md)
Operasi untuk membuat pemetaan wadah proteksi.

### [New-AzMigrateReplicationProtectionIntent](New-AzMigrateReplicationProtectionIntent.md)
Operasi untuk membuat item tujuan proteksi replikasi ASR.

### [New-AzMigrateReplicationVaultSetting](New-AzMigrateReplicationVaultSetting.md)
Operasi untuk mengonfigurasi pengaturan kubah.

### [New-AzMigrateServerReplication](New-AzMigrateServerReplication.md)
Cmdlet New-AzMigrateServerReplication memulai replikasi untuk server tertentu yang ditemukan di proyek Migrasi Azure.

### [Register-AzMigrateProjectTool](Register-AzMigrateProjectTool.md)
Mendaftarkan alat dengan proyek migrasi.

### [Remove-AzMigrateProject](Remove-AzMigrateProject.md)
Menghapus proyek migrasi.
Menghapus proyek yang tidak ada adalah tidak ada.

### [Remove-AzMigrateServerReplication](Remove-AzMigrateServerReplication.md)
Cmdlet Remove-AzMigrateServerReplication menghentikan replikasi untuk server yang dimigrasikan.

### [Restart-AzMigrateServerReplication](Restart-AzMigrateServerReplication.md)
Cmdlet Restart-AzMigrateServerReplication memperbaiki replikasi untuk server yang ditentukan.

### [Set-AzMigrateDiskMapping](Set-AzMigrateDiskMapping.md)
Cmdlet Set-AzMigrateDiskMapping memperbarui pemetaan disk sumber yang terpasang ke server untuk dimigrasikan

### [Set-AzMigrateServerReplication](Set-AzMigrateServerReplication.md)
Cmdlet Set-AzMigrateServerReplication memperbarui properti target untuk server replikasi.

### [Start-AzMigrateServerMigration](Start-AzMigrateServerMigration.md)
Memulai migrasi untuk server replikasi.

### [Start-AzMigrateTestMigration](Start-AzMigrateTestMigration.md)
Cmdlet Start-AzMigrateTestMigration memulai migrasi uji untuk server replikasi.

### [Start-AzMigrateTestMigrationCleanup](Start-AzMigrateTestMigrationCleanup.md)
Cmdlet Start-AzMigrateTestMigrationCleanup memulai pembersihan migrasi uji untuk server replikasi.

