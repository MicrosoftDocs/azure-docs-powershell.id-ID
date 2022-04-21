---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
Module Name: AzureRM.TrafficManager
ms.assetid: 5287D4DB-2709-4A3C-97D5-DB494CEEFD18
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.trafficmanager/set-azurermtrafficmanagerendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Set-AzureRmTrafficManagerEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Set-AzureRmTrafficManagerEndpoint.md
ms.openlocfilehash: a6a5b9ed5dbf1faa4a2be345039e53bb3daae291
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142657414"
---
# Set-AzureRmTrafficManagerEndpoint

## SYNOPSIS
Memperbarui titik akhir Traffic Manager.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmTrafficManagerEndpoint -TrafficManagerEndpoint <TrafficManagerEndpoint>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmTrafficManagerEndpoint** memperbarui titik akhir dalam Azure Traffic Manager.
Cmdlet ini memperbarui pengaturan dari objek titik akhir lokal.
Anda bisa menentukan objek titik akhir baik dengan menggunakan parameter *TrafficManagerEndpoint* atau dengan menggunakan pipeline.

Anda bisa mendapatkan objek lokal yang mewakili titik akhir dengan menggunakan cmdlet Get-AzureRmTrafficManagerEndpoint.
Ubah objek secara lokal lalu gunakan **Set-AzureRmTrafficManagerEndpoint** untuk melakukan perubahan Anda.

## EXAMPLES

### Contoh 1: Memperbarui titik akhir
```
PS C:\>$TrafficManagerEndpoint = Get-AzureRmTrafficManagerEndpoint -Name "endpoint1" -Type AzureEndpoints -ProfileName "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> $TrafficManagerEndpoint.Weight = 20
PS C:\> Set-AzureRmTrafficManagerEndpoint -TrafficManagerEndpoint $TrafficManagerEndpoint
```

Perintah pertama mendapatkan titik akhir Azure Traffic Manager menggunakan cmdlet **Get-AzureRmTrafficManagerEndpoint**.
Perintah menyimpan titik akhir secara lokal dalam variabel $TrafficManagerEndpoint.

Perintah kedua mengubah titik akhir secara lokal.
Perintah ini mengubah berat titik akhir menjadi 20.

Perintah ketiga memperbarui titik akhir di Traffic Manager agar sesuai dengan nilai lokal dalam $TrafficManagerEndpoint.

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

### -TrafficManagerEndpoint
Menentukan objek **TrafficManagerEndpoint** lokal.
Cmdlet ini memperbarui Traffic Manager agar sesuai dengan objek lokal ini.

```yaml
Type: Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerEndpoint
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerEndpoint
Cmdlet ini menerima objek **TrafficManagerEndpoint** .

## OUTPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerEndpoint
Cmdlet ini mengembalikan objek **TrafficManagerEndpoint** .

## NOTES

## RELATED LINKS
