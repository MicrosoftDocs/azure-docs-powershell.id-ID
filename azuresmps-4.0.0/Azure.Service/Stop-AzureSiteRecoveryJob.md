---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 8FF1362B-C7AB-4769-A88B-D1B6E214A006
online version: ''
schema: 2.0.0
ms.openlocfilehash: c6683b0300ab610f9cba6b3b201546287e616fcb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142243189"
---
# Stop-AzureSiteRecoveryJob

## SYNOPSIS
Menghentikan pekerjaan Site Recovery.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByObject (Default)
```
Stop-AzureSiteRecoveryJob -Job <ASRJob> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ById
```
Stop-AzureSiteRecoveryJob -Id <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Stop-AzureSiteRecoveryJob** menghentikan pekerjaan azure Site Recovery.

## EXAMPLES

### Contoh 1: Hentikan semua pekerjaan
```
PS C:\>$Jobs = Get-AzureSiteRecoveryJob 
PS C:\> Stop-AzureSiteRecoveryJob -Job $Jobs
```

Perintah pertama mendapatkan pekerjaan Azure Site Recovery untuk brankas Azure Site Recovery saat ini menggunakan cmdlet **Get-AzureSiteRecoveryJob**, lalu menyimpan hasilnya dalam variabel $Jobs.

Perintah kedua menghentikan pekerjaan yang ditentukan oleh $Jobs.

## PARAMETERS

### -Id
Menentukan ID pekerjaan yang akan dihentikan.

```yaml
Type: String
Parameter Sets: ById
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Menentukan tugas yang akan dihentikan.

```yaml
Type: ASRJob
Parameter Sets: ByObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoveryJob](./Get-AzureSiteRecoveryJob.md)

[Mulai ulang-AzureSiteRecoveryJob](./Restart-AzureSiteRecoveryJob.md)

[Resume-AzureSiteRecoveryJob](./Resume-AzureSiteRecoveryJob.md)


