---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
Module Name: AzureRM.TrafficManager
ms.assetid: 4556C345-55D0-431C-B980-219D5ED14E5F
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.trafficmanager/get-azurermtrafficmanagerendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Get-AzureRmTrafficManagerEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Get-AzureRmTrafficManagerEndpoint.md
ms.openlocfilehash: 335cb4308a64811fdc99b0bafe6660ee69c9b9d3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142059131"
---
# Get-AzureRmTrafficManagerEndpoint

## SYNOPSIS
Mendapatkan titik akhir untuk profil Pengelola Lalu Lintas.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Bidang
```
Get-AzureRmTrafficManagerEndpoint -Name <String> -Type <String> -ProfileName <String>
 -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Objek
```
Get-AzureRmTrafficManagerEndpoint -TrafficManagerEndpoint <TrafficManagerEndpoint>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmTrafficManagerEndpoint** mendapatkan titik akhir untuk profil Azure Traffic Manager.

Anda dapat mengubah objek ini secara lokal, lalu menerapkan perubahan pada profil menggunakan cmdlet Set-AzureRmTrafficManagerEndpoint.
Tentukan titik akhir dengan menggunakan parameter *Nama* dan *Tipe* .
Anda dapat menentukan profil Traffic Manager baik dengan menggunakan parameter *ProfileName* dan *ResourceGroupName* , atau dengan menentukan objek **TrafficManagerProfile** .
Atau, Anda dapat melewati nilai tersebut menggunakan pipeline.

## EXAMPLES

### Contoh 1: Mendapatkan titik akhir
```
PS C:\>$TrafficManagerEndpoint = Get-AzureRmTrafficManagerEndpoint -Name "contoso" -ProfileName "ContosoProfile" -ResourceGroupName "ResourceGroup11" -Type AzureEndpoints
```

Perintah ini mendapatkan titik akhir Azure bernama contoso dari profil bernama ContosoProfile dalam grup sumber daya bernama ResourceGroup11, lalu menyimpan objek tersebut dalam variabel $TrafficManagerEndpoint.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Nama
Menentukan nama titik akhir Manajer Lalu Lintas yang didapat cmdlet ini.

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
Menentukan nama titik akhir Manajer Lalu Lintas yang didapat cmdlet ini.

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
Cmdlet ini mendapatkan titik akhir Manajer Lalu Lintas dalam grup yang ditentukan parameter ini.

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
Menentukan titik akhir Traffic Manager yang didapat cmdlet ini.

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
Menentukan tipe titik akhir yang ditambahkan cmdlet ini ke profil Traffic Manager.
Nilai yang valid adalah: 

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerEndpoint
Parameter 'TrafficManagerEndpoint' menerima nilai tipe 'TrafficManagerEndpoint' dari pipeline

## OUTPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerEndpoint

## CATATAN

## RELATED LINKS

[Menonaktifkan-AzureRmTrafficManagerEndpoint](./Disable-AzureRmTrafficManagerEndpoint.md)

[Enable-AzureRmTrafficManagerEndpoint](./Enable-AzureRmTrafficManagerEndpoint.md)

[New-AzureRmTrafficManagerEndpoint](./New-AzureRmTrafficManagerEndpoint.md)

[Hapus-AzureRmTrafficManagerEndpoint](./Remove-AzureRmTrafficManagerEndpoint.md)

[Set-AzureRmTrafficManagerEndpoint](./Set-AzureRmTrafficManagerEndpoint.md)


