---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 16146A0D-4605-489A-8259-A37BEAC98306
online version: ''
schema: 2.0.0
ms.openlocfilehash: a43251167510e21f7c262e56e8fc9695108acad2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142979068"
---
# Update-AzureSiteRecoveryProtectionEntity

## SYNOPSIS
Memperbarui properti entitas perlindungan di Azure Site Recovery.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Update-AzureSiteRecoveryProtectionEntity -ProtectionEntity <ASRProtectionEntity> [-WaitForCompletion]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzureSiteRecoveryProtectionEntity** memperbarui properti entitas perlindungan di Azure Site Recovery, seperti informasi pemilik mesin virtual.
Cmdlet ini hanya didukung untuk Monitor Mesin Virtual (VMM) untuk entitas perlindungan yang dilindungi VMM.

## EXAMPLES

### Contoh 1: Memperbarui entitas proteksi
```
PS C:\> $Container = Get-AzureSiteRecoveryProtectionContainer
PS C:\> $ProtectionEntity = Get-AzureSiteRecoveryProtectionEntity -ProtectionContainer $Container
PS C:\> Update-AzureSiteRecoveryProtectionEntity -ProtectionEntity $ProtectionEntity
           Name             : 
           ID               : 680ffe0f-6236-465e-8c94-81242fa67e6d
           ClientRequestId  : 2c47e6ce-1460-4187-8a0f-b9073735fa38-2014-12-30 06:44:40Z-P
           State            : NotStarted
           StateDescription : NotStarted
           StartTime        : 
           EndTime          : 
           AllowedActions   : {}
           Tasks            : {}
           Errors           : {}
```

Perintah pertama mendapatkan wadah yang dilindungi dengan menggunakan cmdlet **Get-AzureSiteRecoveryProtectionContainer** , lalu menyimpan objek tersebut dalam variabel $Container.

Perintah kedua mendapatkan mesin virtual dilindungi milik wadah yang disimpan di $Container menggunakan cmdlet **Get-AzureSiteRecoveryProtectionEntity** , lalu menyimpannya dalam variabel $ProtectionEntity.

Perintah akhir memperbarui entitas perlindungan dalam $ProtectionEntity.

## PARAMETERS

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

### -ProtectionEntity
Menentukan entitas perlindungan untuk diperbarui.
Untuk mendapatkan objek **ASRProtectionEntity** , gunakan cmdlet **Get-AzureSiteRecoveryProtectionEntity** .

```yaml
Type: ASRProtectionEntity
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WaitForCompletion
Menunjukkan bahwa cmdlet ini menunggu operasi selesai sebelum mengembalikan kontrol ke konsol Windows PowerShell.

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

## NOTES

## RELATED LINKS

[Get-AzureSiteRecoveryProtectionContainer](./Get-AzureSiteRecoveryProtectionContainer.md)

[Get-AzureSiteRecoveryProtectionEntity](./Get-AzureSiteRecoveryProtectionEntity.md)

[Set-AzureSiteRecoveryProtectionEntity](./Set-AzureSiteRecoveryProtectionEntity.md)


