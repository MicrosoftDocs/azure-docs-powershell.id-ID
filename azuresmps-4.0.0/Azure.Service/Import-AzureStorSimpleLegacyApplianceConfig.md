---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: F41E3B17-A33C-4FBF-B532-2E86F1AAE2B8
online version: ''
schema: 2.0.0
ms.openlocfilehash: 4b31b4007a757b252b5a1026473b108e5215048a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142094553"
---
# Import-AzureStorSimpleLegacyApplianceConfig

## SYNOPSIS
Mengimpor file konfigurasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Import-AzureStorSimpleLegacyApplianceConfig -ConfigFilePath <String> -TargetDeviceName <String>
 -ConfigDecryptionKey <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Import-AzureStorSimpleLegacyApplianceConfig** mengimpor file konfigurasi dari alat warisan.
File tersebut berisi informasi tentang wadah volume, kebijakan pencadangan, dan kredensial akun penyimpanan untuk layanan Azure StorSimple.
Cmdlet ini mengembalikan metadata konfigurasi alat warisan.

## EXAMPLES

### Contoh 1: Mengimpor file konfigurasi
```
PS C:\>Import-AzureStorSimpleLegacyApplianceConfig -ConfigFilePath "C:\MigrationData\LegacyStorSimpleConfig.sse" -TargetDeviceName "8100-123456789" -ConfigDecryptionKey "fWs793hHVhR90NKdDYTeNq"
LegacyConfigId      : e2d5c9b1-b528-4c21-b8ae-533feefc8a41
ImportedOn          : 4/8/2015 7:23:04 PM
ConfigFile          : D:\configs\StorSimpleConfig_27_Mar_15_12_19.xml.sse
TargetApplianceName : Arunkm-N4
Details             : Available Cloud Configuration(s) for migration : 
                          Cloud Configuration(s) 1    : TC8Cloud[Stingray19-FP6] 
                          Cloud Configuration(s) 2    : fulle_cc4
                          Cloud Configuration(s) 3    : fulle_cc2
                          Cloud Configuration(s) 4    : fulle_cc3
                          Cloud Configuration(s) 5    : TC9Cloud[Stingray18-FP3] 
                          Cloud Configuration(s) 6    : fulle_cc1
                          Cloud Configuration(s) 7    : Container-New[Stingray19-FP6] 
                          Cloud Configuration(s) 8    : TC6Cloud[Stingray19-FP6] 
                          Cloud Configuration(s) 9    : TC7Cloud[Stingray18-FP3] 

Result              : Successfully imported config from the legacy appliance! 
Save the legacy config id and cloud configuration(s) for future reference.
```

Perintah ini mengimpor file konfigurasi pada jalur yang ditentukan.
Perintah menyertakan kunci untuk mendekripsi file.

## PARAMETERS

### -ConfigDecryptionKey
Menentukan kunci dekripsi untuk konfigurasi alat warisan.

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

### -ConfigFilePath
Menentukan jalur mutlak file konfigurasi yang akan didapatkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure.

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

### -TargetDeviceName
Menentukan nama perangkat target seperti yang disajikan di portal.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### LegacyApplianceConfiguration
Cmdlet ini mengembalikan detail konfigurasi.
Objek **LegacyApplianceConfiguration** berisi informasi berikut: ID konfigurasi, nama wadah volume, catatan kontrol akses, kebijakan pencadangan, pengaturan bandwidth, wadah volume, kredensial akun penyimpanan, dan volume.

## CATATAN

## RELATED LINKS

[Impor-AzureStorSimpleLegacyVolumeContainer](./Import-AzureStorSimpleLegacyVolumeContainer.md)


