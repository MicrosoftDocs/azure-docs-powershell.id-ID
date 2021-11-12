---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: A7DFF559-188D-4CF9-9315-CA327E0C5C0B
online version: ''
schema: 2.0.0
ms.openlocfilehash: c350fbeca7c8f915fbc759908a1317deb8bd6d060818be7ce7e63b91a927c2e2
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417709"
---
# Set-AzureRoute

## SYNOPSIS
Membuat rute dalam tabel rute.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureRoute -RouteName <String> -AddressPrefix <String> -NextHopType <String> [-NextHopIpAddress <String>]
 -RouteTable <IRouteTable> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRoute** membuat rute dalam tabel rute.
Rute baru diterapkan hampir secara langsung pada mesin virtual yang terkait dengan tabel rute.

## EXAMPLES

### Contoh 1: Add a virtual appliance next hop route
```
PS C:\> New-AzureRouteTable -Name "ApplianceRouteTable" -Location "Central US" -Label "Appliance Route Table" | Set-AzureRoute -RouteName "ApplianceRoute03" -AddressPrefix "10.0.0.0/24" -NextHopType VirtualAppliance -NextHopIpAddress "10.0.1.5"

Routes                        Name                          Location                      Label
------                        ----                          --------                      -----
{approute}                    AppRT                         Central US                    Appliance Route Table
```

Perintah ini membuat tabel rute bernama ApplianceRouteTable di lokasi yang ditentukan.
Perintah melewati tabel rute itu ke cmdlet saat ini.
Cmdlet saat ini menambahkan rute bernama ApplianceRoute03, yang merupakan VirtualAppliance tipe hop berikutnya.
Perintah menentukan alamat IP hop berikutnya dan prefiks alamat untuk rute tersebut.

### Contoh 2: Tambahkan Internet rute hop berikutnya
```
PS C:\> Get-AzureRouteTable -Name "ApplianceRouteTable" | Set-AzureRoute -RouteName "InternetRoute" -AddressPrefix "0.0.0.0/0" -NextHopType Internet

Routes                        Name                          Location                      Label
------                        ----                          --------                      -----
{approute, internetroute}     AppRT                         Central US                    Appliance Route Table
```

Perintah ini mendapatkan tabel rute bernama TabelRoute.
Perintah melewati tabel rute itu ke cmdlet saat ini.
Cmdlet saat ini menambahkan rute bernama InternetRoute, yang merupakan tipe hop internet berikutnya.
Perintah menentukan prefiks alamat untuk rute tersebut.

## PARAMETERS

### -AddressPrefix
Menentukan prefiks alamat untuk rute baru.

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

### -NextHopIpAddress
Menentukan alamat IP alat yang merupakan hop berikutnya untuk lalu lintas yang menggunakan rute ini.
Tentukan nilai ini hanya jika Anda menentukan nilai VirtualAppliance untuk parameter *NextHopType.*

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHopType
Menentukan tipe hop berikutnya untuk lalu lintas yang menggunakan rute ini.
Nilai valid adalah: 

- VPNGateway
- VNETLocal
- Internet
- VirtualAppliance
- Null

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

### -RouteName
Menentukan nama untuk rute baru yang penambahan cmdlet ini.

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

### -RouteTable
Menentukan tabel rute yang menambahkan rute baru kepada cmdlet ini.

```yaml
Type: IRouteTable
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Remove-AzureRoute](./Remove-AzureRoute.md)


