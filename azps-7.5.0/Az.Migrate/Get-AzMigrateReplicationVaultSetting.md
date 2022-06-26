---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/get-azmigratereplicationvaultsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateReplicationVaultSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateReplicationVaultSetting.md
ms.openlocfilehash: b13f73dd42186cc751b8a703642fdf867840325b
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146640144"
---
# Get-AzMigrateReplicationVaultSetting

## SYNOPSIS
Mendapatkan pengaturan vault.
Ini termasuk pengaturan koneksi Migration Hub.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.migrate/get-azmigratereplicationvaultsetting) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzMigrateReplicationVaultSetting -ResourceGroupName <String> -ResourceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzMigrateReplicationVaultSetting -ResourceGroupName <String> -ResourceName <String>
 -VaultSettingName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzMigrateReplicationVaultSetting -InputObject <IMigrateIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan pengaturan vault.
Ini termasuk pengaturan koneksi Migration Hub.

## EXAMPLES

### Contoh 1: {{ Tambahkan judul di sini }}
```powershell
PS C:\> {{ Add code here }}

{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

### Contoh 2: {{ Tambahkan judul di sini }}
```powershell
PS C:\> {{ Add code here }}

{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.IMigrateIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat vault layanan pemulihan ada.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceName
Nama vault layanan pemulihan.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Id Langganan Azure tempat proyek migrasi dibuat.

```yaml
Type: System.String[]
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultSettingName
Nama pengaturan vault.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.IMigrateIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVaultSetting

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IMigrateIdentity>`: Parameter Identitas
  - `[AccountName <String>]`: Jalankan sebagai nama ARM akun.
  - `[AlertSettingName <String>]`: Nama konfigurasi pemberitahuan email.
  - `[ClusterName <String>]`: Nama ARM kluster.
  - `[DatabaseInstanceName <String>]`: Nama unik instans database di hub migrasi Azure.
  - `[DatabaseName <String>]`: Nama unik database di hub migrasi Azure.
  - `[EventName <String>]`: Nama unik peristiwa dalam proyek migrasi.
  - `[FabricName <String>]`: Nama fabric.
  - `[HostName <String>]`: Nama ARM host.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[IntentObjectName <String>]`: Nama niat perlindungan replikasi.
  - `[JobName <String>]`: Nama ARM pekerjaan.
  - `[LogicalNetworkName <String>]`: Nama jaringan logis.
  - `[MachineName <String>]`: Nama ARM mesin.
  - `[MappingName <String>]`: Nama pemetaan Kontainer Perlindungan.
  - `[MigrateProjectName <String>]`: Nama proyek Azure Migrate.
  - `[MigrationItemName <String>]`: Nama item migrasi.
  - `[MigrationRecoveryPointName <String>]`: Nama titik pemulihan migrasi.
  - `[NetworkMappingName <String>]`: Nama pemetaan jaringan.
  - `[NetworkName <String>]`: Nama jaringan utama.
  - `[OperationStatusName <String>]`: Status operasi nama ARM.
  - `[PolicyName <String>]`: Nama kebijakan replikasi.
  - `[ProtectableItemName <String>]`: Nama item yang dapat dilindungi.
  - `[ProtectionContainerName <String>]`: Nama kontainer perlindungan.
  - `[ProviderName <String>]`: Nama penyedia layanan pemulihan.
  - `[RecoveryPlanName <String>]`: Nama rencana pemulihan.
  - `[RecoveryPointName <String>]`: Nama titik pemulihan.
  - `[ReplicatedProtectedItemName <String>]`: Nama item yang dilindungi replikasi.
  - `[ReplicationProtectedItemName <String>]`: Nama item yang dilindungi tempat agen akan diperbarui.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[ResourceName <String>]`: Nama vault layanan pemulihan.
  - `[SiteName <String>]`: Nama situs.
  - `[SolutionName <String>]`: Nama unik solusi migrasi dalam proyek migrasi.
  - `[StorageClassificationMappingName <String>]`: Storage nama pemetaan klasifikasi.
  - `[StorageClassificationName <String>]`: Storage nama klasifikasi.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VaultSettingName <String>]`: Nama pengaturan vault.
  - `[VcenterName <String>]`: Nama ARM VCenter Server.
  - `[VirtualMachineName <String>]`: Nama Komputer Virtual.

## RELATED LINKS

