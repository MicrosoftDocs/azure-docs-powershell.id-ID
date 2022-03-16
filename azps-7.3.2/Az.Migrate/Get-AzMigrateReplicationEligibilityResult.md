---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/get-azmigratereplicationeligibilityresult
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateReplicationEligibilityResult.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateReplicationEligibilityResult.md
ms.openlocfilehash: 793ad3f4f7afc252885b559df3055dad8c1138c8
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140000245"
---
# Get-AzMigrateReplicationEligibilityResult

## SYNOPSIS
Memvalidasi apakah VM yang diberikan dapat dilindungi atau tidak, dalam hal ini, daftar kesalahan akan dikembalikan.

## SYNTAX

### Dapatkan (Default)
```
Get-AzMigrateReplicationEligibilityResult -ResourceGroupName <String> -VirtualMachineName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzMigrateReplicationEligibilityResult -InputObject <IMigrateIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar
```
Get-AzMigrateReplicationEligibilityResult -ResourceGroupName <String> -VirtualMachineName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Memvalidasi apakah VM yang diberikan dapat dilindungi atau tidak, dalam hal ini, daftar kesalahan akan dikembalikan.

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -VirtualMachineName
Nama Mesin Virtual.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.IMigrateIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IReplicationEligibilityResults

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMigrateIdentity>: Parameter Identitas
  - `[AccountName <String>]`: Jalankan sebagai nama arm akun.
  - `[AlertSettingName <String>]`: Nama konfigurasi pemberitahuan email.
  - `[ClusterName <String>]`: Nama ARM kluster.
  - `[DatabaseInstanceName <String>]`: Nama unik contoh database di hub migrasi Azure.
  - `[DatabaseName <String>]`: Nama unik database di hub migrasi Azure.
  - `[EventName <String>]`: Nama unik acara dalam proyek migrasi.
  - `[FabricName <String>]`: Fabric name.
  - `[HostName <String>]`: Nama host ARM.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[IntentObjectName <String>]`: Nama tujuan proteksi replikasi.
  - `[JobName <String>]`: Nama ARM pekerjaan.
  - `[LogicalNetworkName <String>]`: Nama jaringan logis.
  - `[MachineName <String>]`: Nama ARM mesin.
  - `[MappingName <String>]`: Proteksi Container mapping name.
  - `[MigrateProjectName <String>]`: Nama proyek Azure Migrate.
  - `[MigrationItemName <String>]`: Nama item migrasi.
  - `[MigrationRecoveryPointName <String>]`: Nama titik pemulihan migrasi.
  - `[NetworkMappingName <String>]`: Nama pemetaan jaringan.
  - `[NetworkName <String>]`: Nama jaringan utama.
  - `[OperationStatusName <String>]`: Nama ARM status operasi.
  - `[PolicyName <String>]`: Nama kebijakan replikasi.
  - `[ProtectableItemName <String>]`: Nama item yang dapat diproteksi.
  - `[ProtectionContainerName <String>]`: Nama wadah proteksi.
  - `[ProviderName <String>]`: Nama penyedia layanan pemulihan.
  - `[RecoveryPlanName <String>]`: Nama paket pemulihan.
  - `[RecoveryPointName <String>]`: Nama titik pemulihan.
  - `[ReplicatedProtectedItemName <String>]`: Replikasi nama item yang diproteksi.
  - `[ReplicationProtectedItemName <String>]`: Nama item terlindungi tempat agen akan diperbarui.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[ResourceName <String>]`: Nama vault layanan pemulihan.
  - `[SiteName <String>]`: Nama situs.
  - `[SolutionName <String>]`: Nama unik solusi migrasi dalam proyek migrasi.
  - `[StorageClassificationMappingName <String>]`: Storage pemetaan klasifikasi.
  - `[StorageClassificationName <String>]`: Storage klasifikasi.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VaultSettingName <String>]`: Nama pengaturan Vault.
  - `[VcenterName <String>]`: VCenter NAMA ARM.
  - `[VirtualMachineName <String>]`: Nama Mesin Virtual.

## RELATED LINKS

