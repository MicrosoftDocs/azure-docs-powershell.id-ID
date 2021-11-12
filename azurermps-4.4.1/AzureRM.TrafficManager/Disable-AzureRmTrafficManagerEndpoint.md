---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
Module Name: AzureRM.TrafficManager
ms.assetid: 8CC749F1-B961-4F8F-BAD4-2C0F4385D1C2
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Disable-AzureRmTrafficManagerEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Disable-AzureRmTrafficManagerEndpoint.md
ms.openlocfilehash: 1481b577e248354eb2fdccbb9d6ecd450ab0cf62
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423050"
---
# Disable-AzureRmTrafficManagerEndpoint

## SYNOPSIS
Menonaktifkan titik akhir di Traffic Manager profil.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Bidang
```
Disable-AzureRmTrafficManagerEndpoint -Name <String> -Type <String> -ProfileName <String>
 -ResourceGroupName <String> [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Object
```
Disable-AzureRmTrafficManagerEndpoint -TrafficManagerEndpoint <TrafficManagerEndpoint> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Disable-AzureRmTrafficManagerEndpoint** menonaktifkan titik akhir di profil Azure Traffic Manager.

Anda bisa menggunakan operator pipeline untuk mengirim objek **TrafficManagerEndpoint** ke cmdlet ini, atau Anda bisa mengirim objek **TrafficManagerEndpoint** menggunakan parameter *TrafficManagerEndpoint.*

Alternatifnya, Anda bisa menentukan nama titik  akhir dan mengetik dengan menggunakan parameter Nama dan *Tipe,* bersama dengan parameter *ProfileName* *dan ResourceGroupName.*

## EXAMPLES

### Contoh 1: Menonaktifkan titik akhir berdasarkan nama
```
PS C:\> Disable-AzureRmTrafficManagerEndpoint -Name "contoso" -ProfileName "ContosoProfile" -ResourceGroupName ResourceGroup11 -Type ExternalEndpoints
```

Perintah ini menonaktifkan titik akhir eksternal yang bernama contoso dalam profil yang bernama ContosoProfile dalam grup sumber daya ResouceGroup11.
Perintah akan meminta konfirmasi Anda.

### Contoh 2: Menonaktifkan titik akhir dengan menggunakan pipeline
```
PS C:\>Get-AzureRmTrafficManagerEndpoint -Name "contoso" -Type ExternalEndpoints -ProfileName "ContosoProfile" -ResourceGroupName "ResourceGroup11" | Disable-AzureRmTrafficManagerEndpoint -Force
```

Perintah ini mendapatkan titik akhir eksternal yang bernama Contoso dari profil yang bernama ContosoProfile dalam ResourceGroup11.
Perintah itu lalu melewati titik akhir itu ke cmdlet **Disable-AzureRmTrafficManagerEndpoint** dengan menggunakan operator pipeline.
Cmdlet tersebut menonaktifkan titik akhir tersebut.
Perintah menentukan parameter *Paksa.*
Oleh karena itu, kami tidak meminta konfirmasi Anda.

## PARAMETERS

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama titik akhir Traffic Manager cmdlet ini dinonaktifkan.

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

### -ProfileName
Menentukan nama profil Traffic Manager cmdlet ini menonaktifkan titik akhir.
Untuk mendapatkan profil, gunakan cmdlet Get-AzureRmTrafficManagerProfile baru.

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
Cmdlet ini menonaktifkan titik Traffic Manager titik akhir dalam grup yang ditentukan parameter ini.

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

### -TrafficManagerEndpoint
Menentukan titik Traffic Manager titik akhir yang dinonaktifkan cmdlet ini.
Untuk mendapatkan objek **TrafficManagerEndpoint,** gunakan cmdlet Get-AzureRmTrafficManagerEndpoint.

```yaml
Type: Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerEndpoint
Parameter Sets: Object
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe titik akhir yang tambahkan cmdlet ini ke Traffic Manager profil.
Nilai valid adalah: 

- AzureEndpoints
- ExternalEndpoints
- NestedEndpoints

```yaml
Type: System.String
Parameter Sets: Fields
Aliases: 
Accepted values: AzureEndpoints, ExternalEndpoints, NestedEndpoints

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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

### TrafficManagerEndpoint
Parameter 'TrafficManagerEndpoint' menerima nilai tipe 'TrafficManagerEndpoint' dari saluran

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[Enable-AzureRmTrafficManagerEndpoint](./Enable-AzureRmTrafficManagerEndpoint.md)

[Get-AzureRmTrafficManagerEndpoint](./Get-AzureRmTrafficManagerEndpoint.md)

[Get-AzureRmTrafficManagerProfile](./Get-AzureRmTrafficManagerProfile.md)

[New-AzureRmTrafficManagerEndpoint](./New-AzureRmTrafficManagerEndpoint.md)

[New-AzureRmTrafficManagerProfile](./New-AzureRmTrafficManagerProfile.md)

[Remove-AzureRmTrafficManagerEndpoint](./Remove-AzureRmTrafficManagerEndpoint.md)

[Set-AzureRmTrafficManagerProfile](./Set-AzureRmTrafficManagerProfile.md)


