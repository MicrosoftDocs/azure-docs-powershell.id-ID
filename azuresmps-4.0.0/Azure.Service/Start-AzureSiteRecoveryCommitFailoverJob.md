---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 44A22B6C-5FD4-43B0-9726-71E28AE53E9D
online version: ''
schema: 2.0.0
ms.openlocfilehash: 7b4f64f6605f37545189711ad23a2c6052330a2655642f02b659d8a7f36fcb06
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417693"
---
# Start-AzureSiteRecoveryCommitFailoverJob

## SYNOPSIS
Memulai tindakan lakukan failover untuk objek Pemulihan Situs.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByRPId (Default)
```
Start-AzureSiteRecoveryCommitFailoverJob -RPId <String> [-Direction <String>] [-WaitForCompletion]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByPEId
```
Start-AzureSiteRecoveryCommitFailoverJob -ProtectionEntityId <String> -ProtectionContainerId <String>
 [-Direction <String>] [-WaitForCompletion] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByRPObject
```
Start-AzureSiteRecoveryCommitFailoverJob -RecoveryPlan <ASRRecoveryPlan> [-Direction <String>]
 [-WaitForCompletion] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByPEObject
```
Start-AzureSiteRecoveryCommitFailoverJob -ProtectionEntity <ASRProtectionEntity> [-Direction <String>]
 [-WaitForCompletion] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureSiteRecoveryCommitFailoverJob** memulai proses commit failover untuk objek Pemulihan Situs Azure setelah operasi failover.

## EXAMPLES

### Contoh 1: Mulai pekerjaan failover commit
```
PS C:\> $Container = Get-AzureSiteRecoveryProtectionContainer 
PS C:\> $Protected = Get-AzureSiteRecoveryProtectionEntity -ProtectionContainer $Container 
PS C:\> Start-AzureSiteRecoveryCommitFailoverJob -ProtectionEntity $Protected
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

Perintah pertama mendapatkan semua wadah yang diproteksi untuk vault Pemulihan Situs Azure saat ini menggunakan cmdlet **Get-AzureSiteRecoveryProtectionContainer,** lalu menyimpan hasil dalam $Container baru.

Perintah kedua mendapatkan mesin virtual terlindungi yang termasuk dalam wadah yang disimpan di $Container dengan menggunakan cmdlet **Get-AzureSiteRecoveryProtectionEntity.**
Perintah menyimpan hasil dalam $Protected variabel.

Perintah terakhir memulai pekerjaan failover untuk objek dilindungi yang disimpan di $Protected.

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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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
Menentukan ID dari wadah yang diproteksi.
Cmdlet ini memulai pekerjaan untuk mesin virtual terlindungi yang termasuk dalam wadah yang ditentukan cmdlet ini.

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
Menentukan objek **ASRProtectionEntity** untuk memulai pekerjaan.
Untuk mendapatkan objek **ASRProtectionEntity,** gunakan cmdlet **Get-AzureSiteRecoveryProtectionEntity.**

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
Menentukan ID mesin virtual yang diproteksi untuk memulai pekerjaan.

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
Menentukan objek paket pemulihan yang akan digunakan untuk memulai pekerjaan.
Untuk mendapatkan objek **ASRRecoveryPlan,** gunakan cmdlet **Get-AzureSiteRecoveryRecoveryPlan.**

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
Menentukan ID paket pemulihan yang akan digunakan untuk memulai pekerjaan.

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
Menunjukkan bahwa cmdlet menunggu hingga operasi selesai sebelum mengembalikan kontrol ke Windows PowerShell baru.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoveryRecoveryPlan](./Get-AzureSiteRecoveryRecoveryPlan.md)

[Get-AzureSiteRecoveryProtectionContainer](./Get-AzureSiteRecoveryProtectionContainer.md)

[Get-AzureSiteRecoveryProtectionEntity](./Get-AzureSiteRecoveryProtectionEntity.md)


