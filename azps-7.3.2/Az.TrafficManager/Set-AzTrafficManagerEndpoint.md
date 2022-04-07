---
external help file: Microsoft.Azure.PowerShell.Cmdlets.TrafficManager.dll-Help.xml
Module Name: Az.TrafficManager
ms.assetid: 5287D4DB-2709-4A3C-97D5-DB494CEEFD18
online version: https://docs.microsoft.com/powershell/module/az.trafficmanager/set-aztrafficmanagerendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Set-AzTrafficManagerEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Set-AzTrafficManagerEndpoint.md
ms.openlocfilehash: 69132b7cb1c263596aed34e33a8c2b9c07b88322
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140178200"
---
# Set-AzTrafficManagerEndpoint

## SYNOPSIS
Memperbarui titik Traffic Manager akhir.

## SYNTAX

```
Set-AzTrafficManagerEndpoint -TrafficManagerEndpoint <TrafficManagerEndpoint>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzTrafficManagerEndpoint** memperbarui titik akhir di Azure Traffic Manager.
Cmdlet ini memperbarui pengaturan dari objek titik akhir lokal.
Anda bisa menentukan objek titik akhir baik dengan menggunakan parameter *TrafficManagerEndpoint* atau dengan menggunakan saluran.

Anda dapat memperoleh objek lokal yang mewakili titik akhir menggunakan cmdlet Get-AzTrafficManagerEndpoint.
Ubah objek secara lokal lalu gunakan **Set-AzTrafficManagerEndpoint** untuk melakukan perubahan Anda.

## EXAMPLES

### Contoh 1: Memperbarui titik akhir
```
PS C:\>$TrafficManagerEndpoint = Get-AzTrafficManagerEndpoint -Name "endpoint1" -Type AzureEndpoints -ProfileName "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> $TrafficManagerEndpoint.Weight = 20
PS C:\> Set-AzTrafficManagerEndpoint -TrafficManagerEndpoint $TrafficManagerEndpoint
```

Perintah pertama mendapatkan titik Azure Traffic Manager titik akhir dengan menggunakan cmdlet **Get-AzTrafficManagerEndpoint**.
Perintah menyimpan titik akhir secara lokal dalam $TrafficManagerEndpoint variabel.

Perintah kedua akan mengubah titik akhir secara lokal.
Perintah ini mengubah bobot titik akhir menjadi 20.

Perintah ketiga memperbarui titik akhir pada Traffic Manager sesuai dengan nilai lokal dalam $TrafficManagerEndpoint.

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

### -TrafficManagerEndpoint
Menentukan objek **TrafficManagerEndpoint** lokal.
Cmdlet ini memperbarui Traffic Manager cocok dengan objek lokal ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerEndpoint

## OUTPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerEndpoint

## CATATAN

## RELATED LINKS
