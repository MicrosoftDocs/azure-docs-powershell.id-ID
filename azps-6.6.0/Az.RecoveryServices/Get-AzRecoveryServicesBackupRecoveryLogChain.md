---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackuprecoverylogchain
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupRecoveryLogChain.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupRecoveryLogChain.md
ms.openlocfilehash: 2d77659c1379703265abee18f8c31b57859642e7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142771624"
---
# Get-AzRecoveryServicesBackupRecoveryLogChain

## SYNOPSIS
Perintah ini mencantumkan titik mulai dan titik akhir rantai log yang tidak terpotong dari item cadangan yang diberikan. Gunakan untuk menentukan apakah point-in-time, tempat pengguna ingin memulihkan DB, valid atau tidak.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/get-azrecoveryservicesbackuprecoverylogchain) untuk informasi terbaru.

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
Cmdlet **Get-AzRecoveryServicesBackupRecoveryLogChain** mendapatkan titik pemulihan rentang waktu tepat waktu untuk item Azure Backup yang dicadangkan.
Setelah item dicadangkan, objek **AzRecoveryServicesBackupRecoveryLogChain** memiliki satu atau beberapa rentang waktu pemulihan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $StartDate = (Get-Date).AddDays(-7) 
PS C:\> $EndDate = Get-Date 
PS C:\> $Container = Get-AzRecoveryServicesBackupContainer -ContainerType AzureWorkload -Status Registered
PS C:\> $RP = Get-AzRecoveryServicesBackupItem -Container $Container -WorkloadType MSSQL | Get-AzRecoveryServicesBackupRecoveryLogChain -StartDate $Startdate.ToUniversalTime() -EndDate $Enddate.ToUniversalTime()
```

Perintah pertama mendapatkan tanggal dari tujuh hari yang lalu, lalu menyimpannya dalam variabel $StartDate.
Perintah kedua mendapatkan tanggal hari ini, lalu menyimpannya dalam variabel $EndDate.
Perintah ketiga mendapatkan wadah cadangan AzureWorkload, dan menyimpannya dalam variabel $Container.
Perintah keempat mendapatkan item cadangan, lalu membagikannya di seluruh cmdlet piped sebagai objek item cadangan.
Perintah terakhir mendapatkan array rentang waktu titik pemulihan untuk item dalam $BackupItem, lalu menyimpannya dalam variabel $RP.

### Contoh 2

Perintah ini mencantumkan titik mulai dan titik akhir rantai log yang tidak terpotong dari item cadangan yang diberikan. (autogenerasi)

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
Waktu akhir rentang Waktu yang titik pemulihannya perlu didapatkan

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
Objek Item Terproteksi yang titik pemulihannya perlu didapatkan

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
Waktu mulai rentang Waktu yang titik pemulihannya perlu didapatkan

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
Filter dari Kawasan Sekunder untuk Pemulihan Lintas Kawasan

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
ARM ID dari Vault Layanan Pemulihan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ItemBase
System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

## NOTES

## RELATED LINKS
