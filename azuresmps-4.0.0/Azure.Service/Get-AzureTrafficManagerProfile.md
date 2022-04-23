---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: 28136DC3-520B-4134-8736-93D86EEABAE1
online version: ''
schema: 2.0.0
ms.openlocfilehash: b0351f7be40b8bb819adb68ad3e03fcde8f5f644
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143104823"
---
# Get-AzureTrafficManagerProfile

## SYNOPSIS
Mendapatkan detail profil Traffic Manager.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureTrafficManagerProfile [-Name <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureTrafficManagerProfile** mendapatkan detail profil Microsoft Azure Traffic Manager.
Jika Anda tidak menentukan parameter *Nama*, cmdlet mencantumkan profil Traffic Manager dalam langganan saat ini.

## EXAMPLES

### Contoh 1: Dapatkan daftar profil Traffic Manager dalam langganan
```
PS C:\>Get-AzureTrafficManagerProfile
```

Perintah ini mendapatkan daftar profil Traffic Manager dalam langganan Anda.

### Contoh 2: Dapatkan profil Traffic Manager
```
PS C:\>Get-AzureTrafficManagerProfile -Name "MyProfile"
```

Perintah ini mendapatkan profil Traffic Manager bernama MyProfile.

### Contoh 3: Menambahkan titik akhir ke profil Traffic Manager
```
PS C:\>Get-AzureTrafficManagerProfile -Name "MyProfile" | Add-AzureTrafficManagerEndpoint -DomainName "Myapp2.cloudapp.net" -TrafficManagerProfile $MyTrafficManagerProfile -Type "CloudService" -Status "Enabled" | Set-AzureTrafficManagerProfile
```

Perintah ini menambahkan titik akhir ke profil Traffic Manager, lalu menyimpan profil.

## PARAMETERS

### -Nama
Menentukan nama profil Traffic Manager untuk didapatkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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

### Microsoft.WindowsAzure.Commands.Utilities.TrafficManager.Models.IProfileWithDefinition
Cmdlet ini menghasilkan objek profil atau objek Traffic Manager.

## NOTES

## RELATED LINKS

[Add-AzureTrafficManagerEndpoint](./Add-AzureTrafficManagerEndpoint.md)

[Nonaktifkan-AzureTrafficManagerProfile](./Disable-AzureTrafficManagerProfile.md)

[Enable-AzureTrafficManagerProfile](./Enable-AzureTrafficManagerProfile.md)

[New-AzureTrafficManagerProfile](./New-AzureTrafficManagerProfile.md)

[Hapus-AzureTrafficManagerProfile](./Remove-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](./Set-AzureTrafficManagerProfile.md)


