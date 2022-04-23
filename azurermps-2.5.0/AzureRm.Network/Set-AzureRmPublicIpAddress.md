---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: EC798838-1850-4E88-B17F-D2F00F2D4EE9
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/set-azurermpublicipaddress
schema: 2.0.0
ms.openlocfilehash: d78e4d8e84508e9a737bb15dc31b0dad1c9bdedc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143168111"
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

 Perintah pertama mendapatkan sumber daya alamat IP publik dengan nama $publicIPName dalam $rgName grup sumber daya.
Perintah kedua mengatur metode alokasi objek alamat IP publik menjadi "Statis".
Set-AzureRmPublicIPAddress perintah memperbarui sumber daya alamat IP publik dengan objek yang diperbarui, dan mengubah metode alokasi menjadi 'Statis'. Alamat IP publik langsung dialokasikan.

### 2: Mengubah label domain DNS dari alamat IP publik
```
PS C:\> $publicIp = Get-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName

PS C:\> $publicIp.DnsSettings.DomainNameLabel = "newdnsprefix"
    
PS C:\> Set-AzureRmPublicIpAddress -PublicIpAddress $publicIp

PS C:\> $publicIp = Get-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
```

Perintah pertama mendapatkan sumber daya alamat IP publik dengan nama $publicIPName dalam $rgName grup sumber daya.
Perintah kedua mengatur properti DomainNameLabel ke prefiks dns yang diperlukan.
Set-AzureRmPublicIPAddress perintah memperbarui sumber daya alamat IP publik dengan objek yang diperbarui. DomainNameLabel & Fqdn diubah seperti yang diharapkan.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Menentukan objek **PublicIpAddress** yang mewakili status tujuan untuk mengatur alamat IP publik.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSPublicIpAddress
Parameter 'PublicIpAddress' menerima nilai tipe 'PSPublicIpAddress' dari pipeline

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress

## NOTES

## RELATED LINKS

[Get-AzureRmPublicIpAddress](./Get-AzureRmPublicIpAddress.md)

[Baru-AzureRmPublicIpAddress](./New-AzureRmPublicIpAddress.md)

[Hapus-AzureRmPublicIpAddress](./Remove-AzureRmPublicIpAddress.md)


