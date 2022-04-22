---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 2BDB255A-EFB3-4580-BE95-187008DB208C
online version: ''
schema: 2.0.0
ms.openlocfilehash: 847a6f088704436b0c8cdb62aa5de27f5429b3cf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142981091"
---
# New-AzureDeployment

## SYNOPSIS
Membuat penyebaran dari layanan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

```
New-AzureDeployment [-ServiceName] <String> [-Package] <String> [-Configuration] <String> [-Slot] <String>
 [[-Label] <String>] [[-Name] <String>] [-DoNotStart] [-TreatWarningsAsError]
 [-ExtensionConfiguration <ExtensionConfigurationInput[]>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureDeployment** membuat penyebaran Azure dari layanan yang terdiri dari peran web dan peran pekerja.
Cmdlet ini membuat penyebaran berdasarkan file paket (.cspkg) dan file konfigurasi layanan (.cscfg).
Tentukan nama yang unik dalam lingkungan penyebaran.

Gunakan cmdlet **New-AzureVM** untuk membuat penyebaran berdasarkan mesin virtual Azure.

## EXAMPLES

### Contoh 1: Membuat penyebaran
```
PS C:\> New-AzureDeployment -ServiceName "ContosoService" -Slot "Production" -Package "https://contosostorage.blob.core.windows.net/container06/ContosoPackage.cspkg" -Configuration "C:\packages\ContosoConfiguration.cscfg" -Label "ContosoDeployment"
```

Perintah ini membuat penyebaran produksi berdasarkan paket bernama ContosoPackage.cspkg dan konfigurasi bernama ContosoConfiguration.cscfg.
Perintah menentukan label untuk penyebaran.
Ini tidak menentukan nama.
Cmdlet ini membuat GUID sebagai nama.

### Contoh 2: Membuat penyebaran berdasarkan konfigurasi ekstensi
```
PS C:\> New-AzureDeployment -ServiceName "ContosoService" -Slot "Production" -Package "https://contosostorage.blob.core.windows.net/container06/ContosoPackage.cspkg" -Configuration "C:\packages\ContosoConfiguration.cscfg" -ExtensionConfiguration "C:\packages\ContosoExtensionConfig.cscfg"
```

Perintah ini membuat penyebaran produksi berdasarkan paket dan konfigurasi.
Perintah menentukan konfigurasi ekstensi bernama ContosoExtensionConfig.cscfg.
Cmdlet ini membuat GUID sebagai nama dan label.

## PARAMETERS

### -Configuration
Menentukan jalur lengkap file konfigurasi layanan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DoNotStart
Menentukan bahwa cmdlet ini tidak memulai penyebaran.

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

### -EkstensiKonfigurasi
Menentukan array objek konfigurasi ekstensi.

```yaml
Type: ExtensionConfigurationInput[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Label
Menentukan nama label untuk penyebaran.
Jika Anda tidak menentukan label, cmdlet ini menggunakan GUID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama penyebaran.
Jika Anda tidak menentukan nama, cmdlet ini menggunakan GUID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DeploymentName

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paket
Menentukan jalur atau URI file .cspkg dalam penyimpanan dalam langganan atau proyek yang sama.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### -ServiceName
Menentukan nama layanan Azure untuk penyebaran.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Menentukan lingkungan tempat cmdlet ini membuat penyebaran.
Nilai yang valid adalah: Pementasan dan Produksi.
Nilai defaultnya adalah Produksi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TreatWarningsAsError
Menentukan bahwa pesan peringatan adalah kesalahan.
Jika Anda menentukan parameter ini, pesan peringatan menyebabkan penyebaran gagal.

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

[Get-AzureDeployment](./Get-AzureDeployment.md)

[Get-AzureDeploymentEvent](./Get-AzureDeploymentEvent.md)

[Pindahkan-AzureDeployment](./Move-AzureDeployment.md)

[AzureVM baru](./New-AzureVM.md)

[Hapus-AzureDeployment](./Remove-AzureDeployment.md)

[Set-AzureDeployment](./Set-AzureDeployment.md)


