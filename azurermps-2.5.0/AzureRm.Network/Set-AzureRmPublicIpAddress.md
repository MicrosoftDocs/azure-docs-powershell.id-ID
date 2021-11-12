---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: EC798838-1850-4E88-B17F-D2F00F2D4EE9
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/set-azurermpublicipaddress
schema: 2.0.0
ms.openlocfilehash: d78e4d8e84508e9a737bb15dc31b0dad1c9bdedc
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423942"
---
# Set-AzureRmPublicIpAddress

## SYNOPSIS
Menetapkan status tujuan untuk alamat IP publik.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmPublicIpAddress -PublicIpAddress <PSPublicIpAddress> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmPublicIpAddress** menetapkan status tujuan untuk alamat IP publik.

## EXAMPLES

### 1: Mengubah metode alokasi alamat IP publik
```
PS C:\> $publicIp = Get-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName

PS C:\> $publicIp.PublicIpAllocationMethod = "Dynamic"
    
PS C:\> Set-AzureRmPublicIpAddress -PublicIpAddress $publicIp

PS C:\> $publicIp = Get-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
```

 Perintah pertama mendapatkan sumber daya alamat IP publik dengan nama $publicIPName dalam grup sumber daya $rgName.
Perintah kedua mengatur metode alokasi objek alamat IP publik menjadi "Statis".
Set-AzureRmPublicIPAddress umum memperbarui sumber daya alamat IP publik dengan objek yang diperbarui, dan mengubah metode alokasi menjadi 'Statis'. Alamat IP publik akan dialokasikan dengan segera.

### 2: Mengubah label domain DNS dari alamat IP publik
```
PS C:\> $publicIp = Get-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName

PS C:\> $publicIp.DnsSettings.DomainNameLabel = "newdnsprefix"
    
PS C:\> Set-AzureRmPublicIpAddress -PublicIpAddress $publicIp

PS C:\> $publicIp = Get-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
```

Perintah pertama mendapatkan sumber daya alamat IP publik dengan nama $publicIPName dalam grup sumber daya $rgName.
Perintah kedua mengatur properti DomainNameLabel ke prefiks dns yang diperlukan.
Set-AzureRmPublicIPAddress ip publik memperbarui sumber daya alamat IP publik dengan objek yang diperbarui. DomainNameLabel & Fqdn dimodifikasi seperti yang diharapkan.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -PublicIpAddress
Menentukan objek **PublicIpAddress** yang mewakili status tujuan yang harus ditetapkan alamat IP publik.

```yaml
Type: PSPublicIpAddress
Parameter Sets: (All)
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

### PSPublicIpAddress
Parameter 'PublicIpAddress' menerima nilai tipe 'PSPublicIpAddress' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress

## CATATAN

## RELATED LINKS

[Get-AzureRmPublicIpAddress](./Get-AzureRmPublicIpAddress.md)

[New-AzureRmPublicIpAddress](./New-AzureRmPublicIpAddress.md)

[Remove-AzureRmPublicIpAddress](./Remove-AzureRmPublicIpAddress.md)


