---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
Module Name: AzureRM
ms.assetid: 2CE84C3A-EFC0-47FA-ACE5-687380D90A7D
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.trafficmanager/enable-azurermtrafficmanagerprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Enable-AzureRmTrafficManagerProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Enable-AzureRmTrafficManagerProfile.md
ms.openlocfilehash: 252a633112c28b1dc1e62a6004e3f67e2b6a343a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427670"
---
# Enable-AzureRmTrafficManagerProfile

## SYNOPSIS
Mengaktifkan profil Traffic Manager.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Bidang
```
Enable-AzureRmTrafficManagerProfile -Name <String> -ResourceGroupName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Object
```
Enable-AzureRmTrafficManagerProfile -TrafficManagerProfile <TrafficManagerProfile>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Enable-AzureRmTrafficManagerProfile** mengaktifkan Azure Traffic Manager profil.
Anda dapat menentukan objek profil menggunakan saluran atau sebagai nilai parameter.
Alternatifnya, Anda bisa menentukan profil dengan menggunakan parameter *Name* dan *ResourceGroupName.*

## EXAMPLES

### Contoh 1: Mengaktifkan profil yang ditentukan berdasarkan nama
```
PS C:\>Enable-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
```

Perintah ini mengaktifkan profil yang bernama ContosoProfile dalam ResourceGroup11.

### Contoh 2: Mengaktifkan profil menggunakan saluran
```
PS C:\>Get-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11" | Enable-AzureRmTrafficManagerProfile
```

Perintah ini mendapatkan profil bernama ContosoProfile dalam ResourceGroup11.
Perintah tersebut lalu meneruskan profil itu ke cmdlet **Enable-AzureRmTrafficManagerProfile** dengan menggunakan operator pipeline.
Cmdlet tersebut mengaktifkan profil tersebut.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama profil Traffic Manager yang cmdlet ini aktifkan.

```yaml
Type: String
Parameter Sets: Fields
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.
Cmdlet ini mengaktifkan Traffic Manager profil dalam grup yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: Fields
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficManagerProfile
Menentukan objek **TrafficManagerProfile** untuk diaktifkan.
Untuk mendapatkan objek **TrafficManagerProfile,** gunakan cmdlet Get-AzureRmTrafficManagerProfile baru.

```yaml
Type: TrafficManagerProfile
Parameter Sets: Object
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
Cmdlet ini menerima objek **TrafficManagerProfile.**

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[Disable-AzureRmTrafficManagerProfile](./Disable-AzureRmTrafficManagerProfile.md)

[Get-AzureRmTrafficManagerProfile](./Get-AzureRmTrafficManagerProfile.md)

[New-AzureRmTrafficManagerProfile](./New-AzureRmTrafficManagerProfile.md)

[Remove-AzureRmTrafficManagerProfile](./Remove-AzureRmTrafficManagerProfile.md)

[Set-AzureRmTrafficManagerProfile](./Set-AzureRmTrafficManagerProfile.md)


