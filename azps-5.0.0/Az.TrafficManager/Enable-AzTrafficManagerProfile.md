---
external help file: Microsoft.Azure.PowerShell.Cmdlets.TrafficManager.dll-Help.xml
Module Name: Az.TrafficManager
ms.assetid: 2CE84C3A-EFC0-47FA-ACE5-687380D90A7D
online version: https://docs.microsoft.com/en-us/powershell/module/az.trafficmanager/enable-aztrafficmanagerprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/TrafficManager/TrafficManager/help/Enable-AzTrafficManagerProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/TrafficManager/TrafficManager/help/Enable-AzTrafficManagerProfile.md
ms.openlocfilehash: ba578d800631304405ab1e0a4139a11d9f2a26dc
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132409819"
---
# Enable-AzTrafficManagerProfile

## SYNOPSIS
Mengaktifkan profil Traffic Manager.

## SINTAKS

### Bidang
```
Enable-AzTrafficManagerProfile -Name <String> -ResourceGroupName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Object
```
Enable-AzTrafficManagerProfile -TrafficManagerProfile <TrafficManagerProfile>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Enable-AzTrafficManagerProfile** mengaktifkan Azure Traffic Manager profil.
Anda dapat menentukan objek profil menggunakan saluran atau sebagai nilai parameter.
Alternatifnya, Anda bisa menentukan profil dengan menggunakan parameter *Name* dan *ResourceGroupName.*

## CONTOH

### Contoh 1: Mengaktifkan profil yang ditentukan berdasarkan nama
```
PS C:\>Enable-AzTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
```

Perintah ini mengaktifkan profil yang bernama ContosoProfile dalam ResourceGroup11.

### Contoh 2: Mengaktifkan profil menggunakan saluran
```
PS C:\>Get-AzTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11" | Enable-AzTrafficManagerProfile
```

Perintah ini mendapatkan profil bernama ContosoProfile dalam ResourceGroup11.
Perintah tersebut lalu meneruskan profil itu ke cmdlet **Enable-AzTrafficManagerProfile** menggunakan operator pipeline.
Cmdlet tersebut mengaktifkan profil tersebut.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Nama
Menentukan nama profil Traffic Manager yang cmdlet ini aktifkan.

```yaml
Type: System.String
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
Type: System.String
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
Untuk mendapatkan objek **TrafficManagerProfile,** gunakan cmdlet Get-AzTrafficManagerProfile baru.

```yaml
Type: Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile

## OUTPUT

### System.Boolean

## CATATAN

## LINK TERKAIT

[Disable-AzTrafficManagerProfile](./Disable-AzTrafficManagerProfile.md)

[Get-AzTrafficManagerProfile](./Get-AzTrafficManagerProfile.md)

[New-AzTrafficManagerProfile](./New-AzTrafficManagerProfile.md)

[Remove-AzTrafficManagerProfile](./Remove-AzTrafficManagerProfile.md)

[Set-AzTrafficManagerProfile](./Set-AzTrafficManagerProfile.md)


