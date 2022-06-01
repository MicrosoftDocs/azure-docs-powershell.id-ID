---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupstatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesBackupStatus.md
ms.openlocfilehash: 4eb3b3c57bf50d238c01be210aecc6d131596aac
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145976809"
---
# Get-AzRecoveryServicesBackupStatus

## SYNOPSIS
Memeriksa apakah sumber daya ARM Anda dicadangkan atau tidak.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/get-azrecoveryservicesbackupstatus) untuk informasi terbaru.

## SYNTAX

### Nama (Default)
```
Get-AzRecoveryServicesBackupStatus -Name <String> -ResourceGroupName <String> -Type <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### IdWorkload
```
Get-AzRecoveryServicesBackupStatus -Type <String> -ResourceId <String> -ProtectableObjectName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Id
```
Get-AzRecoveryServicesBackupStatus -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Perintah mengembalikan null/kosong jika sumber daya yang ditentukan tidak dilindungi di bawah vault Layanan Pemulihan apa pun dalam langganan.
Jika dilindungi, detail vault yang relevan akan dikembalikan.

## EXAMPLES

### Contoh 1

Memeriksa apakah sumber daya ARM Anda dicadangkan atau tidak. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Get-AzRecoveryServicesBackupStatus -Name 'myAzureVM' -ResourceGroupName 'myAzureVMRG' -Type AzureVM
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

### -Name
Nama Sumber Daya Azure yang item perwakilannya perlu diperiksa apakah sudah dilindungi oleh beberapa Vault Layanan Pemulihan dalam langganan.

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectableObjectName
Nama Sumber Daya Azure yang item perwakilannya perlu diperiksa apakah sudah dilindungi oleh beberapa Vault Layanan Pemulihan dalam langganan.

```yaml
Type: System.String
Parameter Sets: IdWorkload
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya Sumber Daya Azure yang item perwakilannya perlu diperiksa apakah sudah dilindungi oleh beberapa RecoveryServices Vault dalam langganan.

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID Sumber Daya Azure yang item perwakilannya perlu diperiksa apakah sudah dilindungi oleh beberapa RecoveryServices Vault dalam langganan.

```yaml
Type: System.String
Parameter Sets: IdWorkload, Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
Jenis Sumber Daya Azure yang item perwakilannya perlu diperiksa apakah sudah dilindungi oleh beberapa Vault Layanan Pemulihan dalam langganan.

```yaml
Type: System.String
Parameter Sets: Name, IdWorkload
Aliases:
Accepted values: AzureVM, AzureFiles

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.ResourceBackupStatus

## NOTES

## RELATED LINKS
