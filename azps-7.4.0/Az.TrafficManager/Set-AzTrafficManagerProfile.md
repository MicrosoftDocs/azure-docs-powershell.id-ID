---
external help file: Microsoft.Azure.PowerShell.Cmdlets.TrafficManager.dll-Help.xml
Module Name: Az.TrafficManager
ms.assetid: 975DD42E-61B6-437B-884D-C15A8DB7A667
online version: https://docs.microsoft.com/powershell/module/az.trafficmanager/set-aztrafficmanagerprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Set-AzTrafficManagerProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Set-AzTrafficManagerProfile.md
ms.openlocfilehash: 0b7f2915215680eea162677992f8222e2de2ee4d
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144665314"
---
# Set-AzTrafficManagerProfile

## SYNOPSIS
Memperbarui profil Traffic Manager.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.trafficmanager/set-aztrafficmanagerprofile) untuk informasi terbaru.

## SYNTAX

```
Set-AzTrafficManagerProfile -TrafficManagerProfile <TrafficManagerProfile>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzTrafficManagerProfile** memperbarui profil Azure Traffic Manager.
Cmdlet ini memperbarui pengaturan profil dari objek profil lokal.
Anda dapat menentukan objek profil baik dengan menggunakan parameter *TrafficManagerProfile* atau dengan menggunakan alur.

Anda dapat memperoleh objek lokal yang mewakili profil dengan menggunakan cmdlet Get-AzTrafficManagerProfile.
Ubah objek secara lokal lalu gunakan **Set-AzTrafficManagerProfile** untuk menerapkan perubahan Anda.

## EXAMPLES

### Contoh 1: Memperbarui profil
```powershell
$TrafficManagerProfile = Get-AzTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11" 
$TrafficManagerProfile.ProfileStatus = Disabled
Set-AzTrafficManagerProfile -TrafficManagerProfile $TrafficManagerProfile
```

Perintah pertama mendapatkan profil Azure Traffic Manager dengan menggunakan cmdlet Get-AzTrafficManagerProfile.
Perintah menyimpan profil secara lokal dalam variabel $TrafficManagerProfile.

Perintah kedua mengubah profil tersebut secara lokal.
Perintah ini menonaktifkan profil.

Perintah ketiga memperbarui profil Traffic Manager bernama ContosoProfile agar sesuai dengan nilai lokal dalam $TrafficManagerProfile.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile

## OUTPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile

## NOTES

## RELATED LINKS

[Add-AzTrafficManagerEndpointConfig](./Add-AzTrafficManagerEndpointConfig.md)

[Get-AzTrafficManagerProfile](./Get-AzTrafficManagerProfile.md)

[New-AzTrafficManagerProfile](./New-AzTrafficManagerProfile.md)

[Remove-AzTrafficManagerEndpointConfig](./Remove-AzTrafficManagerEndpointConfig.md)

[Remove-AzTrafficManagerProfile](./Remove-AzTrafficManagerProfile.md)


