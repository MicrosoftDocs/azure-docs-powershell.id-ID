---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 7F51F534-6C64-4983-A08F-4732A39C2E7C
online version: ''
schema: 2.0.0
ms.openlocfilehash: c3ece42526e65de38a3d29e436c3cfdda2228fb6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141816066"
---
# Set-AzureDeployment

## SYNOPSIS
Mengubah status, pengaturan konfigurasi, atau mode pemutakhiran penyebaran.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

### Upgrade
```
Set-AzureDeployment [-Upgrade] [-ServiceName] <String> [-Package] <String> [-Configuration] <String>
 [-Slot] <String> [[-Mode] <String>] [[-Label] <String>] [[-RoleName] <String>] [-Force]
 [[-ExtensionConfiguration] <ExtensionConfigurationInput[]>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Config
```
Set-AzureDeployment [-Config] [-ServiceName] <String> [-Configuration] <String> [-Slot] <String>
 [[-ExtensionConfiguration] <ExtensionConfigurationInput[]>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Status
```
Set-AzureDeployment [-Status] [-ServiceName] <String> [-Slot] <String> [-NewStatus] <String>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureDeployment** mengubah status, pengaturan konfigurasi, atau mode pemutakhiran penyebaran Azure.
Anda dapat mengubah status penyebaran menjadi Berjalan atau Ditangguhkan.
Anda dapat mengubah file .cscfg untuk penyebaran.
Anda dapat mengatur mode pemutakhiran dan memperbarui file konfigurasi.
Gunakan cmdlet **Set-AzureWalkUpgradeDomain** untuk memulai pemutakhiran.

## EXAMPLES

### Contoh 1: Mengubah status penyebaran
```
PS C:\> Set-AzureDeployment -Status -ServiceName "ContosoService" -Slot "Production" -NewStatus "Running"
```

Perintah ini mengatur status penyebaran untuk layanan bernama ContosoService di lingkungan produksi ke Berjalan.

### Contoh 2: Menetapkan file konfigurasi lain ke penyebaran
```
PS C:\> Set-AzureDeployment -Config -ServiceName "ContosoService" -Slot "Staging" -Configuration "C:\Temp\MyServiceConfig.Cloud.csfg"
```

Perintah ini menetapkan file konfigurasi berbeda untuk penyebaran untuk layanan bernama ContosoService dalam lingkungan pementasan.

### Contoh 3: Mengatur mode pemutakhiran ke Otomatis
```
PS C:\> Set-AzureDeployment -Upgrade -ServiceName "ContosoService" -Mode Auto -Package "C:\packages\ContosoApp.cspkg" -Configuration "C:\Config\ContosoServiceConfig.Cloud.csfg"
```

Perintah ini mengatur mode pemutakhiran ke Otomatis, dan menentukan paket pemutakhiran dan file konfigurasi baru.

### Contoh 4: Menginstal konfigurasi ekstensi dalam layanan
```
PS C:\> Set-AzureDeployment -Config -ServiceName "ContosoService" -Mode "Automatic" -Package "https://contosostorage.blob.core.windows.net/container06/ContosoPackage.cspkg" -Configuration "C:\packages\ContosoConfiguration.cscfg" -Slot "Production" -ExtensionConfiguration "C:\packages\ContosoExtensionConfig.cscfg"
```

Perintah ini menginstal konfigurasi ekstensi di Layanan Awan yang ditentukan dan menerapkannya pada peran.

## PARAMETERS

### -Config
Menentukan bahwa cmdlet ini mengubah konfigurasi penyebaran.

```yaml
Type: SwitchParameter
Parameter Sets: Config
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Configuration
Menentukan jalur lengkap file konfigurasi .cscfg.
Anda dapat menentukan file konfigurasi untuk perubahan pemutakhiran atau konfigurasi.

```yaml
Type: String
Parameter Sets: Upgrade, Config
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EkstensiKonfigurasi
Menentukan array objek konfigurasi ekstensi.

```yaml
Type: ExtensionConfigurationInput[]
Parameter Sets: Upgrade, Config
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Paksa
Menunjukkan bahwa cmdlet melakukan peningkatan paksa.

```yaml
Type: SwitchParameter
Parameter Sets: Upgrade
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
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
Menentukan label untuk penyebaran yang dimutakhirkan.

```yaml
Type: String
Parameter Sets: Upgrade
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode
Menentukan mode pemutakhiran.
Nilai yang valid adalah: 

- Auto 
- Manual 
- Simultan

```yaml
Type: String
Parameter Sets: Upgrade
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewStatus
Menentukan status target untuk penyebaran.
Nilai yang valid adalah: Berjalan dan Ditangguhkan.

```yaml
Type: String
Parameter Sets: Status
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paket
Menentukan jalur lengkap file paket pemutakhiran.

```yaml
Type: String
Parameter Sets: Upgrade
Aliases: 

Required: True
Position: 2
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

### -RoleName
Menentukan nama peran yang akan dimutakhirkan.

```yaml
Type: String
Parameter Sets: Upgrade
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceName
Menentukan nama layanan Azure penyebaran.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Menentukan lingkungan penyebaran untuk diubah.
Nilai yang valid adalah: Produksi dan Pementasan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
Menentukan bahwa cmdlet ini mengubah status penyebaran.

```yaml
Type: SwitchParameter
Parameter Sets: Status
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Upgrade
Menentukan bahwa cmdlet ini memutakhirkan penyebaran.

```yaml
Type: SwitchParameter
Parameter Sets: Upgrade
Aliases: 

Required: True
Position: 0
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

[Get-AzureDeployment](./Get-AzureDeployment.md)

[Get-AzureDeploymentEvent](./Get-AzureDeploymentEvent.md)

[Pindahkan-AzureDeployment](./Move-AzureDeployment.md)

[AzureDeployment baru](./New-AzureDeployment.md)

[Hapus-AzureDeployment](./Remove-AzureDeployment.md)

[Set-AzureWalkUpgradeDomain](./Set-AzureWalkUpgradeDomain.md)


