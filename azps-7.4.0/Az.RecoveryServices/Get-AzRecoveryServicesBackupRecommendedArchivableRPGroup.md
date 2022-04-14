---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackuprecommendedarchivablerpgroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupRecommendedArchivableRPGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupRecommendedArchivableRPGroup.md
ms.openlocfilehash: 7893fe0c19fe0fe6e8bb7da30f4ee83f141ed5d4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142175227"
---
# Get-AzRecoveryServicesBackupRecommendedArchivableRPGroup

## SYNOPSIS
Dapatkan poin pemulihan yang direkomendasikan untuk dipindahkan bersama-sama ke tingkat VaultArchive.

## SYNTAX

```
Get-AzRecoveryServicesBackupRecommendedArchivableRPGroup [-Item] <ItemBase> [-VaultId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Get-AzRecoveryServicesBackupRecommendedArchivableRPGroup** mendapatkan titik pemulihan yang direkomendasikan untuk dipindahkan ke tingkat VaultArchive.
Titik pemulihan ini ketika dipindahkan bersama-sama akan menghasilkan penghematan maksimum.

## EXAMPLES

### Contoh 1: Ambil rp yang direkomendasikan untuk dipindahkan ke tingkat VaultArchive
```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$item = Get-AzRecoveryServicesBackupItem -BackupManagementType "AzureVM" -WorkloadType "AzureVM" -VaultId $vault.ID
$rpGroup = Get-AzRecoveryServicesRecommendedArchivableRPGroup -Item $item[3] -VaultId $vault.ID
```

Di sini kami menggunakan **cmdlet Get-AzRecoveryServicesRecommendedArchivableRPGroup** untuk mengambil daftar RPs yang direkomendasikan untuk dipindahkan ke tingkat VaultArchive dan menetapkan ke $rpGroup. 

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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.RecoveryPointBase

## CATATAN

## RELATED LINKS
