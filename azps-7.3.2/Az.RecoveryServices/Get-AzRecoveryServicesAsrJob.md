---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesasrjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesAsrJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesAsrJob.md
ms.openlocfilehash: 440293c2e4c15b94981fdfa16c2bd104972b0de9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143240759"
---
# Get-AzRecoveryServicesAsrJob

## SYNOPSIS
Mendapatkan detail pekerjaan ASR yang ditentukan atau daftar pekerjaan ASR terbaru dalam kubah Layanan Pemulihan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/get-azrecoveryservicesasrjob) untuk informasi terbaru.

## SYNTAX

### ByParam (Default)
```
Get-AzRecoveryServicesAsrJob [-StartTime <DateTime>] [-EndTime <DateTime>] [-TargetObjectId <String>]
 [-State <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByName
```
Get-AzRecoveryServicesAsrJob -Name <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByObject
```
Get-AzRecoveryServicesAsrJob -Job <ASRJob> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzRecoveryServicesAsrJob** mendapatkan pekerjaan Azure Site Recovery.
Anda dapat menggunakan cmdlet ini untuk melihat pekerjaan ASR dalam kubah Layanan Pemulihan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $jobs = Get-AzRecoveryServicesAsrJob -TargetObjectId $ASRObjectId
```

Mengembalikan semua pekerjaan pada objek ASR tertentu(mereferensikan objek ASR seperti item yang direplikasi atau rencana pemulihan menurut ID-nya.) 

### Contoh 2

Mendapatkan detail pekerjaan ASR yang ditentukan atau daftar pekerjaan ASR terbaru dalam kubah Layanan Pemulihan. (autogenerasi)

```powershell <!-- Aladdin Generated Example --> 
Get-AzRecoveryServicesAsrJob -Job $Job
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

### -EndTime
Menentukan waktu akhir untuk pekerjaan.
Cmdlet ini mendapatkan semua pekerjaan yang dimulai sebelum waktu yang ditentukan.
Untuk mendapatkan objek **DateTime** untuk parameter ini, gunakan cmdlet Get-Date.
Untuk informasi selengkapnya, ketik .`Get-Help Get-Date`

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: ByParam
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Menentukan objek pekerjaan ASR untuk mendapatkan detail yang diperbarui.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRJob
Parameter Sets: ByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Tentukan tugas ASR menurut nama.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Menentukan waktu mulai untuk pekerjaan.
Cmdlet ini mendapatkan semua pekerjaan yang dimulai setelah waktu yang ditentukan.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: ByParam
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Negara Bagian
Menentukan status untuk pekerjaan ASR.
Cmdlet ini mendapatkan semua pekerjaan yang sesuai dengan status yang ditentukan.
Nilai yang dapat diterima untuk parameter ini adalah:

- NotStarted
- InProgress
- Berhasil
- Lain
- Gagal
- Dibatalkan
- Ditangguhkan

```yaml
Type: System.String
Parameter Sets: ByParam
Aliases:
Accepted values: NotStarted, InProgress, Succeeded, Other, Failed, Cancelled, Suspended

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetObjectId
Menentukan ID objek. Digunakan untuk mencari pekerjaan pada objek yang ditentukan.

```yaml
Type: System.String
Parameter Sets: ByParam
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRJob

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRJob

## NOTES

## RELATED LINKS

[Mulai ulang-AzRecoveryServicesAsrJob](./Restart-AzRecoveryServicesAsrJob.md)

[Resume-AzRecoveryServicesAsrJob](./Resume-AzRecoveryServicesAsrJob.md)

[Stop-AzRecoveryServicesAsrJob](./Stop-AzRecoveryServicesAsrJob.md)
