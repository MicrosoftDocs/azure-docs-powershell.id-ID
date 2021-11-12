---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 1AB168AA-F466-4C7C-9AD7-0BC7AEEBC932
online version: ''
schema: 2.0.0
ms.openlocfilehash: d27470fd28bf28f52666524ec398181a2ad1317b
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426522"
---
# Set-AzureVNetGatewayKey

## SYNOPSIS
Mengatur kunci yang telah dibagikan untuk koneksi antara gateway Azure VPN dan situs jaringan lokal.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureVNetGatewayKey -VNetName <String> -LocalNetworkSiteName <String> -SharedKey <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureVNetGatewayKey** mengatur kunci bersama untuk koneksi antara gateway jaringan privat virtual Azure (VPN) dan situs jaringan lokal lokal.
Kunci harus sama dengan kunci yang dikonfigurasi di gateway situs jaringan lokal.
Jika tombol tidak cocok, koneksi tidak dapat menetapkan.

## EXAMPLES

## PARAMETERS

### -LocalNetworkSiteName
Menentukan nama situs jaringan lokal yang tersambung ke gateway jaringan virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedKey
Menentukan kunci bersama untuk ditetapkan ke gateway VPN.
Nilai harus berupa string alfanumerik tidak lebih dari 128 karakter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VNetName
Menentukan jaringan virtual di mana cmdlet ini mengatur kunci bersama untuk koneksi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureVNetGatewayKey](./Get-AzureVNetGatewayKey.md)


