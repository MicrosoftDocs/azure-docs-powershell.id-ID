---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 6F31F2B4-6131-4B11-B074-CA05CE3A56F1
online version: ''
schema: 2.0.0
ms.openlocfilehash: ed3b8f56a7b6cc80161eba2cd2fa0e55fb766081
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142654084"
---
# Start-AzureStorSimpleLegacyVolumeContainerMigrationPlan

## SYNOPSIS
Memulai pembuatan rencana migrasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Melakukan migrasiSpecificContainer
```
Start-AzureStorSimpleLegacyVolumeContainerMigrationPlan -LegacyConfigId <String>
 -LegacyContainerNames <String[]> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Melakukan migrasiAllContainer
```
Start-AzureStorSimpleLegacyVolumeContainerMigrationPlan -LegacyConfigId <String> [-All]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureStorSimpleLegacyVolumeContainerMigrationPlan** memulai pembuatan rencana migrasi.
Pembuatan rencana migrasi tidak sinkron.
Untuk melihat status paket migrasi, gunakan cmdlet **Get-AzureStorSimpleLegacyVolumeContainerMigrationPlan** .

## EXAMPLES

### Contoh 1: Memulai paket migrasi
```
PS C:\>Start-AzureStorSimpleLegacyVolumeContainerMigrationPlan -LegacyConfigId "c5a831e1-7888-44f4-adf1-92994be630c3" -LegacyContainerNames "OneSDKAzureCloud"
Successfully started estimating the Migration Plan. Please check details with Get-AzureStorSimpleLegacyVolumeContainerMigrationPlan
```

Perintah ini memulai pembuatan rencana migrasi untuk wadah warisan bernama OneSDKAzureCloud.
Perintah mengembalikan pesan tentang status rencana, dan untuk menggunakan cmdlet **Get-AzureStorSimpleLegacyVolumeContainerMigrationPlan** untuk informasi terbaru.

### Contoh 2: Mulai paket migrasi untuk semua wadah volume
```
PS C:\>Start-AzureStorSimpleLegacyVolumeContainerMigrationPlan -LegacyConfigId "c5a831e1-7888-44f4-adf1-92994be630c3" -All
Successfully started estimating the Migration Plan. Please check details with Get-AzureStorSimpleLegacyVolumeContainerMigrationPlan
```

Perintah ini memulai pembuatan rencana migrasi untuk semua wadah volume warisan dalam file konfigurasi yang diimpor.

## PARAMETERS

### -Semua
Menunjukkan bahwa cmdlet ini memulai perkiraan waktu migrasi untuk semua wadah volume dalam file konfigurasi yang diimpor.

```yaml
Type: SwitchParameter
Parameter Sets: MigrateAllContainer
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LegacyConfigId
Menentukan ID unik konfigurasi peralatan warisan.

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

### -LegacyContainerNames
Menentukan array nama wadah volume untuk membuat rencana migrasi.

```yaml
Type: String[]
Parameter Sets: MigrateSpecificContainer
Aliases: 

Required: True
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### String
Cmdlet ini mengembalikan status pekerjaan rencana migrasi jika telah berhasil dimulai di peralatan.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleLegacyVolumeContainerMigrationPlan](./Get-AzureStorSimpleLegacyVolumeContainerMigrationPlan.md)


