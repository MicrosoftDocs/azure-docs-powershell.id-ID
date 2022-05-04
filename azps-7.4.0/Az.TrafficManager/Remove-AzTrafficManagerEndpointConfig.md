---
external help file: Microsoft.Azure.PowerShell.Cmdlets.TrafficManager.dll-Help.xml
Module Name: Az.TrafficManager
ms.assetid: 8E12A392-A100-4814-9003-B2999150DCE1
online version: https://docs.microsoft.com/powershell/module/az.trafficmanager/remove-aztrafficmanagerendpointconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Remove-AzTrafficManagerEndpointConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Remove-AzTrafficManagerEndpointConfig.md
ms.openlocfilehash: d46ef1f1aed47d3216ffdd6acb1287751c3bd17a
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144626520"
---
# Remove-AzTrafficManagerEndpointConfig

## SYNOPSIS
Menghapus titik akhir dari objek profil Traffic Manager lokal.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.trafficmanager/remove-aztrafficmanagerendpointconfig) untuk informasi terbaru.

## SYNTAX

```
Remove-AzTrafficManagerEndpointConfig -EndpointName <String> -TrafficManagerProfile <TrafficManagerProfile>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzTrafficManagerEndpointConfig** menghapus titik akhir dari objek profil Azure Traffic Manager lokal.
Anda bisa mendapatkan profil dengan menggunakan cmdlet Get-AzTrafficManagerProfile.

Cmdlet ini beroperasi pada objek profil lokal.
Terapkan perubahan Anda ke profil untuk Traffic Manager dengan menggunakan cmdlet Set-AzTrafficManagerProfile.
Untuk menghapus titik akhir dan menerapkan perubahan dalam satu operasi, gunakan cmdlet Remove-AzTrafficManagerEndpoint.

## EXAMPLES

### Contoh 1: Menghapus titik akhir
```powershell
$TrafficManagerProfile = Get-AzTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
Remove-AzTrafficManagerEndpointConfig -EndpointName "contoso" -TrafficManagerProfile $TrafficManagerProfile 
Set-AzTrafficManagerProfile -TrafficManagerProfile $TrafficManagerProfile
```

Perintah pertama mendapatkan profil Azure Traffic Manager dengan menggunakan cmdlet **Get-AzTrafficManagerProfile**.
Perintah menyimpan profil lokal dalam variabel $TrafficManagerProfile.

Perintah kedua menghapus titik akhir Azure bernama contoso dari profil yang disimpan di $TrafficManagerProfile.
Perintah ini hanya mengubah objek lokal.

Perintah akhir memperbarui profil Traffic Manager bernama ContosoProfile agar sesuai dengan nilai lokal di $TrafficManagerProfile.

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

### -EndpointName
Menentukan nama titik akhir Traffic Manager yang dihapus cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficManagerProfile
Menentukan objek **TrafficManagerProfile** lokal.
Cmdlet ini memodifikasi objek lokal ini.
Untuk mendapatkan objek **TrafficManagerProfile** , gunakan cmdlet Get-AzTrafficManagerProfile.

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

[Remove-AzTrafficManagerEndpoint](./Remove-AzTrafficManagerEndpoint.md)

[Set-AzTrafficManagerProfile](./Set-AzTrafficManagerProfile.md)


