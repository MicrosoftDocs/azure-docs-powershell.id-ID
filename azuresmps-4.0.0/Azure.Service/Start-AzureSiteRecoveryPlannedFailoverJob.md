---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 2575F5C4-A276-49CE-AB0C-726F359DA6F9
online version: ''
schema: 2.0.0
ms.openlocfilehash: 37eb0368d66528cb07648c6286bf7c1f9bac8cb3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141965983"
---
# Start-AzureSiteRecoveryPlannedFailoverJob

## SYNOPSIS
Memulai operasi failover yang direncanakan Site Recovery.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByRPId (Default)
```
Start-AzureSiteRecoveryPlannedFailoverJob -RPId <String> -Direction <String> [-WaitForCompletion]
 [-Optimize <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByPEId
```
Start-AzureSiteRecoveryPlannedFailoverJob -ProtectionEntityId <String> -ProtectionContainerId <String>
 -Direction <String> [-WaitForCompletion] [-Optimize <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByRPObject
```
Start-AzureSiteRecoveryPlannedFailoverJob -RecoveryPlan <ASRRecoveryPlan> -Direction <String>
 [-WaitForCompletion] [-Optimize <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByPEObject
```
Start-AzureSiteRecoveryPlannedFailoverJob -ProtectionEntity <ASRProtectionEntity> -Direction <String>
 [-WaitForCompletion] [-Optimize <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureSiteRecoveryPlannedFailoverJob** memulai failover yang direncanakan untuk entitas perlindungan Site Recovery Azure atau rencana pemulihan.
Anda dapat memeriksa apakah pekerjaan berhasil menggunakan cmdlet **Get-AzureSiteRecoveryJob** .

## EXAMPLES

### Contoh 1: Memulai pekerjaan failover yang direncanakan
```
PS C:\> $Container = Get-AzureSiteRecoveryProtectionContainer 
PS C:\> $Protected = Get-AzureSiteRecoveryProtectionEntity -ProtectionContainer $Container 
PS C:\> Start-AzureSiteRecoveryPlannedFailoverJob -Direction PrimaryToRecovery -ProtectionEntity $Protected -Optimize ForDowntime
ID               : c38eecdc-731c-405b-a61c-08db99aae2fe
ClientRequestId  : 32ace403-0916-4967-83a1-529176bd6e88-2014-49-06 15:49:24Z-P
State            : NotStarted
StateDescription : NotStarted
StartTime        : 
EndTime          : 
AllowedActions   : {}
Name             : 
Tasks            : {}
Errors           : {}
```

Perintah pertama mendapatkan semua kontainer yang dilindungi di azure saat ini Site Recovery kubah dengan menggunakan cmdlet **Get-AzureSiteRecoveryProtectionContainer**, lalu menyimpan hasilnya dalam variabel $Container.
Dalam contoh ini, ada satu wadah.

Perintah kedua mendapatkan mesin virtual yang dilindungi milik wadah yang disimpan di $Container menggunakan cmdlet **Get-AzureSiteRecoveryProtectionEntity** .
Perintah menyimpan hasil dalam variabel $Protected.

Perintah akhir memulai pekerjaan failover ke arah PrimaryToRecovery untuk mesin virtual terproteksi yang disimpan di $Protected.

## PARAMETERS

### -Arah
Menentukan arah failover.
Nilai yang dapat diterima untuk parameter ini adalah:

- PrimaryToRecovery
- PemulihanToPrimary

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Optimize
Menentukan apa yang harus dioptimalkan.
Parameter ini berlaku untuk failover dari situs Azure ke situs lokal yang memerlukan sinkronisasi data yang signifikan.
Nilai yang dapat diterima untuk parameter ini adalah:

- Untuk Waktu Henti
- ForSynchronization

Ketika **ForDowntime** ditentukan, ini menunjukkan bahwa data disinkronkan sebelum failover untuk meminimalkan waktu henti.
Sinkronisasi dilakukan tanpa mematikan mesin virtual.
Setelah sinkronisasi selesai, pekerjaan ditangguhkan.
Lanjutkan pekerjaan untuk melakukan operasi sinkronisasi tambahan yang mematikan mesin virtual.

Ketika **ForSynchronization** ditentukan, ini menunjukkan bahwa data hanya disinkronkan selama failover sehingga sinkronisasi data diminimalkan.
Karena pengaturan ini diaktifkan, mesin virtual segera dimatikan.
Sinkronisasi dimulai setelah shutdown untuk menyelesaikan operasi failover.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionContainerId
Menentukan ID wadah yang dilindungi untuk memulai pekerjaan.

```yaml
Type: String
Parameter Sets: ByPEId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionEntity
Menentukan objek entitas perlindungan Site Recovery.

```yaml
Type: ASRProtectionEntity
Parameter Sets: ByPEObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionEntityId
Menentukan objek **ASRProtectionEntity** untuk memulai pekerjaan.
Untuk mendapatkan objek **ASRProtectionEntity** , gunakan cmdlet **Get-AzureSiteRecoveryProtectionEntity** .

```yaml
Type: String
Parameter Sets: ByPEId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPlan
Menentukan objek rencana pemulihan.

```yaml
Type: ASRRecoveryPlan
Parameter Sets: ByRPObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RPId
Menentukan ID rencana pemulihan untuk memulai pekerjaan.

```yaml
Type: String
Parameter Sets: ByRPId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForCompletion
Menunjukkan bahwa cmdlet menunggu operasi selesai sebelum mengembalikan kontrol ke konsol Windows PowerShell.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoveryProtectionContainer](./Get-AzureSiteRecoveryProtectionContainer.md)

[Get-AzureSiteRecoveryProtectionEntity](./Get-AzureSiteRecoveryProtectionEntity.md)


