---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/start-azrecoveryservicesasrplannedfailoverjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Start-AzRecoveryServicesAsrPlannedFailoverJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Start-AzRecoveryServicesAsrPlannedFailoverJob.md
ms.openlocfilehash: 8bae2a884dd1d0fb14c8c7535989545185c1e244
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136564127"
---
# Start-AzRecoveryServicesAsrPlannedFailoverJob

## SYNOPSIS
Memulai operasi failover yang direncanakan.

## SYNTAX

### ByRPIObject (Default)
```
Start-AzRecoveryServicesAsrPlannedFailoverJob -ReplicationProtectedItem <ASRReplicationProtectedItem>
 -Direction <String> [-Optimize <String>] [-CreateVmIfNotFound <String>]
 [-ServicesProvider <ASRRecoveryServicesProvider>] [-DataEncryptionPrimaryCertFile <String>]
 [-DataEncryptionSecondaryCertFile <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByRPObject
```
Start-AzRecoveryServicesAsrPlannedFailoverJob -RecoveryPlan <ASRRecoveryPlan> -Direction <String>
 [-Optimize <String>] [-CreateVmIfNotFound <String>] [-DataEncryptionPrimaryCertFile <String>]
 [-DataEncryptionSecondaryCertFile <String>] [-MultiVmSyncPoint <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByRPIObjectWithRecoveryTag
```
Start-AzRecoveryServicesAsrPlannedFailoverJob -ReplicationProtectedItem <ASRReplicationProtectedItem>
 -Direction <String> [-Optimize <String>] [-CreateVmIfNotFound <String>]
 [-DataEncryptionPrimaryCertFile <String>] [-DataEncryptionSecondaryCertFile <String>] -RecoveryTag <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzRecoveryServicesAsrPlannedFailoverJob** memulai failover yang direncanakan untuk item terproteksi replikasi Situs Azure atau paket pemulihan.
Anda dapat memeriksa apakah pekerjaan berhasil dengan menggunakan cmdlet Get-AzRecoveryServicesAsrJob.

## EXAMPLES

### Contoh 1
```
PS C:\> $currentJob = Start-AzRecoveryServicesAsrPlannedFailoverJob -RecoveryPlan $RP -Direction PrimaryToRecovery
```

Memulai failover yang direncanakan untuk paket pemulihan ASR tertentu dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

## PARAMETERS

### -CreateVmIfNotFound
Buat mesin virtual jika tidak ditemukan saat gagal kembali ke kawasan utama (digunakan di pemulihan lokasi alternatif.) Nilai yang dapat diterima untuk parameter ini adalah:

- Ya
- Tidak

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Yes, No

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataEncryptionPrimaryCertFile
Menentukan file sertifikat utama.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataEncryptionSeccryptryCertFile
Menentukan file sertifikat sekunder.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.


```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Arah
Menentukan arah failover.
Nilai yang dapat diterima untuk parameter ini adalah:

- PrimaryToRecovery
- PemulihanToPrimary

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: PrimaryToRecovery, RecoveryToPrimary

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MultiVmSyncPoint
Menentukan apakah akan mengaktifkan poin sinkronisasi multi VM untuk failover dari VM sync multi VM yang diaktifkan (Hanya berlaku untuk skenario replikasi VMware ke Azure).

```yaml
Type: System.String
Parameter Sets: ByRPObject
Aliases:
Accepted values: Enable, Disable

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Optimize
Menentukan apa yang akan dioptimalkan.
Parameter ini berlaku ketika failover dilakukan dari situs Azure ke situs lokal yang memerlukan sinkronisasi data penting.
Nilai valid adalah:

- ForDowntime
- ForSynchronization

Saat **ForDowntime** ditentukan, ini menunjukkan bahwa data disinkronkan sebelum failover untuk meminimalkan waktu henti.
Sinkronisasi dilakukan tanpa mematikan mesin virtual.
Setelah sinkronisasi selesai, pekerjaan ditangguhkan.
Lanjutkan pekerjaan untuk melakukan operasi sinkronisasi tambahan yang mematikan mesin virtual.

Saat **ForSynchronization** ditentukan, ini menunjukkan bahwa data disinkronkan selama failover saja sehingga sinkronisasi data diminimalkan.
Dengan pengaturan ini diaktifkan, mesin virtual akan langsung mematikan.
Sinkronisasi dimulai setelah penutupan untuk menyelesaikan operasi failover.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ForDownTime, ForSynchronization

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPlan
Menentukan objek paket Pemulihan ASR yang terkait dengan rencana pemulihan yang akan gagal berakhir.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRRecoveryPlan
Parameter Sets: ByRPObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryTag
Menentukan tag pemulihan: RecoveryTagApplicationConsistent, RecoveryTagCrashConsistent (Hanya berlaku untuk VMware ke skenario replikasi Azure).

```yaml
Type: System.String
Parameter Sets: ByRPIObjectWithRecoveryTag
Aliases:
Accepted values: RecoveryTagApplicationConsistent, RecoveryTagCrashConsistent

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationProtectedItem
Menentukan objek item dilindungi replikasi ASR yang terkait dengan item replikasi yang diproteksi yang akan gagal atas.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRReplicationProtectedItem
Parameter Sets: ByRPIObject, ByRPIObjectWithRecoveryTag
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServicesProvider
Mengidentifikasi host untuk membuat mesin virtual saat kegagalan ke lokasi alternatif dengan menentukan objek penyedia layanan ASR terkait dengan penyedia layanan ASR yang berjalan pada host.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRRecoveryServicesProvider
Parameter Sets: ByRPIObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRRecoveryPlan

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRReplicationProtectedItem

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRJob

## CATATAN

## RELATED LINKS
