---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackuprecoverylogchain
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupRecoveryLogChain.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupRecoveryLogChain.md
ms.openlocfilehash: faea62b3dbd7bdb1ee477955203e1375804cb627
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145553348"
---
# Get-AzRecoveryServicesBackupRecoveryLogChain

## SYNOPSIS
Perintah ini mencantumkan titik awal dan akhir dari rantai log yang tidak terganggu dari item cadangan yang diberikan. Gunakan untuk menentukan apakah titik waktu, di mana pengguna ingin DB dipulihkan, valid atau tidak.

## SYNTAX

### NoFilterParameterSet (Default)
```
Get-AzRecoveryServicesBackupRecoveryLogChain [-Item] <ItemBase> [-UseSecondaryRegion] [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### DateTimeFilter
```
Get-AzRecoveryServicesBackupRecoveryLogChain [[-StartDate] <DateTime>] [[-EndDate] <DateTime>]
 [-Item] <ItemBase> [-UseSecondaryRegion] [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzRecoveryServicesBackupRecoveryLogChain** mendapatkan titik pemulihan rentang waktu untuk item Azure Backup yang dicadangkan.
Setelah item dicadangkan, objek **AzRecoveryServicesBackupRecoveryLogChain** memiliki satu atau beberapa rentang waktu pemulihan.

## EXAMPLES

### Contoh 1
```powershell
$StartDate = (Get-Date).AddDays(-7) 
$EndDate = Get-Date 
$Container = Get-AzRecoveryServicesBackupContainer -ContainerType AzureWorkload -Status Registered
$RP = Get-AzRecoveryServicesBackupItem -Container $Container -WorkloadType MSSQL | Get-AzRecoveryServicesBackupRecoveryLogChain -StartDate $Startdate.ToUniversalTime() -EndDate $Enddate.ToUniversalTime()
```

Perintah pertama mendapatkan tanggal dari tujuh hari yang lalu, lalu menyimpannya dalam variabel $StartDate.
Perintah kedua mendapatkan tanggal hari ini, lalu menyimpannya dalam variabel $EndDate.
Perintah ketiga mendapatkan kontainer cadangan AzureWorkload, dan menyimpannya dalam variabel $Container.
Perintah keempat mendapatkan item cadangan, lalu membagikannya di seluruh cmdlet yang disalurkan sebagai objek item cadangan.
Perintah terakhir mendapatkan array rentang waktu titik pemulihan untuk item dalam $BackupItem, lalu menyimpannya dalam variabel $RP.

### Contoh 2

Perintah ini mencantumkan titik awal dan akhir dari rantai log yang tidak terganggu dari item cadangan yang diberikan. (dibuat otomatis)

```powershell
<!-- Aladdin Generated Example --> 
Get-AzRecoveryServicesBackupRecoveryLogChain -Item $Item -VaultId $vault.ID
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

### -EndDate
Waktu akhir rentang Waktu yang titik pemulihannya perlu diambil

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: DateTimeFilter
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Item
Objek Item Terproteksi yang titik pemulihannya perlu diambil

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemBase
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StartDate
Waktu mulai rentang Waktu yang titik pemulihannya perlu diambil

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: DateTimeFilter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSecondaryRegion
Filter dari Wilayah Sekunder untuk Pemulihan Lintas Wilayah

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultId
ID ARM dari Vault Layanan Pemulihan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemBase
System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

## NOTES

## RELATED LINKS
