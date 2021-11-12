---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
Module Name: AzureRM.TrafficManager
ms.assetid: 975DD42E-61B6-437B-884D-C15A8DB7A667
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Set-AzureRmTrafficManagerProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Set-AzureRmTrafficManagerProfile.md
ms.openlocfilehash: e8baf033131442f23a0db63339673018b209f140
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423043"
---
# Set-AzureRmTrafficManagerProfile

## SYNOPSIS
Memperbarui profil Traffic Manager Anda.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmTrafficManagerProfile -TrafficManagerProfile <TrafficManagerProfile>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmTrafficManagerProfile** memperbarui Azure Traffic Manager profil.
Cmdlet ini memperbarui pengaturan profil dari objek profil lokal.
Anda bisa menentukan objek profil baik dengan menggunakan parameter *TrafficManagerProfile* atau dengan menggunakan saluran.

Anda dapat memperoleh objek lokal yang mewakili profil menggunakan cmdlet Get-AzureRmTrafficManagerProfile.
Ubah objek secara lokal lalu gunakan **Set-AzureRmTrafficManagerProfile** untuk melakukan perubahan Anda.

## EXAMPLES

### Contoh 1: Memperbarui profil
```
PS C:\>$TrafficManagerProfile = Get-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11" 
PS C:\> $TrafficManagerProfile.ProfileStatus = Disabled
PS C:\> Set-AzureRmTrafficManagerProfile -TrafficManagerProfile $TrafficManagerProfile
```

Perintah pertama mendapatkan profil Azure Traffic Manager dengan menggunakan cmdlet Get-AzureRmTrafficManagerProfile.
Perintah menyimpan profil secara lokal di $TrafficManagerProfile lokal.

Perintah kedua mengubah profil secara lokal.
Perintah ini akan menonaktifkan profil.

Perintah ketiga memperbarui profil Traffic Manager bernama ContosoProfile agar sesuai dengan nilai lokal di $TrafficManagerProfile.

## PARAMETERS

### -TrafficManagerProfile
Menentukan objek **TrafficManagerProfile** lokal.
Cmdlet ini memperbarui Traffic Manager agar sesuai dengan objek lokal ini.

```yaml
Type: Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
Cmdlet ini menerima objek **TrafficManagerProfile.**

## OUTPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
Cmdlet ini mengembalikan objek **TrafficManagerProfile.**

## CATATAN

## RELATED LINKS

[Add-AzureRmTrafficManagerEndpointConfig](./Add-AzureRmTrafficManagerEndpointConfig.md)

[Get-AzureRmTrafficManagerProfile](./Get-AzureRmTrafficManagerProfile.md)

[New-AzureRmTrafficManagerProfile](./New-AzureRmTrafficManagerProfile.md)

[Remove-AzureRmTrafficManagerEndpointConfig](./Remove-AzureRmTrafficManagerEndpointConfig.md)

[Remove-AzureRmTrafficManagerProfile](./Remove-AzureRmTrafficManagerProfile.md)


