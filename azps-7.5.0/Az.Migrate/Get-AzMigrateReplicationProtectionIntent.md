---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/get-azmigratereplicationprotectionintent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateReplicationProtectionIntent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateReplicationProtectionIntent.md
ms.openlocfilehash: 35320ce5e394624b6781bcf2774e043ddd66267d
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144112018"
---
# Get-AzMigrateReplicationProtectionIntent

## SYNOPSIS
Mendapatkan detail niat perlindungan replikasi ASR.

## SYNTAX

### Daftar (Default)
```
Get-AzMigrateReplicationProtectionIntent -ResourceGroupName <String> -ResourceName <String>
 [-SubscriptionId <String[]>] [-SkipToken <String>] [-TakeToken <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzMigrateReplicationProtectionIntent -IntentObjectName <String> -ResourceGroupName <String>
 -ResourceName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzMigrateReplicationProtectionIntent -InputObject <IMigrateIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail niat perlindungan replikasi ASR.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -IntentObjectName
Nama niat perlindungan replikasi.

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

### -SkipToken
Token penomoran halaman.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
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

### -TakeToken
Ukuran halaman.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
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

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IReplicationProtectionIntent

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMigrateIdentity>: Parameter Identitas
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
  - `[OperationStatusName <String>]`: Nama ARM status operasi.
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

