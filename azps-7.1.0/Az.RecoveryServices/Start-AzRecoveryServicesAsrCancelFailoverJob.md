---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/start-azrecoveryservicesasrcancelfailoverjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Start-AzRecoveryServicesAsrCancelFailoverJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Start-AzRecoveryServicesAsrCancelFailoverJob.md
ms.openlocfilehash: 60c287de2a13df639c613c766bdc9777b8e5f490
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136758651"
---
# Start-AzRecoveryServicesAsrCancelFailoverJob

## SYNOPSIS
Memulai tindakan membatalkan failover untuk objek Pemulihan Situs.

## SYNTAX

### ByRPIObject (Default)
```
Start-AzRecoveryServicesAsrCancelFailoverJob -ReplicationProtectedItem <ASRReplicationProtectedItem>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByRPObject
```
Start-AzRecoveryServicesAsrCancelFailoverJob -RecoveryPlan <ASRRecoveryPlan>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzRecoveryServicesAsrCancelFailoverJob** memulai proses pembatalan failover untuk objek Pemulihan Situs Azure.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $currentJob = Start-AzRecoveryServicesAsrCancelFailoverJob -RecoveryPlan $RP
```

Memulai failover pembatalan untuk paket pemulihan tertentu dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

### Contoh 2

Memulai tindakan membatalkan failover untuk objek Pemulihan Situs. (otomatisgenerated)

```powershell
<!-- Aladdin Generated Example --> 
Start-AzRecoveryServicesAsrCancelFailoverJob -ReplicationProtectedItem $ReplicationProtectedItem
```

## PARAMETERS

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

### -RecoveryPlan
Menentukan objek paket pemulihan ASR yang terkait dengan paket pemulihan akan failover.

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

### -ReplicationProtectedItem
Menentukan objek item dilindungi replikasi ASR yang terkait dengan replikasi item yang diproteksi untuk failover.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRReplicationProtectedItem
Parameter Sets: ByRPIObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
