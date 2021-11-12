---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
Module Name: AzureRM.TrafficManager
ms.assetid: 5287D4DB-2709-4A3C-97D5-DB494CEEFD18
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Set-AzureRmTrafficManagerEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Set-AzureRmTrafficManagerEndpoint.md
ms.openlocfilehash: 8856a2f9f1a65d6d312571d75e2400a7dcf30bc0
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427226"
---
# Set-AzureRmTrafficManagerEndpoint

## SYNOPSIS
Memperbarui titik Traffic Manager akhir.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmTrafficManagerEndpoint -TrafficManagerEndpoint <TrafficManagerEndpoint>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmTrafficManagerEndpoint** memperbarui titik akhir di Azure Traffic Manager.
Cmdlet ini memperbarui pengaturan dari objek titik akhir lokal.
Anda bisa menentukan objek titik akhir baik dengan menggunakan parameter *TrafficManagerEndpoint* atau dengan menggunakan saluran.

Anda dapat memperoleh objek lokal yang mewakili titik akhir menggunakan cmdlet Get-AzureRmTrafficManagerEndpoint.
Ubah objek secara lokal lalu gunakan **Set-AzureRmTrafficManagerEndpoint** untuk melakukan perubahan Anda.

## EXAMPLES

### Contoh 1: Memperbarui titik akhir
```
PS C:\>$TrafficManagerEndpoint = Get-AzureRmTrafficManagerEndpoint -Name "endpoint1" -Type AzureEndpoints -ProfileName "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> $TrafficManagerEndpoint.Weight = 20
PS C:\> Set-AzureRmTrafficManagerEndpoint -TrafficManagerEndpoint $TrafficManagerEndpoint
```

Perintah pertama mendapatkan titik akhir Azure Traffic Manager dengan menggunakan cmdlet **Get-AzureRmTrafficManagerEndpoint.**
Perintah menyimpan titik akhir secara lokal dalam $TrafficManagerEndpoint baru.

Perintah kedua akan mengubah titik akhir secara lokal.
Perintah ini mengubah bobot titik akhir menjadi 20.

Perintah ketiga memperbarui titik akhir di Traffic Manager sesuai dengan nilai lokal dalam $TrafficManagerEndpoint.

## PARAMETERS

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

### Microsoft.Azure.Commands.Network.TrafficManagerEndpoint
Cmdlet ini menerima objek **TrafficManagerEndpoint.**

## OUTPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerEndpoint
Cmdlet ini mengembalikan objek **TrafficManagerEndpoint.**

## CATATAN

## RELATED LINKS

